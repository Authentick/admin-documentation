# LDAP directory

## How does this mode work?

Gatekeeper will create a LDAP directory for the application. The third-party application can connect to it and get a list of all users.

## Configuring LDAP directory

LDAP directory requires requires no further configuration besides enabling it for a given application in the application settings. 

## Viewing LDAP settings

In the application settings you will find the following details:

* Hostname and port of the LDAP server
* Base DN of the LDAP configuration
* Bind User
* Bind User Password

You will need to configure these details inside your application to connect against Gatekeeper.

