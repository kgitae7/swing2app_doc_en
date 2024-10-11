# Sending a push notification By API

<mark style="color:blue;">Using the push API to send Swing2App push notifications.</mark>

Swing2App provides the following method to send push messages sent from the dashboard in the form of APIs.

In the case of API use not agreed in advance and indiscriminate mass shipment, the use may be restricted.

This API is available to users of paid apps.

* API Specification

## API for sending push notification to Swing2App application

<mark style="color:green;">`POST`</mark> `https://www.swing2app.com/swapi/push_api_send_message`

<mark style="color:orange;">\*\*\* App ID and API KEY that need to be issued can be issued upon request to the customer center. \*\*</mark>

#### Request Body

| Name                                                 | Type   | Description                                                                                                                                                                                                                                |
| ---------------------------------------------------- | ------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| app\_id<mark style="color:red;">\*</mark>            |        | APP\_ID provided by Swing2App                                                                                                                                                                                                              |
| app\_api\_key<mark style="color:red;">\*</mark>      | String | API KEY provided by Swing2App                                                                                                                                                                                                              |
| send\_target\_list<mark style="color:red;">\*</mark> | String | <p>Send destination type setting items When sending to indiviUser ID to send to user_id in single dispatch When sending multiple messages, separate them with “,”<br>Ex:) user_id1,user_id2 Enter -1<br>[When sending all ]<br>Ex:) -1</p> |
| send\_type<mark style="color:red;">\*</mark>         | String | Enter the send type. Enter "push" in case of push delivery                                                                                                                                                                                 |
| message\_title<mark style="color:red;">\*</mark>     | String | message title                                                                                                                                                                                                                              |
| message\_content<mark style="color:red;">\*</mark>   | String | message content                                                                                                                                                                                                                            |
| message\_image\_url                                  | String | image url (Optional)                                                                                                                                                                                                                       |
| message\_link\_url                                   | String | link url (Optional)                                                                                                                                                                                                                        |

{% tabs %}
{% tab title="200: OK " %}
```javascript
{
    // Response
    result : true, // message id 
    userCount : 3 , // sent user count
    remainSmsCount 0, 
    isPaymentSms : F
}
```
{% endtab %}
{% endtabs %}

* Code example

{% tabs %}
{% tab title="Javascript-jQuery" %}
```javascript
var form = new FormData();
form.append("app_id", "app_id");
form.append("app_api_key", "api_key");
form.append("send_target_list", "test");
form.append("send_type", "push");
form.append("message_title", "title");
form.append("message_content", "content");
form.append("message_image_url", "https://www.swing2app.com/assets/images/logo.png");
form.append("message_link_url", "https://www.swing2app.com/");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_api_send_message",
  "method": "POST",
  "timeout": 0,
  "processData": false,
  "mimeType": "multipart/form-data",
  "contentType": false,
  "data": form
};

$.ajax(settings).done(function (response) {
  console.log(response);
});
```
{% endtab %}

{% tab title="Java" %}
```java
Unirest.setTimeouts(0, 0);
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_api_send_message")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("app_api_key", "api_key")
  .field("send_target_list", "test")
  .field("send_type", "push")
  .field("message_title", "title")
  .field("message_content", "content")
  .field("message_image_url", "https://www.swing2app.com/assets/images/logo.png")
  .field("message_link_url", "https://www.swing2app.com/")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_api_send_message',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','app_api_key' => 'api_key','send_target_list' => 'test','send_type' => 'push','message_title' => 'title','message_content' => 'content','message_image_url' => 'https://www.swing2app.com/assets/images/logo.png','message_link_url' => 'https://www.swing2app.com/'),
));

$response = curl_exec($curl);

curl_close($curl);
echo $response;

```
{% endtab %}

{% tab title="ETC" %}
Refer to the Postman link below for examples of usage for each language.

[https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b79b93a1-9f46-4d1c-a961-33afa5bfde3f](https://documenter.getpostman.com/view/14364369/2s83zdxSKf#b79b93a1-9f46-4d1c-a961-33afa5bfde3f)
{% endtab %}
{% endtabs %}

<mark style="color:blue;">\[JavaScript Implementation Example – Send All]</mark>

```javascript
var apiKey = "test_api_key";
var appId = "test_app_id";
var sendTargetList = '-1';
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_api_send_message",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_type : 'push' ,
        message_title:'title',
        message_content:'content',
        message_image_url: 'https://www.swing2app.com/assets/images/logo.png',
        message_link_url: 'https://www.swing2app.com/',
        app_api_key : apiKey
    },
    success: function (model) {
        console.log("success");

    }
});
```

<mark style="color:blue;">\[JavaScript Implementation Example – Individual Push notification]</mark>

```javascript
var apiKey = "test_api_key";
var appId = "test_app_id";
var sendTargetList = 'user_id';
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_api_send_message",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_type : 'push' ,
        message_title:'title',
        message_content:'message',
        message_image_url: 'https://www.swing2app.com/assets/images/logo.png',
        message_link_url: 'https://www.swing2app.com/',
        app_api_key : apiKey
    },
    success: function (model) {
        console.log("success");

    }
});
```
