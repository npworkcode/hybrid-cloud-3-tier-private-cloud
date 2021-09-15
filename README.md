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
2) The database backup action orchestrates the stop and restart of the Web Tier and Load Balancer before and after backup operations.
3) The cloud-init scripts leverage macros and variables not hard-coded account names and public keys.
4) The database password is a mandatory field and uses a regular expression to validate the length is 8 or more characters.

# Create Blueprint for HAProxy, Apache Server and MySQL and create interdependencies
![Initial setup of 3 Tier environment](/project2/images/2021-02-02_141151-TeccWebApplication-Application.jpg)

# Configure WebScale function for Apache Server
![Web Scale Configuration](/project2/images/2021-02-02_141333-webscalein.jpg)

# Configure Database backup function for MySQL Server
![Database Backup Configuration](/project2/images/2021-02-02_141421-Database_Backup.jpg)

# Enter MySQL password before Deploying 3 Tier App
![MySQL Password](/project2/images/2021-02-02_141723-Tecc_3_Tier_App.jpg)

# Initial provisioning of 3 Tier App
![Provisioning Step](/project2/images/2021-02-02_142235-Tecc_3Tier_Services.jpg)

# Provisioning of MySQL Database
![Provisioning MySQL](/project2/images/2021-02-02_144003-MySQL_start.jpg)

# Provisioning of Apache Web Server
![Provisioning Apache](/project2/images/2021-02-02_144620-webserver_provisioning.jpg)

# Provisioning of HAProxy Server
![Provisioning HAProxy](/project2/images/2021-02-02_145734-Haproxy_provisioning.jpg)

# Demonstrate WebScaleOut funtion showing increase of WebServers deployed from 2 to 3
![WebScaleOut Apache](/project2/images/2021-02-02_151123-webscaleout.jpg)

# Show WebServer Services after WebScaleOut
![WebScaleOut Apache Deployed Services](/project2/images/2021-02-02_151216-webscaleout_services.jpg)

# Show All Functions for 3 Tier App Deployment
![Functions for 3 Tier App](/project2/images/2021-02-02_151317-webscale_service.jpg)

# Activate WebScaleIn Function to decrease the Number of Apache Servers by 1
![WebScaleIn for Apache Web Server](/project2/images/2021-02-02_152038-webscalein.jpg)

# Show WebServer Services after WebScaleIn
![WebScaleIn Apache Deployed Services](/project2/images/2021-02-02_152115-webscale-services.jpg)

# Unprovision all Services
![Delete All Deployed Services](/project2/images/2021-02-02_152344-application_delete.jpg)

# Show Private Cloud 3 Tier Deployment
![Private Cloud 3 Tier Application](/project2/images/0-start.jpg)

