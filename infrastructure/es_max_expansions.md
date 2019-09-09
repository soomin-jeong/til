# 190909
[ ElasticSearch ]

0. Lesson Leanred: Set ```max_expansions``` in case of requesting **Match Query** or **Multi Match Query**

1. Problem: There was a significant latency on searching username on elaticsearch.

2. Solution implemented: added max_expansions option to limit the number of response

```
query = User.search().query('multi_match', query=keyword, fields=['username', 'nickname'], type='phrase_prefix', max_expansions=10)
response = query.execute()
```

3. Tips
  - In case of multi match query, the ```max_expansions``` does **NOT** limit the final number of response since it limits the number of response for each field.
