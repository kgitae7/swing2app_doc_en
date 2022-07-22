# OneSignal Integration for WebView Prototype Apps

Swing2App recently release a new feature for the WebView apps. Earlier if a user wanted to convert their website to an app and wanted to send push notifications to users then they had to make Push-only prototype of apps only but now the WebView prototype app users can also send and receive unlimited push notifications with the simple integration of OneSignal with Swing2App.

<mark style="color:red;">**\*Caution:**</mark>\ <mark style="color:red;"></mark><mark style="color:red;">**This tutorial and OneSignal integration is working only in Web-View prototype only.**</mark>

&#x20;<mark style="color:red;"></mark>&#x20;

Let’s check out the step by step process of integration.

<mark style="color:blue;">**SETTING ONESIGNAL ACCOUNT ON ONESIGNAL DASHBOARD**</mark>

Subscribe to the services of OneSignal on [https://www.onesignal.com](https://www.onesignal.com/)

1. Once you are done with the signup, on the dashboard, click <mark style="color:blue;"></mark> <mark style="color:blue;"></mark><mark style="color:blue;">**‘New App/Website’**</mark>

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2177.png)

2\. Fill in the relevant details.

* Input your app name
* Choose platform (Google Android)
* Click **Configure Your Platform**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2196.png)

* Select Google Android in Settings page.

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2180.png)

&#x20;

* Input Firebase Server Key , Sender ID\
  ([https://documentation.onesignal.com/docs/generate-a-google-server-api-key](https://documentation.onesignal.com/docs/generate-a-google-server-api-key))\
  You can refer how to get server key and sender ID

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2195.png)

Similarly, setup OneSignal Platform (Apple iOS) (if you are not using iOS , you can skip this )

* **Go to platform -> Click Apple iOS**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2182.png)

&#x20;

* Input p12 file
* Input Production Private Key Password
* p12 file and password will be provided by Swing2App. To get the p12 file and password, please drop an email as [help@swing2app.com](mailto:help@swing2app.com).\
  <mark style="color:red;">**Please note:**</mark> <mark style="color:red;"></mark><mark style="color:red;">For this, your app should be first released to the App Store.</mark>

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2194.png)

***

&#x20;

<mark style="color:blue;">**INTEGRATING ONESIGNAL ACCOUNT WITH SWING2APP**</mark>

1. You would have to setup OneSignal on Maker(V2) page of the same app.
   * Go to **Maker(V2)**
   * Click on **Advanced**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2185.png)

&#x20;

2\.  Input **OneSignal App ID** on swing2app and click **Update.**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2187.png)

&#x20;<mark style="color:orange;"></mark>&#x20;

<mark style="color:orange;">**How to find OneSignal app ID on OneSignal dashboard**</mark>

* Go to your OneSignal app
* Click Keys & IDs

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2188.png)

&#x20;

<mark style="color:orange;">**Sending Push Notification on OneSignal dashboard**</mark>

* Go to **Messages.**
* Click **New Push.**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2189.png)

&#x20;

* A message screen will open.
* Input Message and Setting message option

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2193.png)

&#x20;<mark style="color:blue;">**Tip. If you want to send push notification as link then click**</mark>

– Input “link” on **KEY** in additional data

– Input the URL in **Value** field.

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2191.png)

&#x20;

Once all the information is entered the message settings, click **Confirm** and **Send Message.**

![](https://support.swing2app.com/wp-content/uploads/2020/11/Group-2192.png)

&#x20;

You can send push notification via OneSignal its unlimited and free.

You can utilize sending another option provided by OneSignal. Push notification will be sent only to the users who has installed the user’s app.
