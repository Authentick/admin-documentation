# Nextcloud

{% embed url="https://nextcloud.com/" %}

Nextcloud can be integrated using the LDAP directory and authentication mode. This enables users to login to Nextcloud using the regular web login, the Nextcloud server will be able to enumerate all users.

## Gatekeeper configuration

Configure LDAP authentication and Directory mode as described in our documentation.

{% page-ref page="../understanding-settings/authentication-modes/ldap-authentication.md" %}

{% page-ref page="../understanding-settings/directory-modes/ldap-directory.md" %}

Take note of the bind credentials as well as the base DN.

## Nextcloud configuration

Install the LDAP app as described in the Nextcloud documentation:

{% embed url="https://docs.nextcloud.com/server/20/admin\_manual/configuration\_user/user\_auth\_ldap.html" %}

You will have to configure the following settings:

{% tabs %}
{% tab title="Server" %}
* **Host:** Use the hostname shown in the Gatekeeper configuration.
* **User DN:** Use the User DN shown in the Gatekeeper configuration.
* **Base DN:** Use the Base DN shown in the Gatekeeper configuration.
{% endtab %}

{% tab title="Users" %}
* **Only these object classes:** inetOrgPerson
{% endtab %}

{% tab title="Login attributes" %}
* **LDAP/AD Username:** ✅\*\*\*\*
* **Other Attributes:** email
{% endtab %}

{% tab title="Advanced" %}
* **Directory Settings**
  * **User Display Name Field:** displayname
* **Special Attributes**
  *  **Email Field:** email
{% endtab %}
{% endtabs %}

Upon configuration, you should be able to see all granted users in the "Users" settings and also be able to authenticate individually.

{% hint style="info" %}
Users will have to generate app-specific passwords for each login inside Gatekeeper.
{% endhint %}

