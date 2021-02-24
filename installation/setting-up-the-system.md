---
description: Learn how to install your own Authentick server in minutes using Snap.
---

# Setting up the system

## How is Authentick shipped?

Authentick is currently only distributed as a [Snap](https://snapcraft.io/), which is a distribution format that bundles all dependencies and offers automatic updates. Most configuration is done automatically for you.

Whilst this ensures that you have a secure and up-to-date setup, it also has the downside that our opinionated release likely won't fit on an existing machine. Our Snap package will for example listen by default on port 80 and 443, which is likely to cause issues if you have other web applications installed.

{% hint style="warning" %}
Whilst there is a Docker image used for development purposes, we do advise against using it for production purposes.
{% endhint %}

## Supported distributions

Snap will run on most Linux distributions and is pre-installed already on Ubuntu. For simplicity, we would recommend taking the latest Ubuntu LTS \(long term support\) version as that is how we deploy it, but any other distributon won't make a difference.

{% hint style="info" %}
The official [Snap documentation](https://snapcraft.io/docs/installing-snapd) shows a list of supported distributions and guides on how to install Snap.
{% endhint %}

Make sure that you don't have any other services running on the system that is listening on any of these ports:

* 80 \(HTTP\)
* 389 \(LDAP\)
* 443 \(HTTPS\)

Gatekeeper may use different ports in the future, we **highly recommend** to install Authentick on a dedicated host for this reason.

## Required pre-requisites

Before you proceed, make sure you fulfill the following criteria:

* [ ] Running a supported distribution with Snap
* [ ] SMTP account

