
# Linux Server Configuration

The Linux Server is configured on azure. A database server is installed and configured , and an existing web application is deployed onto it.

## Components for grader Access

1. IP Address/DNS: 40.76.207.238, http://sportscatalog.eastus.cloudapp.azure.com
2. SSH Port: 2200

## Summary of Software Installed

1. Python 2
2. Flask
3. Sqlalchemy.orm
4. Oauth2client
5. Postgresql
6. Psycopg2
7. Python 3 mod_wsgi package
8. NTP
9. NGINX

## Configurations Made

1. Created user named 'grader' and gave sudo access.
2. Enforced Key-based Authentication.
3. Disabled remote user login.
4. Disabled Password based logins by modifying the sshd_config file.
5. Changed SSH port from 22 to 2200 by routing traffic from 2200 to 22. Incoming traffic on port 22 is disabled.
        sudo iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 2200 -j REDIRECT --to-port 22
6. VM Configured to allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).


## Web App Deployed
http://sportscatalog.eastus.cloudapp.azure.com

Udacity Item Catalog Project https://github.com/bhorkar/udacity_item_catalog is deployed. It manages sports item catalog.

## Resources
Changing ssh port on azure: https://stackoverflow.com/questions/35780769/changing-ssh-port-22-to-a-custom-port-in-azure-resource-group-vm
Using nginx web server: https://www.patricksoftwareblog.com/how-to-configure-nginx-for-a-flask-web-application/


