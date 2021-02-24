# mod\_auth\_openidc

{% embed url="https://github.com/zmartzone/mod\_auth\_openidc" %}

[`mod_auth_openidc`](https://github.com/zmartzone/mod_auth_openidc) is an Apache module implementing the OpenID Connect standard. The module allows you to add OpenID Connect to any existing Apache service.

{% hint style="info" %}
Authentick Proxy can also be put in front of your application and offers additional features such as instant session revocation.
{% endhint %}

## Authentick configuration

Setup an OpenID Connect app as described in the documentation, as Redirect URI configure `https://<my-hostname>/gatekeeper-oidc-redirect`

{% page-ref page="../understanding-settings/authentication-modes/openid-connect.md" %}

Upon configuration, take note of the following entries which you'll need these for the Apache configuration:

* Metadata URL
* Client ID
* Client Secret

## Apache configuration

The [`mod_auth_openidc` documentation](https://github.com/zmartzone/mod_auth_openidc/blob/master/README.md) contains a lot of information about more advanced setups.

For a simple setup, which would protect the `/var/www/html` folder, the following should suffice:

```text
OIDCProviderMetadataURL {METADATA_URL_FROM_THE_SETTINGS}
OIDCRedirectURI /gatekeeper-oidc-redirect
OIDCClientID {CLIENT_ID_FROM_THE_SETTINGS}
OIDCClientSecret {CLIENT_SECRET_FROM_THE_SETTINGS}
OIDCCryptoPassphrase {LONG_AND_SECURE_RANDOM_TEXT_GENERATED_BY_YOU_KEEP_IT_SECRET}

<Directory "/var/www/html/">
   AuthType openid-connect
   Require valid-user
</Directory>
```

