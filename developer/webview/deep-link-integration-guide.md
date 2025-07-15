# Deep Link Integration Guide

Swing2App offers deep link functionality for **Push-Only Apps**, allowing you to launch the app or redirect users to specific URLs.\
This guide explains how to implement deep links, encode URLs, and locate your app ID for integration.

***

## ✅ Basic Deep Link Structure

The basic format for using Swing2App’s deep link is as follows:

```
https://www.swing2app.com/swapi/openAppWithUrl?appId={app_id}
```

* `{app_id}` should be replaced with your app’s unique ID (how to find it is explained below).
* This URL launches the app without directing to a specific page.
* If the app is **not installed**, the user will be redirected to either the **Google Play Store or Apple App Store** depending on their device.

***

## ✅ Adding a Target URL to the Deep Link

To launch the app and open a specific page, you can append the `url` parameter.

```
https://www.swing2app.com/swapi/openAppWithUrl?appId={app_id}&url=https://m.naver.com
```

### ℹ️ Note:

* The `url` parameter must be **URL-encoded**.
* Example:\
  Here is how the URL should look after encoding:

```
✅ Before encoding:
https://google.com

✅ After encoding:
https%3A%2F%2Fgoogle.com
```

* You can encode the URL using tools like `encodeURIComponent()` in JavaScript or any online URL encoder.

***

## ✅ POST Method Support

Deep links can be invoked via both **GET** and **POST** methods.\
This is useful when you want to avoid exposing parameters in the URL or need more secure communication.

***

## ✅ How to Find Your App ID (appId)

Only users who have purchased a subscription (paid apps) can access the appId.

### Navigation Path:

```
App Management > Service Management > App Operations > Advanced App Management > API-KEY Management
```

* On this page, you’ll find the `appId` and other API credentials.
* Free users or unpaid apps will not have access to the appId and cannot use the deep link feature.

***

## ✅ Example Deep Links

### App Launch Only (Redirects to store if not installed)

```
https://www.swing2app.com/swapi/openAppWithUrl?appId=275a02bc-9a02-4f9e-b54c-077d056e2cb1
```

### App Launch + Open Specific Page

```
https://www.swing2app.com/swapi/openAppWithUrl?appId=275a02bc-9a02-4f9e-b54c-077d056e2cb1&url=https%3A%2F%2Fm.naver.com
```

***

## ✅ Important Notes

* If the app is not installed, users will be redirected to the appropriate app store.
* Make sure the app is updated to the **latest version** to ensure the deep link functions properly.
* Push-only apps support limited features and may not fully support in-app navigation using WebViews.

***

## 📌 Conclusion

With Swing2App’s deep link support, even Push-Only Apps can implement powerful marketing features such as app launches, in-app redirection, and app store navigation.
