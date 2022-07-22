# Sending a push using the push API

<mark style="color:blue;">Send Swing2App push using push API</mark>

Swing2App provides the following to send push messages sent from the dashboard in the form of API.

The use of APIs in a manner not previously agreed upon and indiscriminate mass delivery may be restricted.

This API is provided to paid app users.

**1. API Specification**

| <mark style="color:blue;">API Address</mark> | https://api.swing2app.com/swapi/push\_send |
| -------------------------------------------- | ------------------------------------------ |
| <mark style="color:blue;">HTTP Method</mark> | Post                                       |

| Parameter Name                                            | Input Example                                                                                                                                                | Explanation                                                                                                                                                                                                                                                                   |
| --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <mark style="color:blue;">app\_id</mark>                  | kbe35b81a-5dc6-4cec-ad76-e7bcc3310642                                                                                                                        | \*App ID issued by Swing2App                                                                                                                                                                                                                                                  |
| <mark style="color:blue;">send\_target\_list</mark>       | targetUserId or -1                                                                                                                                           | <p>*User ID to send</p><p>User_id for single send</p><p>When sending multiple transmissions, separate them with “,” and enter</p><p>ex:) user_id1,user_id2</p><p>Enter -1 for all shipments</p><p>ex:) -1</p>                                                                 |
| <mark style="color:blue;">send\_target\_type\_list</mark> | MEMBER or ALL\_TARGET                                                                                                                                        | <p>* Enter MEMBER as many times as you want to send to individual users.</p><p>(Example: ‘MEMBER,MEMBER’),</p><p>For shipping to all, include ‘ALL_TARGET’.</p><p>(Example: ‘ALL_TARGET’),</p>                                                                                |
| <mark style="color:blue;">send\_type</mark>               | push                                                                                                                                                         | \*Enter ‘push’ because it is push sending                                                                                                                                                                                                                                     |
| <mark style="color:blue;">message\_json</mark>            | { “messageTitle” : “Content” , “messageContent” : “Content” , “messageLinkUrl” : “http://m.naver.com” , “messageImageUrl” : “http://swing2app.com/abc.png” } | <p>*Enter the following variable according to the JSON format string</p><p>messageTitle: Title,</p><p>messageContent: Content</p><p>messageLinkUrl: Link address</p><p>messageImageUrl: Image address</p><p>*Can be omitted if there is no link address and image address</p> |
| <mark style="color:blue;">api\_user</mark>                | help@swing2app.com                                                                                                                                           | \*Swing2App User ID                                                                                                                                                                                                                                                           |
| <mark style="color:blue;">api\_key</mark>                 | abewfw235ksie8d                                                                                                                                              | \*API KEY issued by Swing2App                                                                                                                                                                                                                                                 |

<mark style="color:orange;">**\* App ID and API KEY that need to be issued can be issued by requesting the customer service center.**</mark>

<mark style="color:blue;">\[javascript Implementation example – Send all]</mark>

```
var apiUserId = "help@swing2app.com";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "Title" , "messageContent" : "Content" , 
"messageLinkUrl" : "http://m.naver.com" , messageImageUrl : "http://swing2app.com/abc.png" }';
var sendTargetList = '-1';
var sendTargetTypeList = "ALL_TARGET";
$.ajax({
    url: "https://api.swing2app.com/swapi/push_send",
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
    success: function (model) {
        console.log("Push sending success");

    }
});
```

<mark style="color:blue;">\[javascript Implementation example – Individual delivery]</mark>

```
var apiUserId = "help@swing2app.com";
var apiKey = "test_api_key";
var appId = "test_app_id";
var messageJson = '{ "messageTitle" : "Title" , "messageContent" : "Content"}';
var sendTargetList = 'user_id';
var sendTargetTypeList = "MEMBER";
$.ajax({
    url: "https://api.swing2app.com/swapi/push_send",
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
    success: function (model) {
        console.log("Push sending success");

    }
});
```
