# Sign-in with Google

###### You can let your users authenticate using their Google Accounts by integrating Google Sign-In into your app. *WeDeploy™ Authentication*.

## Sign-in with Google

<!-- <article id="sign-in> -->

```js
var auth = WeDeploy.auth();

var provider = new auth.provider.Google();
provider.setProviderScope("email");

auth.signInWithRedirect(provider);

auth.onSignIn(function(user) {
	// Fires when user is signed in after redirect.
});
```

<!-- </article> -->

<!-- <article id="setup-app-client-id-and-secret> -->

## Setup app client id and secret

Create a client id and client secret by [registering your application](https://developers.google.com/youtube/registering_an_application) on Google. 

```json
{
	"id": "auth",
	"name": "Auth",
	"type": "wedeploy/auth",
	"env": {
		"WEDEPLOY_AUTH_EMAIL_CONTENT": "Hello ${user.name},<br><br>Follow this link to reset your ${project.name} password:<br><br><a href=\"http://auth.${project.domain}/reset.html?code=${resetCode}&email=${user.email}\" target=\"_blank\">http://auth.${project.domain}/reset.html?code=${resetCode}&email=${user.email}</a><br><br>If you didn't ask to reset your password, you can ignore this email.<br><br>Thanks,<br><br><em>WeDeploy Team</em>",
		"WEDEPLOY_AUTH_EMAIL_REGEX": "^[a-zA-Z0-9.!#$%&'*+/=?^_`{|}~-]+@[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?(?:\\.[a-zA-Z0-9](?:[a-zA-Z0-9-]{0,61}[a-zA-Z0-9])?)*$",
		"WEDEPLOY_AUTH_GOOGLE": "true",
		"WEDEPLOY_AUTH_GOOGLE_CLIENT_ID": "",
		"WEDEPLOY_AUTH_GOOGLE_CLIENT_SECRET": "",
		"WEDEPLOY_AUTH_SECURE_FIELDS": "providers,password,resetKey,supportedScopes"
	}
}
```

<!-- </article> -->

## What's Next?

* Now we're ready to start authenticating and grow our user base.