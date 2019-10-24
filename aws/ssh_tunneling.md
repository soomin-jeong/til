# 191024
[ SSH Tunneling ]

* Problem: Accessing the production database via IDE was not allowed, because the the public accessibility for RDS was set No . The security group set up was quite complicated on our production server. Changing the SG configuration was tricky since it could block a valid access right away.
* Solution: SSL Tunneling

1. Concept
    1. A proxy server connected to the client (me) copies the data from a backend service (my target) without any direct inference in the SSL connection.
2. Advantages
    1. As long as it’s on TCP connection, any program (including those not supporting SSH) can be connected by SSH.
3. Steps
    1. Launch an extra instance connected to the target Database.
    2. Check if the instance can be connected to the Database.
        ```
        nc -v <RDS_Endpoint> 3306
        ```
    3. Check if the local machine connected to the instance connected to the Database
        ```
        ssh -i <pemfile_path> <user>@ec2-user@ec2_publicDns -N -L 3306:<user>@RDS_endpoint:3306
        ```
