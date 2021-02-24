# OpenID Connect

## How does this mode work?

In this mode your third-party application will redirect users back to Authentick for authentication using the OpenID Connect protocol.

## Configuring OpenID Connect

OpenID Connect requires you to configure the Redirect URI. This URI must be fully-qualified and will be matched strictly. \(example: `https://example.com/oidc_redirect`\)

Your third-party application will need to configure the OpenID Connect details created by Authentick, as explained in the next section.

## Viewing OpenID Connect settings

The application settings will show you the following details which you usually need to configure in your third-party application:

* Metadata URL
* Client ID
* Client Secret

