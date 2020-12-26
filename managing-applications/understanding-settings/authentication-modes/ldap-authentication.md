# LDAP authentication

{% hint style="warning" %}
LDAP authentication requires users to create an application-specific password. The security is reduced as the login flow doesn't happen via the Gatekeeper web interface.

We recommend using LDAP authentication only if the other modes are not an option.
{% endhint %}

## How does this mode work?

In this mode users will login on your third-party application directly. The third-party application will have to connect to the Gatekeeper LDAP server to validate the credentials

This flow does not use the web interface and is usually used in cases where a web interface isn't supported. \(e.g. configuring server applications such as Postfix\)

## Configuring LDAP authentication

LDAP authentication requires requires no further configuration besides enabling it for a given application in the application settings. 

## Viewing LDAP settings

In the application settings you will find the following details:

* Hostname and port of the LDAP server
* Base DN of the LDAP configuration

You will need to configure these details inside your application to connect against Gatekeeper.

