# hybrid-cloud-3-tier-private-cloud
## Design a blueprint to deploy and configure a three-tier web application with a load balancer, web server, and database VM hosted on the private cloud.

### Three tiers of the web application
1) A load balancer HAProxy on CentOS Linux VM
2) A web server Apache Server on CentOS Linux VM
3) A database server MySQL Server based on CentOS Linux VM

### Security & Configuration
1) All VM accounts require SSH access and can be granted sudo priviledges.
2) Deployment scenario named small and each VM uses 1 vCPU, 1 Core, 1 GB RAM
3) No VM resource parameter can be changed by end user except the Database VM memory
4) A MySQL password must be provided at run-time
5) MySQL database configured with MySQL user named webapp_user and a single table called tecc_dba_test
6) Web app installed to standard web docroot
7) Web app uses the database using tecc_webuser account.
8) Web app reads and writes to the tecc_dba_test database table.

### Additional Configuration
1) The web tier can scale-out and scale-in with the use of a variable / macro and is not hard coded.
2) The database backup action orchestrates the stor and restart of the Web Tier and Load Balancer before and after backup operations.
3) The cloud-init scripts leverage macros and variables not hard-coded account names and public keys.
4) The database password is a mandatory field and uses a regular expression to validate the length is 8 or more characters.

![Private Cloud 3 Tier Application](/project2/images/0-start.jpg)

