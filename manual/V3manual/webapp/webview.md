# How to create a webview app

**App Authoring V3 Version – Webview App Creation Manual**

****

> **What is a webview app?**
>
> **The webview app is a web app creation platform created by hanging a link to a mobile web URL such as a homepage.**
>
> Because the website works with the app as it is, you can create the same app as the web.

![](broken-reference)

****

## **Start.** Get started with the App Creation Wizard

**​**

**When you first create an app in a swing-to-app or start building additional apps, the App Authoring Wizard splash screen (a pop-up window) pops up first.**

**Here, you choose what type of app you want to build, then enter the basic information and you'll be taken to the authoring maker.**

**​**

<mark style="color:blue;">**1.Form of Creation: Select a web app based on the website**</mark>

![](broken-reference)

For a webview app, please select the 2nd method of creation, "Web App Based on Website".

This is a style that creates a website by applying it to the app as it is.

Select the \[Next] button.

**​**

**​**

<mark style="color:blue;">**2.Enter web app basic information**</mark>

The next step is to enter the basic information, where you enter the basics needed to build a web app.

![](https://wp.swing2app.co.kr/wp-content/uploads/2022/06/%EC%9B%B9%EB%B7%B0%EC%95%B11.png)

**1) Enter the website address (URL).**

This is the site link you want to apply to your app, and be sure to include a hyperlink Error! Hyperlink reference not valid..

After entering the link address, a single click on the mouse cursor in the empty space will be reflected.

You can check if the applied site is popping up well with the virtual machine (preview) screen on the right.

**2) Check whether the push function is enabled**

Push is a feature that allows users who have installed an app to send notifications, announcements, and promotional reminders from the app.

Since we are going to create a webview app with no functionality, please check the push function as 'Unused'.

Add-ons can be modified again in the App Creation Maker, so you can check for unused here, and change them again later!

Select the \[Next] button.



<mark style="color:blue;">**3.App name, icon, standby screen image registration**</mark>

![](broken-reference)

The final step is to **register the app name input, app icon, and standby image.**

App names, icons, and standby screen images can all be modified again in the creation maker.

If the image isn't ready yet, you can just enter the app name and press the Done button.

Icons and images that will fit on the standby screen can be reapplied in the production maker.

​

<mark style="color:green;">**–> Icon, how to register standby screen image**</mark>

![](broken-reference)

On the app icon, the standby screen, select the \[Register] button and the file attachment window will open.

You can upload an image here and apply it.

**- Icon image size: 1024px\*1024px**

**-Standby screen image size: 2282px\*2282px**

When the registration is complete, select the \[Done] button.

When the App Authoring Wizard registration is complete, the App Authoring Maker screen opens.

If you look at the app creation process on the left, you can see the steps on the STEP1 Basic Information, STEP2 Design, and STEP Page.

Step by step, enter your content and you're done.

<mark style="color:red;">**\*When the STEP progress reaches 100%, all step inputs are complete.**</mark>

**​**

## **STEP1** Basic Information

![](broken-reference)

**STEP1 The contents in the basic information have already been registered in the App Creation Wizard except for the app ID.**

If you modify the app name, you can re-enter it.

If you modify the app icon, standby screen image, or register a new one, you can complete the registration on that screen.

1\) Enter App ID <mark style="color:red;">**\*The app ID is the unique identifier of the app and cannot be changed after setting.**</mark>

2\) Enter the app name

3\) App icon image **(1024px\*1024px)**

4\) App standby image registration **(2282px\*2282px)**

5\) Select \[Save] button

**​**

**\*App icon image, standby screen image Please create an image according to the size listed on the screen first, and then register.**

**For icons and standby screens, please first look at the Production Guidelines Manual and create them!**

**​**<mark style="color:blue;">**Go to the icon image creation guide**</mark>

<mark style="color:blue;">**Go to the standby screen image creation guide**</mark>



**\*App name, icon, and standby screen images, except for the app ID, can be modified and updated without limitation.**

**When modifying the app basic information, you need to press the \[Update App] button to update to the new version.**

<mark style="color:red;">**\*Information**</mark>

If you modify the STEP1 Basic Information menu again after the app is created, you will need to update the app again before the app will reflect the changes.

For example, if you changed the name of your app, save → after the change → press the Update App button to recreate it as a new version.

If it's released on the App Store or Play Store, you'll need to resubmit updates to that Store as an updated version of the app.



## STEP2 Design

![](broken-reference)

STEP2 Design Phase – Set the prototype, basic options, and advanced options.

The prototype has already been selected in the App Creation Wizard, so you can move on.

In Webview – If you modify it as a push prototype, you can change it and update it.

1.Select Prototype: It is selected as 'WebView Only'.

2\. Basic Options

1\) Pull and refresh: This is a function that refreshes when the screen is pulled and released.

2\)Placement of the top button at the bottom of the screen: When the screen is moved down by scrolling, selecting the top button is the function to move to the top of the screen.

<mark style="color:red;">**\*If there is already a top button in the website to be applied to the app, we recommend that you check it as 'Unused' and if not, check it as 'Enabled'.**</mark>

​

3.Advanced options

You can check whether the system font is being used.

<mark style="color:red;">**\*The system font is the font set on the phone (text size, etc.), and the default setting in the options is checked in "Yes".**</mark>

**For example, if you check the system font usage as an example:**

**If you increase the text size on your phone significantly→ the text displayed in the app will also appear at the text size set on the phone.**

**If you don't use the system font, it will be automatically set to the default in-app font, so it will look independent of your phone's settings.**

Therefore, except for special reasons, <mark style="color:red;">**we recommend that you use it according to the default settings (use system fonts: yes).**</mark>

​

4\)Select the Save button

​

<mark style="color:red;">**\*Information**</mark>

If you modify the STEP2 design menu again after the app is created, you will need to update the app again before the app can reflect the changes.

For example, if you changed the toolbar background color, save → after the change → press the Update App button to recreate the new version.

If it's released on the App Store or Play Store, you'll need to resubmit updates to that Store as an updated version of the app.



## STEP3 Page

![](broken-reference)

The STEP3 page step will enter a link to the website that applies to your app, which you have already registered in the App Creation Wizard.

If you want to edit the site address, please re-enter it in the appropriate step. If you don't have anything to modify, just save it.

1\)Enter your website address

2\) Address setting: Choose whether to set the first run address

**\*First Run Address Line In addition to the website associated with the app, you can install the app and apply a separate web page that is only visible the first time.**

Check 'No' if you don't use it, or 'Yes' if you don't use it. Please include Error! Hyperlink reference not valid. when entering your site address.

3\)Select the Save button



<mark style="color:red;">**\*Information**</mark>

The STEP3 page menu is automatically reflected in the app by simply modifying and saving it. You don't need to update the app (recreate the app)



## **STEP4 Complete App Creation**

![](broken-reference)

All steps have been entered. You can build apps.

1\)Select the Create App button

2\) Select the \[Create] button in the App Creation pop-up window.'

The Show Updates option doesn't affect your production by choosing anything. **Because it's a webview app, the update window doesn't appear in the app.**

So you just have to make it as checked.

\*WebView App Update If your app is released on the Play Store/App Store, etc., you will need to upload a new version of the app to get the app updated through the Store.

If your app is for personal use that hasn't been released, you'll need to delete the existing app and reinstall it as an updated version.

![](https://wp.swing2app.co.kr/wp-content/uploads/2019/04/%EC%A4%84%EB%9D%BC%EC%9D%B8.png)

The webview app is built in less than 10 minutes.

The finished app can be viewed by using the official Swing-to-App app \[App Preview] or by downloading the e-mailed APK file from your Android phone.

**\*Webview and apps made with push can only be viewed on Android phones. \*I can't check my iPhone**

Creating an app is simple, so you can easily follow it by looking at the manual.

The production is free of charge at no extra charge.

​

## **STEP5** Download the app to your phone to confirm

**​**

\*Webview and apps made with push can only be viewed on Android phones. (I can't check my iPhone)

Swing2App Official App – Download the app created by \[App Preview] to check it out.

![](broken-reference)

**1) Download the official 'Swing to App' app from the Play Store. \*If the app is already installed, please update to the latest version.**

<mark style="color:blue;">**PlayStore launch link (URL)**</mark>

**​**

**2) After launching the app, select the \[App Preview] menu at the top of the → category and log in with your Swing2App website subscription account (ID, password).**

\*Easy Login User: If you used to log in with Easy Login when you signed up for Swing-to-App, please select the Naver, Google, and Facebook icons to log in.

\*Note: To log in, you must enter the account you signed up for in the http://www.swing2app.co.kr of the Swing-to-App homepage. http://www.swing2app.co.kr/

It's not an account signed up for in the official Swing-to-App app\~!

**​**

**3) Once you're done signing in, the app preview page will open, where you can see a list of apps you've created.**

**4) You can install the app on your phone by pressing the \[Download App] button.**

**\*The webview app is only available on Android phones. (iPhone not available)**

****

<mark style="color:green;">**▶ App launch: App preview- Download app**</mark>

![](broken-reference)

Please check the process of downloading the app from the app preview through the image that you are receiving.

**When installing the app, you may occasionally see a Google Play Protect blocking message, but you can ignore it, select Install, and proceed.**

In this way, you can install the webview app on your Android phone and test if it works properly.

If you don't have any issues, you can prepare for the launch of your store.

When you launch an App Store or Play Store app, you need to switch from the free version app to the paid version.

To switch to the paid version, you can purchase a Swing-to-App Paid App Pass.

When creating a webview app, push app, enter the website address, and then

On the virtual machine (preview screen), you will see a message that says 'Please check after installing the app on your mobile phone' or 'The connection has been refused'.

**If the security that prevents external connections within the website you connected to, that is, the prohibition of external sharing and embedding, is enabled, you will see the message.**

Therefore, when you link to a website that has this security setting, you will see a message that says Deny Connection on the web preview screen.

Even if you get these messages, **it doesn't mean you can't build an app.**

**You can check more accurately by simply checking with the app that the screen cannot be displayed on the web for security reasons.**

**Therefore, please save and \[Create App] and download it to the app to confirm.**

If you look at it as an app, you can see that the site works normally with the app.

If the app also refuses to connect, please contact the inquiry board.

**\*However, the URL for internal use and the site address used by the company's internal server cannot be connected and cannot be created as a web app.**



## Webview app creation instructions

![](https://wp.swing2app.co.kr/wp-content/uploads/2022/06/%EC%9B%B9%EB%B7%B05.png)

When creating a webview app or push app, after entering the website address, you can see that the virtual machine (preview screen) displays the message "Please check after installing the app on your mobile phone" or "Refused to connect".

**If the security that prevents external connections within the website you connected to, that is, the prohibition of external sharing and embedding, is enabled, you will see the message.**

Therefore, when you link to a website that has this security setting, you will see a message that says Deny Connection on the web preview screen.

Even if you get these messages, **it doesn't mean you can't build an app.**

**You can check more accurately by simply checking with the app that the screen cannot be displayed on the web for security reasons.**

**Therefore, please save and \[Create App] and download it to the app to confirm.**

If you look at it as an app, you can see that the site works normally with the app.

If the app also refuses to connect, please contact the inquiry board.

**\*However, the URL for internal use and the site address used by the company's internal server cannot be connected and cannot be created as a web app.**

​

​

## Precautions and Webview App Creation Q\&A

**​**

**Q.Is it true that the webview app is difficult to launch on the App Store and Play Store?**

**–PlayStore —**

WebView and PushVersion Apps (web apps that link to a website) are required to provide supporting documentation (advance notice documents) in accordance with Google's WebView policy.

In order to prove that the site you linked to the app belongs to you or the company (company), you will need to provide a notice document such as a business registration certificate or website domain registration confirmation.

When you submit your documents, you can also launch a webview app on the Play Store without any problems.

**–App Store–**

Web apps such as push apps and webview apps need to be vetted to know if they are released.

A web app doesn't mean it won't be released unconditionally. There are various policy reasons for Apple, so you'll need to get screening feedback to find out.

We will appeal as much as possible to help you launch the App Store, but please understand that we cannot judge whether or not your app is released\~!

Please note that even if the Store is rejected, the cost of the subscription and upload ticket will not be refunded for the app that has been registered on the App Store.

**– These web apps are difficult to release.**

\*Apps that connect to a PC version of a website other than the mobile web will be rejected. The website must be connected to the mobile web.

\*Web apps that have only promotional or marketing content on the web, that have no substantive content, or that have limited user engagement will be rejected.

\*Shopping mall sells digital products on the web, but web apps that do not use Apple's in-app payment module will be rejected. (Physical products not applicable)

\*In addition to the regular login, we provide simple and social login (Katok, Naver, etc.), but will be rejected if you do not have an Apple login.

If you provide external login and social login functionality, you must also provide Apple login functionality for release.

\* This includes all other cases where the content on the website is not in line with Apple's policies. (Prohibited content: sexual content, tobacco, drugs, excessive abusive language, etc.)

**Q. When creating a webview app, can I connect to any site to create it?**

One thing to be careful about when creating a webview app is that you shouldn't use sites from other third parties or well-known brands like you've created them!

You can only use the homepage that our company runs, the website you created (using the hosting company), etc.

There are many users who want to link their Naver blog or the next café with a webview or push.

These sites will error or will not function properly if you link them to the app.

\* These apps should not be released on the Play Store or the App Store. (Copyright will be rejected on the grounds of brand imitation)

And there's a site on the web that doesn't work with the app, i.e. prohibits embedding.

\*Naver, the following portal sites, and the sites provided by the portal (modoo, storefarm web, etc.), YouTube, social media sites (Instagram, KakaoTalk, Facebook), etc. are the representative sites that have been banned from embedding!

Therefore, you need to apply a homepage that can prove that you created it with domain registration information, and a website (homepage) that can be verified by a business registration certificate if it is created by the company.

**Q. Can the WebView app not send pushes?**

Yes, the webview app cannot send a push because it cannot use other functions of the app.

If you need to send a push, you need to create it as a push version app, not a webview app.

**Q. If it's difficult to make it yourself, but I pay for the development, can I do the above in the Swing-to-App app?**

If you ask us to produce it, we will do it all for you.

From designing icons and standby images, to creating apps and uploading them to the store.

\*You can check the production agency fee on the Swing to App Custom Package product page. <mark style="color:blue;">http://www.swing2app.co.kr/view/payment\_list\_by\_recommend\_custom</mark>

However, you will need to create your own Google developer account to upload to the Play Store and let us know your account.

The App Store requires that an Apple developer account be optional, but if you use your own account, you will need to create your own account and tell us about it.

Accounts are not created in the Swing-to-App app.

**Q. Can I switch from WebView to Push Version**&#x20;

Yes you can.

\*During the App Creation →STEP2 design step, please change the prototype to 'Push Only' and save and update the app again.

When updated to the new version, the prototype is changed and verifiable.

If your app has been released on the Play Store, App Store, etc., you can update it to the newly created version as well.

However, users who use the WebView Unlimited product should not be changed.

**Q. How do I change my website address after creating the WebView app?**

The same goes for changing the weblink address applied to your app.

**App Creation→ STEP3 Page Menu 1)Enter the URL Address in the Website Address field → 2)Select the Save button**

\*Modifying the web link address is automatically reflected in the app by simply pressing the Save button.

\*If you exit the app and relaunch it, it will be applied to the changed website.

However, users of WebView Unlimited paid apps will need to save and re-create the app. You will need to update to the new version to be reflected.

**Q. Will the WebView app change to a normal prototype?**

After being built as a webview-based (push, webview) prototype, → cannot be changed to a normal prototype (slides, tops, footers, drop-down lists, drop-down boxes).

\*If you need to change from a webview-based prototype to a different prototype, you'll need to create a new app.

**Q. Can I use a basic subscription and then change it to the WebView Unlimited plugin?**

Yes you can.

If you purchase unlimited plugins for Webmu after using the basic subscription, we will create an unlimited number of settings.

**\*Precautions**

1\) A new version of the app created with unlimited webviews requires you to update it back to the App Store and Play Store.

Since the existing subscription app and the WebViewUnlimited app are not compatible with each other, users will need to update to the new version so that users can receive the update.

2\) If you purchase and use the Swing Paid App Pass, and then pay for the WebView Unlimited plugin, there will be no split refund for the remaining period.

Therefore, please use the paid app subscription date and purchase unlimited tickets for WebView.

**Q. Does the WebView app reflect any modifications or updates made on the website directly in the app?**

Because your web app is a website-driven application, the screen you see on your website is reflected in the app as well.

Even if you don't have to do anything extra in the app, updates from the web are automatically reflected in the app as well.

**Q. Can the functions that work normally on the mobile web not be available in the app?**

If there's no problem on the web, the app won't have the problem either. However, technical errors can occur at any time.

So, if you have anything problematic while testing your app before launch, please leave it as an inquiry board.

We are here to help by identifying your symptoms.













​
