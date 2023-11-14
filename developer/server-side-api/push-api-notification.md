# Sending a push notification By API

<mark style="color:blue;">Using the push API to send Swing2App push notifications.</mark>

Swing2App provides the following method to send push messages sent from the dashboard in the form of APIs.

In the case of API use not agreed in advance and indiscriminate mass shipment, the use may be restricted.

This API is available to users of paid apps.

* API Specification

{% swagger method="post" path="" baseUrl="https://www.swing2app.com/swapi/push_send" summary="API for sending push notification to Swing2App application" %}
{% swagger-description %}
<mark style="color:orange;"><mark style="color:orange;">\*\*\*<mark style="color:orange;"></mark> <mark style="color:orange;"></mark><mark style="color:orange;">App ID and API KEY that need to be issued can be issued upon request to the customer center.</mark> <mark style="color:orange;"></mark><mark style="color:orange;"><mark style="color:orange;">\*\*<mark style="color:orange;"></mark>
{% endswagger-description %}

{% swagger-parameter in="body" name="app_id" required="true" type="" %}
APP\_ID provided by Swing2App
{% endswagger-parameter %}

{% swagger-parameter in="body" name="api_user" required="true" type="" %}
Swing2app user account (email address)
{% endswagger-parameter %}

{% swagger-parameter in="body" name="api_key" required="true" %}
API KEY provided by Swing2App
{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_target_list" required="true" %}
Send destination type setting items When sending to indiviUser ID to send to user\_id in single dispatch When sending multiple messages, separate them with “,” \
Ex:) user\_id1,user\_id2 Enter -1 \
\[When sending all ]\
Ex:) -1
{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_target_type_list" required="true" %}
Send destination type setting items When sending to individual users, input MEMBER as many as the number, separate them with ‘,’ If sending to all. \
enter 'ALL\_TARGET'\
\[When sending to 2 specific users] Ex:) MEMBER, MEMBER \
\[When sending to all] \
Ex:) ALL\_TARGET\

{% endswagger-parameter %}

{% swagger-parameter in="body" name="send_type" required="true" %}
Enter the send type. Enter "push" in case of push delivery
{% endswagger-parameter %}

{% swagger-parameter in="body" name="message_json" required="true" %}
\* Enter the following variables according to the JSON format string\


messageTitle: Title,

messageContent: Content

messageLinkUrl: Link Address

messageImageUrl: Image Url

\*Can be omitted if there is no link address and image address\
\
Ex:)

\[In case of sending title, content, link, image]

{“messageTitle" : "title" , "messageContent" : "content" , "messageLinkUrl" : "https://www.swing2app.com" , "messageImageUrl":"https://www.swing2app.com/abc.png"}\


\[In case of sending only the title, content, and image]

{“messageTitle" : "title" , "messageContent" : "content" , "messageImageUrl":"http://www.swing2app.com/abc.png"}\


\[In case of sending only the title, content]

{“messageTitle" : "title" , "messageContent" : "content" }
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    // Response
    result : true, // message id 
    userCount : 3 , // sent user count
    remainSmsCount 0, 
    isPaymentSms : F
}
```
{% endswagger-response %}
{% endswagger %}

* Code example

{% tabs %}
{% tab title="Javascript-jQuery" %}
```javascript
var form = new FormData();
form.append("app_id", "app_id");
form.append("api_user", "UserAccount");
form.append("api_key", "api_key");
form.append("send_target_list", "test");
form.append("send_target_type_list", "MEMBER");
form.append("send_type", "push");
form.append("message_json", "{\"messageTitle\" : \"push title\" , \"messageContent\" : \"push content\" , \"messageLinkUrl\" : \"http://www.swing2app.com\" , \"messageImageUrl\":\"http://www.swing2app.com/abc.png\"}");

var settings = {
  "url": "https://www.swing2app.com/swapi/push_send",
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
HttpResponse<String> response = Unirest.post("https://www.swing2app.com/swapi/push_send")
  .multiPartContent()
  .field("app_id", "app_id")
  .field("api_user", "UserAccount")
  .field("api_key", "api_key")
  .field("send_target_list", "test")
  .field("send_target_type_list", "MEMBER")
  .field("send_type", "push")
  .field("message_json", "{\"messageTitle\" : \"push title\" , \"messageContent\" : \"push content\" , \"messageLinkUrl\" : \"http://m.naver.com\" , \"messageImageUrl\":\"http://www.swing2app.com/abc.png\"}")
  .asString();

```
{% endtab %}

{% tab title="Php" %}
```php
<?php

$curl = curl_init();

curl_setopt_array($curl, array(
  CURLOPT_URL => 'https://www.swing2app.com/swapi/push_send',
  CURLOPT_RETURNTRANSFER => true,
  CURLOPT_ENCODING => '',
  CURLOPT_MAXREDIRS => 10,
  CURLOPT_TIMEOUT => 0,
  CURLOPT_FOLLOWLOCATION => true,
  CURLOPT_HTTP_VERSION => CURL_HTTP_VERSION_1_1,
  CURLOPT_CUSTOMREQUEST => 'POST',
  CURLOPT_POSTFIELDS => array('app_id' => 'app_id','api_user' => 'UserAccount','api_key' => 'api_key','send_target_list' => 'test','send_target_type_list' => 'MEMBER','send_type' => 'push','message_json' => '{"messageTitle" : "push title" , "messageContent" : "push content" , "messageLinkUrl" : "http://www.swing2app.com" , "messageImageUrl":"http://www.swing2app.com/abc.png"}'),
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
var apiUserId = "help@swing2app.com";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "push title" , "messageContent" : "push content" , 
"messageLinkUrl" : "https://www.swing2app.com" , "messageImageUrl" : "https://www.swing2app.com/abc.png" }';
var sendTargetList = '-1';
var sendTargetTypeList = "ALL_TARGET";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_send",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_json : messageJson,
        api_user : apiUserId,
        api_key : apiKey
    },
    success: function (rModel) {
        console.log("success");

    }
});
```

<mark style="color:blue;">\[JavaScript Implementation Example – Individual Push notification]</mark>

```javascript
var apiUserId = "help@swing2app.co.kr";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "push title" , "messageContent" : "push content"}';
var sendTargetList = 'user_id';
var sendTargetTypeList = "MEMBER";
$.ajax({
    url: "https://www.swing2app.co.kr/swapi/push_send",
    type: "post",
    dataType: "json",
    data : {
        app_id : appId,
        send_target_list : sendTargetList,
        send_target_type_list : sendTargetTypeList,
        send_type : 'push' ,
        message_json : messageJson,
        api_user : apiUserId,
        api_key : apiKey
    },
    success: function (rModel) {
        console.log("success");

    }
});
```
