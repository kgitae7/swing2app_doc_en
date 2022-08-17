# App Creation FAQ

<details>

<summary>Design Theme – Can a prototype only select one UI style?</summary>

Yes yes.

Design Themes Offered by Swing – Prototypes can only be used in one style of choice.

This prevents you from using a combination of styles.

Sometimes there's a UI style that combines slides + towers.

If you use this mix of styles, this is an app that has been developed separately through customization. Various styles can be applied through customization.

</details>

<details>

<summary>How many characters can I register for an app name?</summary>

When building an app, there is no specific limit to the number of characters in the name.

However, if the number of characters that appear when you install the app on your phone is too long, the name will be truncated and displayed.

**App/app titles vary slightly depending on the phone model, but can be between 9 and 11 characters long.**

If the app name exceeds 10 characters, please make the app name less than 10 characters when you create the app, as the app name will be truncated and visible when you install the app on your phone.

</details>

<details>

<summary>I want to put an image full on the app home screen, but is there an optimized size?</summary>

Images that go into the app don't have the recommended size.

**Because the standard sizes of mobile phones are all different, it is not possible to know the same image size for all models.**

In the case of images, it is a form of scaling the vertical to fit the horizontal length of the phone's LCD screen.

**Please adjust the recommended size to 1080px wide and 1980-2200px vertical based on mobile screen resolution.**

**★To fit the horizontal size, the vertical length is adjusted according to the screen of the phone.**

**So depending on what prototype you applied to the portrait and the type of phone you have, it may be a little longer or shorter in length.**

Because it is fixed horizontally and vertically changes depending on the mobile environment, not all phones can show the same screen.

\* Please note that since the size varies by phone, the latest models may look a little shorter in length, except in the case of tablets.

</details>

<details>

<summary>I can't delete the app.</summary>

Uninstalling an app is only possible if you have at least 2 apps.

If there is only 1 app, it will not be uninstalled. To 'Uninstall' you can uninstall an app by going to the My Menu – <mark style="color:blue;"></mark> [<mark style="color:blue;">\[Manage Apps\]</mark>](https://www.swing2app.com/view/app\_stat) <mark style="color:blue;"></mark> page.

\*Please note that paid users do not want the app to be uninstalled until the end of the paid period.

</details>

<details>

<summary>The icon image is cropped from the phone and visible.</summary>

When creating an icon image, you need to put a background color and a center image in the background.

Make sure that the center image is not too large.

\*Important\* Background color is not transparent, but must be colored.

When installed on your phone, the app icon will be rounded to make it visible.

\- Reference images

![](../.gitbook/assets/영문아이콘\_안드로이드버전1.png)

Therefore, if you work with the center image too large, it will be rounded and all the corners will be cut off.

Please design with that in mind.

The icon creation guide is also available in the manual, so please check out the detailed manual.&#x20;

<mark style="color:blue;">****</mark>[<mark style="color:blue;">**\[Go to the app icon image creation guide\]**</mark>](../manual/maual/appbasic/appicon.md)<mark style="color:blue;">****</mark>

</details>

<details>

<summary>What is the standby screen image that registers for basic information?</summary>

The standby screen is the screen that is displayed during the loading time before the app is launched.

For each type of mobile phone, the waiting screen is displayed in different Internet environments and the time it takes to see it varies.

It should look as short as 1 to 3 seconds.

Due to the mobile app policy, the standby screen is a mandatory item, so when you create a swing-to-app app, you must also register an image to be displayed on the standby screen.

Guidelines on how to create a standby screen can be found in detail in the manual.&#x20;

**☞** [<mark style="color:blue;">**See how to create a standby screen image**</mark>](../manual/maual/appbasic/apploading.md)<mark style="color:blue;">****</mark>

</details>

<details>

<summary>I worked on the standby screen image to the recommended size, but the image was cropped on my phone and I can see it.</summary>

**The recommended size for standby screen images is the official recommended size for all models because the LCD screen is different for each mobile phone model. (2282\*2282)**

However, since the liquid crystals are square, tablet screens, etc. are all different sizes, when you create an image, you need to make sure that the main image does not fill up the wallpaper.

Therefore, when working with standby screens, you should check and produce the standby screen guideline manual provided by the swing.

Reference Image)

[![](https://s3.ap-northeast-2.amazonaws.com/swing2bucket/resource/image/help/20dcb89afcf17106ac72ea410440d487.png?type=w966)](http://blog.naver.com/PostView.nhn?blogId=swing2app\&logNo=221214959655\&parentCategoryNo=\&categoryNo=49\&viewDate=\&isShowPopularPosts=false\&from=postView)

In the attached image, blue becomes the wallpaper. (Image that can be cropped)

You just need to work on making sure that all the important image cuts are in the gray space. (Image shown on the actual screen)

Usually, users work with the image to a large blue area, so the image is cropped and visible depending on the phone type.

Therefore, please make a standby screen by checking the guidelines - how to make it.

**☞** [<mark style="color:blue;">**See how to create a standby screen image**</mark>](../manual/maual/appbasic/apploading.md)<mark style="color:blue;">****</mark>

</details>

<details>

<summary>Are there any restrictions on app updates?</summary>

Yes, you can use it without restrictions.

After you create the app, modify and update it, you are free to use it.

</details>

<details>

<summary>Where do I make modifications (updates) after app creation?</summary>

The Swing-to-App does not have an app modification (update) task page.

When making corrections, please do the same by going to the app creation page.

You can overwrite existing apps and keep updating.

After saving, press the Update button to re-create the new version.

</details>
