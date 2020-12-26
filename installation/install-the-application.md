# Install the application

Installing Gatekeeper is a fairly straight forward process:

```
$ snap install gatekeeper
```

Upon running the command, Gatekeeper will be started and the setup wizard available via the web interface at _http://\[your-ip\]/install._

{% hint style="info" %}
The setup wizard will only be accessible once. Do not close or reload the tab. If you do, you will have to reinstall Gatekeeper.
{% endhint %}

### Configuring HTTPS

The setup wizard will ask you what certificates the Gatekeeper server should use. The following options are available:

* Using "[Let's Encrypt](https://letsencrypt.org/)", a nonprofit Certificate Authority, which will offer you free certificates. 
* Using Gatekeeper default certificates. 

We highly recommend choosing "Let's Encrypt" if your system is publicly accessible. Gatekeeper requires TLS certificates for several functionalities, by choosing "Let's Encrypt", the application will be able to automatically issue and renew certificates when needed.

{% hint style="info" %}
Gatekeeper currently does not support adding custom certificates.
{% endhint %}

### Configuring email sending

Gatekeeper uses emails to notify users of anomalous behaviour and offer ways to mitigate them.

The installation wizard will ask you for details to a SMTP account. The account needs to be able to send emails. Gatekeeper does not need to consume incoming emails.

### Creating the first user

As last step, Gatekeeper will ask you to create the initial user account. This user will have administrator rights, but you can remove the rights at any time.

