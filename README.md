
# What is UI Kit
The UI Kit library is collection of custom UI Component and UI Screens design to build chat application within few minutes.
UI kit is designed to avoid boilerplate code for building UI,it has three different ways to build a chat application with fully customizable UI.It will help developers to build a chat application within using various UI Components.


## Setup
 Follow the below metioned steps for easy setup and seamless integration with UI Kit

### Get your Application Keys
<a href="https://app.cometchat.io/" traget="_blank">Signup for CometChat</a> and then:

* Create a new app
* Head over to the API Keys section and note the `API_Key` and `App_ID` (for Auth Only key)
---
### Minimum Requirement

*Angular8



### Add the CometChat Dependency

install `@cometchat-pro/chat` using `npm`.
```javascript
    npm install @cometchat-pro/chat@2.0.6 --save
```

### Initialize CometChat

The `init()` method initializes the settings required for CometChat
 We suggest calling the `init()` method on app startup, preferably in the `onCreate()` method of the Application class.
```javascript
var appID = "APP_ID";
var region = "REGION";
var appSetting = new CometChat.AppSettingsBuilder().subscribePresenceForAllUsers().setRegion(region).build();
CometChat.init(appID, appSetting).then(
  () => {
    console.log("Initialization completed successfully");
    // You can now call login function.
  },
  error => {
    console.log("Initialization failed with error:", error);
    // Check the reason for error and take appropriate action.
  }
);
```
**Note :**
Make sure you replace the APP_ID with your CometChat `App_ID` and `REGION` with your app region in the above code.

### Log in your User

Once initialization is successful, you will need to create a user.
To create users on the fly, you can use the createUser() method. This method takes a User object and the API Key as input parameters and returns the created User object if the request is successful.

```javascript
let apiKey = "API_KEY";
var uid = "user1";
var name = "Kevin";

var user = new CometChat.User(uid);

user.setName(name);

CometChat.createUser(user, apiKey).then(
    user => {
        console.log("user created", user);
    },error => {
        console.log("error", error);
    }
)
});
```
**Note :** </br>
* Make sure you replace the `API_KEY` with your CometChat API Key in the above code.
* We have setup 5 users for testing having UIDs: `SUPERHERO1`, `SUPERHERO2`, `SUPERHERO3`,`SUPERHERO4` and `SUPERHERO5`.


## Add UI Kit to your project
After adding necessary dependancies inside you app to integrate UI Kit inside your app.Kindly follow the below steps:
 ## Option: 1
1. Simply clone the UI Kit Library from angular-chat-uikit repository.
2. Copy the module to your project lib folder
3. Start using cometchat-component by following the exmple code.

 ## Option: 2
1. Simply clone the UI Kit Library from angular-chat-uikit repository.
2. Build the cometchat-uikit lib using the instructions provided [here](https://angular.io/guide/creating-libraries#publishing-your-library).
3. Start using cometchat-component by following the exmple code.



### Launch UI Unified

*UI Unified is a way to launch a fully working chat application using the UI Kit .In UI Unified all the UI Screens and UI Components working together to give the full experience of a chat application with minimal coding effort.*

 Add the following code snippet in `onSuccess` of CometChat `login`.

 ```html
 <cometchat-embeded>
</cometchat-embeded>
 ```
</br>


## Next Step

 To read the full dcoumentation on UI Kit integration visit our [Documentation](https://prodocs.cometchat.com/docs/angular-ui-kit)



## Troubleshooting
Facing any issues while integrating or installing the UI Kit please <a href="https://forum.cometchat.com/"> visit our forum</a>.