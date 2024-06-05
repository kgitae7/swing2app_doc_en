# Javascript Integration API Documentation

It is a javascript API that allows you to control the web view and the push-only prototype app provided by Swing2App.

In short, include and use the following js file through the API specification below and perform the functions you need.

{% hint style="info" %}
Common js file Please include the following js file in your HTML file
{% endhint %}

{% code overflow="wrap" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2024_02_28_002/js/swing_app_on_web.js"></script>
```
{% endcode %}

## WebView Javascript API Specifications

## Webview Control Related Methods



#### • **Webview Backwards** <a href="#back-webview" id="back-webview"></a>

To Move to the previous page in the webview app. Same style as the back function in the web browser

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.webview.back();
```
{% endcode %}



#### • **Webview Forward** <a href="#forward-webview" id="forward-webview"></a>

Move to the front page in the webview app. Same style as the forward function in the web browser

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.webview.forward();
```
{% endcode %}

#### • Go to Webview Home <a href="#go-to-home" id="go-to-home"></a>

Ability to navigate from the webview app to the home page (set initial page) set in the Swing2App.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.navigateToHome()
```
{% endcode %}



#### • **Clean Web Cache** <a href="#webview-clear-cache" id="webview-clear-cache"></a>

Command to Clear Cache in WebView&#x20;

<mark style="color:blue;">\*Available from js lib version 2024\_02\_28\_002</mark>

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.webview.clearCache()
```
{% endcode %}

## Controlling the Toolbar methods

#### • Enabling the Toolbar <a href="#toolbar-setting" id="toolbar-setting"></a>

You can control the Toolbar via API in a push-only prototype.

You can hide, enable, and set the auto-hide option for the toolbar while the app is running.

<mark style="color:blue;">\*Available from js lib version 2024\_02\_28\_002</mark>

{% code lineNumbers="true" %}
```javascript
// toolbar active , autohide inactive
// swingWebViewPlugin.app.webview.updateToolbar(true,false)
// toolbar active , autohide active 
// swingWebViewPlugin.app.webview.updateToolbar(true,true)
// toolbar inactive , autohide inactive
// swingWebViewPlugin.app.webview.updateToolbar(false,false)
swingWebViewPlugin.app.webview.updateToolbar(false,false)
```
{% endcode %}



## Application-related methods



#### • **Get platform information** <a href="#get-platform-info" id="get-platform-info"></a>

Functions for getting platform information from the web

{% code lineNumbers="true" %}
```javascript
if( swingWebViewPlugin.app.methods.getCurrentPlatform() == 'android' )
{
    console.log('android');
}
else if( swingWebViewPlugin.app.methods.getCurrentPlatform() == 'ios' )
{
    console.log('ios');
}
else
{
    console.log('web browser');
}
```
{% endcode %}



#### • **Get version and device information** <a href="#get-version-device-info" id="get-version-device-info"></a>

A function that gets the version of the app and the H/W and S/W information of the device

{% code lineNumbers="true" %}
```javascript
// android
swingWebViewPlugin.app.methods.getAppVersion(function(value){
    console.log('model : ' + value.model);
    console.log('sdk_version : ' + value.version);
    console.log('version_release : ' + value.version_release);
    console.log('manufacturer : ' + value.manufacturer);
    console.log('app_version : ' + value.appVersion);
    console.log('radio_version : ' + value.radio_version);
    console.log('package_name : ' + value.packageName);
});

// ios
swingWebViewPlugin.app.methods.getAppVersion(function(value){
    console.log('model : ' + value.model);
    console.log('name : ' + value.name);
    console.log('systemVersion : ' + value.systemVersion);
    console.log('appVersion : ' + value.appVersion);
    console.log('bundleVersion : ' + value.bundleVersion);
    console.log('bundleID : ' + value.bundleID);
});
```
{% endcode %}



#### • **Close application** <a href="#how-to-exit-app" id="how-to-exit-app"></a>

Command to terminate a running app

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doExitApp();
```
{% endcode %}

#### • **Run a URL with an external browser** <a href="#open-external-browser-specific-url" id="open-external-browser-specific-url"></a>

If you want to open a specific page with the default browser of an app such as Chrome or Safari, you can use the following function.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doExternalOpen('https://www.swing2app.com');
```
{% endcode %}



#### • **Run URLs with the embedded browser** <a href="#open-browser-specific-url" id="open-browser-specific-url"></a>

Run using Android and iOS's own built-in browser.

If you must use Chrome and Safari, you can operate Chrome and Safari from inside the app through the code below.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.openBrowser('https://www.swing2app.com');
```
{% endcode %}

#### • **Share the current page** <a href="#share-current-page" id="share-current-page"></a>

Run the code below for the current Web page-sharing feature

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doShareCurrentPage();
```
{% endcode %}

#### • **Share a custom URL** <a href="#share-specific-url" id="share-specific-url"></a>

If you want to share the specified URL, run the code as shown below.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.doShareWithUrl('https://www.swing2app.com');
```
{% endcode %}



#### • **Checking the notification setting status of the application** <a href="#set-notification" id="set-notification"></a>

Ability to check the status of push alarm settings in the application.

If the push is disabled or if the push is turned off by the OS itself,

You can check if the app is turned off with its own settings.

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.isNotificationEnabled(function (result) {
    if( result == '1' ) // Able to send push notification
    {
        console.log('push active');
    }
    else if( result == 'off_on_system' )    // Disabling app push by OS setting
    {
        console.log('push inactive');
    }
    else if( result == 'off_on_app' )       // Disable App Push by App Settings
    {
        console.log('push inactive');
    }
});
```
{% endcode %}

Ex:) Code example for recommending activation when Off setting according to push setting

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.methods.isNotificationEnabled(function (result) {
    if( result == '1' ) // Able to send push notification
    {
        console.log('push active');
    }
    else if( result == 'off_on_system' )    // Disabling app push by OS setting
    {
        console.log('push inactive');
        swingWebViewPlugin.app.methods.goToNotificationSetting("system"); // Open Notification Setting in System setting
    }
    else if( result == 'off_on_app' )       // Disable App Push by App Settings
    {
        console.log('push inactive');
        swingWebViewPlugin.app.methods.goToNotificationSetting("app");    // Open Notification Setting in App
    }
});
```
{% endcode %}



Ability to move alarm settings of applications or systems

(1) Go to the screen where you can set the alarm by the application itself

```javascript
swingWebViewPlugin.app.methods.goToNotificationSetting('app');
```

(2) Go to the screen where you can set your own alarm for the system (Android, iOS)

```javascript
swingWebViewPlugin.app.methods.goToNotificationSetting('system');
```

##

## Methods related to AdMob

This is a command that allows you to manage in-app AdMob ads directly from the website.

Please refer to the information below to use the ads.

{% hint style="info" %}
This command only works for apps with ad mob enabled
{% endhint %}



#### • **Show banner ads** <a href="#show-admob-banner" id="show-admob-banner"></a>

Commands to display AdMob banner ads in applications

| Parameter | Explanation             | Example values                         |
| --------- | ----------------------- | -------------------------------------- |
| adId      | Enter banner ad unit ID | ca-app-pub-3940256099942544/6300978111 |

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.showBanner('ca-app-pub-3940256099942544/6300978111');
```
{% endcode %}

* **End banner ads**

Command to stop AdMob banner ads in the application

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.closeBanner();
```
{% endcode %}

* **Show interstitial ads**

Commands to display AdMob interstitial ads in applications

| Parameter | Explanation                | Example values                         |
| --------- | -------------------------- | -------------------------------------- |
| adId      | Enter interstitial unit ID | ca-app-pub-3940256099942544/6300978111 |

{% code lineNumbers="true" %}
```javascript
swingWebViewPlugin.app.admob.showInterstitialAd('ca-app-pub-3940256099942544/6300978111');
```
{% endcode %}
