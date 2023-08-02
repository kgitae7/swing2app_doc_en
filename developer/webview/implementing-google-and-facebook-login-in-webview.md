# Implementing Google and Facebook Login in WebView

While developing Android apps, if you want to use the login features of platforms like Google and Facebook in WebView, it's common for Google and Facebook to block these features for security reasons. (If you encounter a message like the one below, it's because of this block.)



<figure><img src="../../.gitbook/assets/image (23).png" alt="" width="375"><figcaption><p>Example Screen of Google Login Blocked in WebView</p></figcaption></figure>

<figure><img src="../../.gitbook/assets/image (20).png" alt="" width="375"><figcaption></figcaption></figure>



Such blocks should be understood as measures to protect the personal information and account security of app users. In this post, we will take a closer look at the User Agent Disallow issue and introduce alternative approaches to bypass it.

1. What is User Agent Disallow?
   * The User Agent is an HTTP header that the client (web browser or WebView) sends to the server to inform about its properties.
   * User Agent Disallow means that Google and Facebook detect and block the User Agent string to prevent the use of their own login features through WebView.
2. What is the reason for the User Agent Disallow issue?
   * WebView, a lightweight web browser built into mobile apps, needs to block certain features for security reasons.
   * User Agent Disallow is one of the ways to enhance security by restricting the use of login APIs like Google and Facebook in WebView, thereby preventing abuse.
3.  What are the alternative ways to bypass User Agent Disallow? The most common methods include the following approaches:

    a. Open an external browser:

    * When a user chooses Google Login or Facebook Login, WebView opens an external browser to display the login page.
    * Since the external browser is considered a separate application from WebView, it is not affected by the security policy.
    * Once the login is complete, the external browser delivers the login result via a callback URL, which the application can capture and process.

    \* Please refer to the guide below for development.

    b. Use a Fake UserAgent:

    * Using a fake UserAgent can bypass this issue for Google Login. However, it is impossible to bypass it for Facebook.
    * How to change UserAgent in Swing2App:

    Maker(V3) -> Advance Settings -> App Production Settings And change the two values below.

<figure><img src="../../.gitbook/assets/image (22).png" alt="" width="563"><figcaption><p>How to Change UserAgent in Swing2App</p></figcaption></figure>



(1) Android WebView UserAgent

\-> UserAgent Value to Bypass Google Login (Android)

<mark style="color:blue;">**"Mozilla/5.0 (Linux; Android 9; SM-G950N) AppleWebKit/537.36 (KHTML, like Gecko) Version/4.0 Chrome/88.0.4324.93 Mobile Safari/537.36"**</mark>

(2) IOS WebView UserAgent

\-> UserAgent Value to Bypass Google Login (iOS)

<mark style="color:blue;">**"Mozilla/5.0 (iPhone; CPU iPhone OS 16\_0 like Mac OS X) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/16.0 Mobile/15E148 Safari/604.1"**</mark>

## Learn How to Bypass Google and Facebook Login by Opening an External Browser <a href="#how-to-avoid-disallow" id="how-to-avoid-disallow"></a>

### #Execution Process

(1) Run login\_example.html in the app's built-in browser from WebView

The execution example code for login\_example.html is attached below. Among the execution parameters of login\_example.html, there is a customUrl item, which you can set in the advanced settings. You can use the set value.&#x20;

\*It is recommended to set the custom url scheme value as a unique value for each app.



{% code title="run code" %}
```javascript
swingWebViewPlugin.app.methods.openBrowser('https://www.swing2app.co.kr/sns_login_temp/sns_login_temp_ext.html?customUrl=myapp1706');
```
{% endcode %}

* Please refer to the Javascript integration API below for more details about the browser execution&#x20;

Use the code below to create a login page.

* In the code below, the Facebook app ID and Google client ID listed in the todo must be changed before use

{% code title="login_example.html" fullWidth="true" %}
```html
<html>
<head>
    <!-- Title -->
    <title>Swing-test</title>
    <meta content="width=device-width, initial-scale=1" name="viewport">
    <meta charset="UTF-8">
    <!-- Javascripts -->
    <script src="/assets/plugins/jquery/jquery-2.1.4.min.js"></script>
    <script>
        var host = location.host.toLowerCase();
        const urlParams = new URLSearchParams(window.location.search);
        var customUrl = urlParams.get('customUrl');
        var autoType = urlParams.get('autoType');
        $(document).ready(function () {
            window.fbAsyncInit = function() {
                FB.init({
                    appId      : '464485827223968', // todo input facebook App Id
                    xfbml      : true,
                    version    : 'v9.0'
                });
                FB.AppEvents.logPageView();

                if( autoType == "facebook"){
                    fb_login();
                }
            };

            (function(d, s, id){
                var js, fjs = d.getElementsByTagName(s)[0];
                if (d.getElementById(id)) {return;}
                js = d.createElement(s); js.id = id;
                js.src = "https://connect.facebook.net/en_US/sdk.js";
                fjs.parentNode.insertBefore(js, fjs);
            }(document, 'script', 'facebook-jssdk'));
        });

        var googleAuth2 = null;
        function fb_login(){
            $("#infoBox").append("fb_login start");

            FB.login(function(response) {
                if (response.authResponse) {
                    console.log('Welcome!  Fetching your information.... ');
                    var access_token = response.authResponse.accessToken; //get access token
                    if (response.status === 'connected') {   // Logged into your webpage and Facebook.
                        gotoSnsLoginPageFn("facebook", access_token);
                    } else {

                    }
                } else {
                    //user hit cancel button
                    console.log('User cancelled login or did not fully authorize.');
                }
            }, {
                scope: 'public_profile,email'
            });
        }

        function googleInitFn() {
            gapi.load('auth2', function() {
                /* Ready. Make a call to gapi.auth2.init or some other API */
                googleAuth2 = gapi.auth2.init({
                    client_id: '829822048277-oncammdmeq2mku9lbqndknoustamqcbq.apps.googleusercontent.com',  // todo input google client_id
                    cookiepolicy: 'single_host_origin',
                    scope: 'profile email'
                });
                attachSignin(document.getElementById('googleLoginBtn'));

                if( autoType == "google" ) {
                    setTimeout(function() {
                        $("#googleLoginBtn")[0].click();
                    },1000);
                }

            });
        }
        function attachSignin(element) {
            console.log(element.id);
            googleAuth2.attachClickHandler(element, {},
                function(googleUser) {
                    var loginAuth2 = gapi.auth2.getAuthInstance();
                    if (loginAuth2.isSignedIn.get()) {
                        var authToken = loginAuth2.currentUser.get().getAuthResponse().id_token;
                        gotoSnsLoginPageFn("google", authToken);
                    }

                }, function(error) {
                    // alert(JSON.stringify(error, undefined, 2));
                });
        }

        function googleLoginActionFn(){
            googleAuth2.signIn().then(function(user){
                if (user.isSignedIn()) {
                    var authToken = user.getAuthResponse().id_token;
                    gotoSnsLoginPageFn("google", authToken);
                }
            });
        }

        function gotoSnsLoginPageFn(idType, token){
            var $form = $("#snsLoginForm");
            $form.find("[name=id_type]").val(idType);
            $form.find("[name=token]").val(token);

            var runUrl = customUrl +'://app?function=command&linkUrl=' + btoa( "loginTokenCallback('"+ token +"','" + idType + "');" );
            $('.return-app-area a').attr('href', runUrl );
            $('.sns-login-area').hide();
            $('.return-app-area').show();


            $('.command-button').text('Login successful - Proceed');
        }

    </script>

    <meta name="google-signin-client_id" content="829822048277-oncammdmeq2mku9lbqndknoustamqcbq.apps.googleusercontent.com">    <!-- todo google signin-client-id 입력 -->
    <script src="https://apis.google.com/js/platform.js?onload=googleInitFn" async defer></script>

    <script>
    </script>
</head>
<body>

<div class="sns-login-area" style="width: 100%; padding:30px">
    <div class="sns-login-btn-box facebook">
        <div class="sns-login-main-btn" id="snsFaceBookLoginBtn" onclick="fb_login();">
            <span class="icon"><img src="/assets/images/sns_login/facebook.png" /></span>
            <span class="buttonText">Facebook Login</span>
        </div>
    </div>

    <div class="sns-login-btn-box google">
        <div id="googleLoginBtn" class="customGPlusSignIn sns-login-main-btn">
            <span class="icon"><img src="/assets/images/sns_login/google.png" /></span>
            <span class="buttonText">Google Login</span>
        </div>
    </div>
</div>

<div class="return-app-area" style="display: none;padding: 30px;text-align: center;background: #e6e6e6;"><a href="#" class="command-button" style="color: black;text-decoration: none;font-size: 25px;">로그인 성공 - 이동하기</a>
</div>
<div id="infoBox" style="display: none">
</div>

</body>
</html>

```
{% endcode %}

(2) Define a callback function on the website to receive the device token

When the login is completed in browser 1, the deviceToken is passed to the defined callback function. The idType value is passed as defined in login\_example.html, and in the provided source, it is differentiated as "facebook" and "google".



{% code title="Implementing Callback" %}
```javascript
function loginTokenCallback(token, idType) {
    console.log("token : " + token );
    console.log("idType : " + idType );
}
```
{% endcode %}

(3) Implement login with the received accessToken

Afterwards, use the received accessToken to fetch user information on the website and implement linked login.
