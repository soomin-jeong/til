# 190909
[ EC2 ]

1. Problem: Several instances are connected to the same ELB and URI. You need to check an error log, status, etc in a specific instance.
2. Solution: Specify the instance IP in your host configuation
3. How To:
  1) edit ```/etc/hosts```
  2) add a line of ```[instance IP] URI```
  for example, ```123.456.78.90 google.com```
  3) safely commentize it after the test
