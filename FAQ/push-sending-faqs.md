# Push sending FAQs

<details>

<summary>Can push-notification be sent from all apps created by Swing2App?</summary>

﻿Among the Swing2App prototypes, the webview app created as "webview only" cannot use the push notification function. All apps other than webview apps - General prototype apps and push-only apps can use push-notification.

</details>

<details>

<summary>Is there a limit to send push notifications to members?</summary>

You can send Push-notifications an unlimited number of times and to an unlimited number of members.

</details>

<details>

<summary>Is the push notification feature available for free?</summary>

﻿Yes, the push notification feature is available for free. You can also send it from the free version of the app.

</details>

<details>

<summary>Can I send push notification to all users who have installed the app?</summary>

Yes, push notifications will be sent to all users who have installed the app. In a regular prototype app – even to non-registered users (guests) as long as the app is installed, it will be sent.

But for the push app, the push notification will be sent in one go to all users who have installed the app.

</details>

<details>

<summary>Can I select members when sending pushes?</summary>

﻿For the General prototype apps, push notifications can be sent by selecting members. You can select any user, or group to send the push. However, the push-only app cannot select members, and can only send notifications to all members.

</details>

<details>

<summary>Can I send a push notification on any date or time zone?</summary>

﻿With help of Push Reservation settings, you can send push notifications based on the date and time zone of a specific region. You can set push notifications' shipping date, shipping day, shipping time, repeat cycle, etc.

</details>

<details>

<summary>When sending a push, is it possible to apply it to go to a web link or a specific page in the app?</summary>

Yes, you can. You can select the \[Link Wizard] button from the Send Push menu to choose which page or menu to go to. \*Push-only apps cannot use the link wizard. The app can be applied by directly entering the web link address (URL) in the link registration field.

﻿

</details>

<details>

<summary>[Push-only app] Can I not select a member when sending a push?</summary>

When sending a push from the push app, you cannot select a member, only send the entire service. The push-only app is an app created by applying the website (homepage) link to the app as it is, so there are no members signing up for the app. Therefore, since the app cannot recognize the member, the member cannot be selected, and only the entire shipment is possible. And all are marked as 'guests'.

</details>

<details>

<summary>Can I link Swing2App push through [Push-only App] member linkage? (Push API integration)</summary>

﻿Yes you can. It can only be provided to paid app users, and if requested, we will send you a push API integration guide. You can set it up and use it yourself. When the member is linked, the registered member in the app operation-member inquiry is linked. In addition, push sending can be sent only to the members who want to send it. If you can't set it yourself, you can ask us to do the work. Development costs are incurred when the work is commissioned. If you need this feature, please contact us by email. We're here to help you with the instructions. \*E-mail Address:help@swing2app.co.kr \*It cannot be provided in the free app, and is only available to paid app users.

﻿

</details>

<details>

<summary>[Push-only app] push history – Why does "number of sending members" always appear in the shipping history only 1 or 2 people?</summary>

The push-only app is an app created by applying the website (homepage) link to the app as it is, so there are no members signing up in the app. Therefore, since the app cannot recognize members, only the customer is identified in the member view, and there is no number of app members itself. Since the push sending history is also not recognized, the number of sending members is automatically set to one. If you appear to be 2 people, if you have registered a test device, you will be added and shown as 2 people. Therefore, for push app users, the number of sending members is meaningless.

</details>

<details>

<summary>[Push-only app] When sending push, is the "Link Wizard" function not available?</summary>

Yes, the push app is an app composed of websites, and there is no menu linked to the app, so you cannot use the link wizard. You can send by entering only the web link address (URL) in the \[Link registration] field. This feature is only available for regular prototyped apps.

</details>

<details>

<summary>[Push-only app] When sending a push, is the "Show push message after checking notification" function not available?</summary>

This feature is also only available in apps built as regular prototypes. It cannot be used in apps created with push-only apps.

</details>

<details>

<summary>What is the difference between the "number of sending members" and "number of sending devices" in the push history?</summary>

\-Number of members sent: The number of members whose push was sent **\*The number of members who have signed up for membership, and guests are not counted.** **\*Push app has no members, so it cannot be counted as 1 or 2 -Number of sending devices**: The actual number of messages sent to mobile phone devices \*You can check how many users the push was actually sent to. Therefore, you can check how many people the push was sent to by the number of sending devices.

</details>

<details>

<summary>The actual number of app members is much higher, but the number of push-sending devices is very insufficient. (If there are fewer shipping devices than the number of members)</summary>

In this case, it's because **app users have not been able to receive push notifications.** If you disable receiving push notifications, the pushes sent to your phone will be counted less than the number of members. If you install the app but turn off push notifications, the actual tally sent will be small. And there may be cases where you deleted the app, and there may be cases where the push is not sent because the app has not been used for a long time.

</details>

<details>

<summary>There are far more push-sending devices than the actual number of app members. (When there are more sending devices than members)</summary>

In this case, it is **because there are more customers who have not signed up than members who have signed up for the app.** In other words, in the Swing to App, customers who have not registered as members are not counted as members, and customers are counted as one person unconditionally. If 1,000 people use the actual app / 500 people sign up, the number of members sent to 501 is counted. (Guests are counted as 1 member) Therefore, if there are more pushes sent to mobile phones than the number of members, it is because there are more customers using the app than registered users. **In particular, those who have created the app with the push version are displayed as 1 or 2 members. The number of sending devices can be checked by the push count sent to the actual mobile phone.**

</details>

<details>

<summary>Are pushes only sent from apps?</summary>

Yes, the push is only sent when the app is installed on your phone. \*Virtual machine, app will not be sent in preview state. Therefore, install or download the created app on your phone and proceed with the push send. Send a push while the app is closed. (Available on Android phones, iPhone can only be checked if released on the App Store)

</details>

<details>

<summary>Can I try a push test? I want to make the push come only for me (admin), what can I do?</summary>

**1.How to test a general prototype app push**

Please sign up in the app first. You can change the level of a member to an administrator, or you don't have to change it. (Regardless of push sending) Send push – Select the recipient in the default settings. Select and add the username you want to test to send pushes only to specific selected members. You can also upgrade this feature a bit further and later select specific groups to send pushes.

**2.How to test push-only app push**

The push-only app can be sent out from the test device registration management. Please refer to the manual below. \[Manage push devices – check test push delivery]\\

</details>

<details>

<summary>Push history: Sent completed, app push There is also a push in the push notification window, but the notification does not come.</summary>

Push must be sent while the app is closed so that you can check it as a notification. If you send a push while the app is running, it will be displayed in the form of a pop-up window. Also, make sure that the actual app is installed on your phone. (Preview, Virtual Machine X) Therefore, **in order to receive push notifications through normal root, please send them while the app is closed.**

</details>

<details>

<summary>I entered the contents in Send push, but the push cannot be sent.</summary>

Make sure you don't use emojis in the subject line and message fields. If you put a mobile emoticon used on your phone, the message is not recognized and the push cannot be sent. Only symbols (special characters) used on a PC can be entered. Therefore, please be careful with the use of emoticons.

</details>

<details>

<summary>If I don't use the app for a long time, won't the user receive push notifications?</summary>

Yes, if you do not use the app for a long time, the app activation status may change → to inactive, and push notifications may not be sent. The reference time is different for each platform and device. The period varies from at least 7 days of inactivity to \~ a month. Simply launch the app again and future push notifications will be sent normally.

</details>

<details>

<summary>If a user has turned off push notifications, can't the app administrator (developer) get notifications again?</summary>

Yes, this part is not something that developers can enforce. Whether to use a feature or not is up to the app user, so developers cannot force it to be used.

</details>
