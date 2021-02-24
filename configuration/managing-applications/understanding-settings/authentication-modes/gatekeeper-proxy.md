# Authentick Proxy

## How does this mode work?

In this mode Authentick will be acting as reverse proxy in front of the third-party application. Your third-party application will not need to be exposed to the internet directly.

This mode supports immediate session suspension. If a user logs out, Authentick Proxy is immediately aware of it.

The third-party application will receive a signed JWT assertion which identifies the currently logged-in user. Authentick Proxy can be used in combination with other authentication modes.

## Configuring Authentick Proxy

Authentick Proxy requires you to configure an Internal as well as a public hostname.

**Internal hostname:** Defines what host Authentick should connect to. This needs to include the HTTPS or HTTP protocol. \(example: `http://192.168.1.45`\)

**Public hostname:** Defines what the public hostname is that should be routed to the internal endpoint. \(example: `example.com`\)

{% hint style="info" %}
Authentick will automatically request a HTTPS certificate using Let's Encrypt, if you have enabled the certificate issuance in the setup.
{% endhint %}

Authentick will add the following headers to the request:

* **X-Forwarded-For:** Containing the original client IP address
* **X-Gatekeeper-Jwt-Assertion:** Containing the JWT assertion.

{% hint style="danger" %}
If your application is accessible from the internet directly, you **MUST** verify the **X-Gatekeeper-Jwt-Assertion** header. 
{% endhint %}

## Viewing Authentick Proxy settings

In the application settings you will find the following details:

* Internal hostname
* Public hostname

You usually do not need to change these in the future.

