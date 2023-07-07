---
description: >-
  A guide to utilizing user integration on Wix websites through simple code
  insertion
---

# Wix Website User Integration Guide

To enable interaction between your own Wix website and the Swing2App app when users log in, we will guide you through the necessary steps.

Once the user integration is completed, you will be able to view the website members on the Swing2App console and send push notifications to individual members of the website.

## 1. User Integration Guide

### 1.1 Navigate to the Wix Dashboard

<figure><img src="../../../.gitbook/assets/image (14).png" alt=""><figcaption><p>Wix Console</p></figcaption></figure>

### 1.2 Insert an Embed HTML element on the home screen

<figure><img src="../../../.gitbook/assets/image (18).png" alt=""><figcaption><p>Wix Console - HTML Element</p></figcaption></figure>

### 1.3 Insert the source code into the HTML element

<figure><img src="../../../.gitbook/assets/image (16).png" alt=""><figcaption><p>Wix Console - Source Code</p></figcaption></figure>

(1) Insert the following code in the designated area

{% code title="HTML 요소 코드" lineNumbers="true" %}
```html
<script src="https://pcdn2.swing2app.co.kr/swing_public_src/v3/2022_06_17_001/js/swing_app_on_web.js"></script>

<script>
 window.onmessage = (event) => {
    if (event.data) {
       let receivedData = event.data;
      	console.log('login account : ' + receivedData.id + ',' + receivedData.name);
      swingWebViewPlugin.app.login.doAppLogin(receivedData.id,receivedData.name);
    }
  };
  
</script>

```
{% endcode %}

### 1.5 Assign an ID to the HTML element

<figure><img src="../../../.gitbook/assets/image (17).png" alt=""><figcaption><p>Wix Console - Assigning ID</p></figcaption></figure>

(1) Assigning an ID to the created HTML element&#x20;

Please make sure to assign the following ID to the element

ID value: swing2appLogin



### 1.6 Inserting Page Code (Final Step)

<figure><img src="../../../.gitbook/assets/image (5).png" alt=""><figcaption><p>Wix Console - Source Code</p></figcaption></figure>

(1) Click on the Home screen, then insert the following code in the (2) source area of item&#x20;

If you have inserted the code below, all the steps are completed. After saving and deploying, it should function properly.

{% code lineNumbers="true" %}
```javascript
import wixUsers from 'wix-users';
import { currentMember } from 'wix-members-frontend';
$w.onReady(function () {
    if (wixUsers.currentUser.loggedIn) {
        currentMember.getMember('FULL')
            .then((member) => {
                const id = member._id;
                const fullName = `${member.contactDetails.firstName} ${member.contactDetails.lastName}`;
                $w("#swing2appLogin").postMessage({
                    id : id ,
                    name : fullName
                });
                return member;
            })
            .catch((error) => {
                console.error(error);
            });
    }
    else{
        console.log('guest login');
        $w("#swing2appLogin").postMessage({
            id : null ,
            name : null
        });
    }
});

```
{% endcode %}

### 1.7 Verification of User Integration

If you have completed all the integration steps, access the Swing2App console after running the website on the app.

Go to Push & Members -> Member Inquiry screen to verify if the website members are displayed.

If they are visible, the integration is successfully completed.

<figure><img src="../../../.gitbook/assets/image (12).png" alt=""><figcaption><p>Swing2App Console</p></figcaption></figure>

