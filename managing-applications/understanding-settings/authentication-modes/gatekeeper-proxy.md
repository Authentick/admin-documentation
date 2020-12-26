# Gatekeeper Proxy

## How does this mode work?

In this mode Gatekeeper will be acting as reverse proxy in front of the third-party application. Your third-party application will not need to be exposed to the internet directly.

This mode supports immediate session suspension. If a user logs out, Gatekeeper Proxy is immediately aware of it.

The third-party application will receive a signed JWT assertion which identifies the currently logged-in user.

## Configuring Gatekeeper Proxy

Gatekeeper Proxy requires you to configure an Internal as well as a Public hostname

**Internal hostname:** Defines what host Gatekeeper should connect to. This needs to include the HTTPS or HTTP protocol. \(example: `http://192.168.1.45`\)

**Public hostname:** Defines what the public hostname is that should be routed to the internal endpoint. \(example: `example.com`\)

{% hint style="info" %}
Gatekeeper will automatically request a HTTPS certificate using Let's Encrypt, if you have enabled the certificate issuance in the setup.
{% endhint %}

Gatekeeper will add the following headers to the request:

* **X-Forwarded-For:** Containing the original client IP address
* **X-Gatekeeper-Jwt-Assertion:** Containing the JWT assertion.

{% hint style="danger" %}
If your application is accessible from the internet directly, you **MUST** verify the **X-Gatekeeper-Jwt-Assertion** header. 
{% endhint %}

## Viewing Gatekeeper Proxy settings

In the application settings you will find the following details:

* Internal hostname
* Public hostname

You usually do not need to change these in the future.

