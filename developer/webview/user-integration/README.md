# Website Member Integration Guide

Website members linkage method (registering web users to Swing2App service).

It is a task to register by matching the device to the Swing2App DB.

We request JavaScript insertion for member linkage.

Please insert the following sentence in the common header (so that the script fits on all screens).

The user ID below refers to your web users.

### - Code inserted when logged in

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2022_06_17_001/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogin("test_account","test_name");
});
</script>
```
{% endcode %}

ex:) User ID: test\_account, Username: test\_name

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2022_06_17_001/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogin("test_account","test_name");
});
</script>
```
{% endcode %}

### - Code inserted when logged out or not logged in

{% code lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2022_06_17_001/js/swing_app_on_web.js"></script>
<script>
document.addEventListener("DOMContentLoaded", function() {
    swingWebViewPlugin.app.login.doAppLogout();
});
</script>
```
{% endcode %}

{% hint style="info" %}
js file insertion tips

(1) You only need to insert the js file once.

(2) It is recommended to insert it into the common header and footer of the website.
{% endhint %}

After completing the member linkage, you can send the push by the website itself using the push-sending API.

[\[Push Sending API Guide\]](../../server-side-api/)

