# Getting started

Add Talkative to your web app in less than 5 minutes. You can either install by copy/pasting a snippet or via npm.

Login to [Talkative](https://meettalkative.com) and click Create an app.  Fill out all information in the Install page and note down your App ID.

## Install via snippet

Copy the code snippet you see in the Install page in to `<head>` of every page of your site where you might want to reach a user. The snippet should look like this:

```
<!-- Start of async Talkative code -->
<script>
!(function() {
  (o = document.createElement("script")),
    (o.type = "text/javascript"),
    (o.id = "talkativeSdkScipt"),
    (o.crossorigin = "anonymous"),
    (o.src = "https://meettalkative.com/resources/talkative.min.js"),
    (n = document.getElementsByTagName("script")[0]),
    n.parentNode.insertBefore(o, n);
})();
talkativeSdkScipt.addEventListener("load", function() {
  talkative.load(YOUR_APP_ID);
});
</script>
<!-- End of async Talkative code -->
```
where `YOUR_APP_ID` is the Talkative App ID of your app that you can find in the Install page

You can reach your users on any page which has the above snippet. You'll see them online in your dashboard and can call them at any time. 

You can access Talkative functions anywhere in your page via the `window` object. For example, just call `window.talkative.identify(USER_EMAIL)` or `window.talkative.track()`.

## Install via npm

If you use npm or yarn with your frontend, you can also use the [Talkative npm package](https://www.npmjs.com/package/talkative-sdk).

1. Run `npm i talkative-sdk --save` to install the SDK on your frontend.
2. In every page that you would like to reach a user, import the package with `import talkative from "talkative-sdk";`
3. On page load, call `talkative.load(YOUR_APP_ID)` where `YOUR_APP_ID` is the Talkative App ID of your app that you can find in the Install page. 

You can reach your users on any page which has the `load` function called. You'll see them online in your dashboard and can call them at any time.

# Advanced

## Tracking events
Track and segment users you want to talk to by actions they've taken

By default, if you have the Talkative snippet installed on a page, you can see which pages your users are visiting. You can also track more granular events like completeing onboarding, pressing a Submit button or trying a new feature. Simply call `talkative.track(EVENT_NAME)`.

## Identifying users
Identify users by email to figure out who to reach out to for user interviews

1. If you want to identify users with their email address, you can call `talkative.identify(YOUR_USERS_EMAIL)` on any page that has the Talkative snippet from above. As soon as you call this function, the unidentified user on your page will be labeled with `YOUR_USERS_EMAIL` going forward. 

2. When logging out your user, call `talkative.logout()` so that we no longer associate new users visiting your page in the same browser.

# API

| Function | Parameters        | Return Value | Where to call                           | Example                                      |
|----------|-------------------|--------------|-----------------------------------------|----------------------------------------------|
| load     | appID: String     | None         | On every page you want to use Talkative | talkative.load("2XlXiopHy")                  |
| identify | email: String     | None         | When you're logging in a user           | talkative.identify("test@meettalkative.com") |
| track    | eventName: String | None         | At time of any event you want to track  | talkative.track("Onboarding complete")       |
| logout   | None              | None         | When you're logging out a user          | talkative.logout()                           |


If you have any trouble at all with installation, just email us at <support@meettalkative.com> or on the chat in the bottom right. We'll get back to you in 12 hours or less.

# Google Tag Manager
If you use Google Tag Manager, follow these steps:
1. Open up your account and head to the workspace for your site
2. Select New Tag
3. In Tag Configuration, select Custom HTML
4. Copy and paste the Talkative JavaScript snippet from above with your App ID
5. In Triggering, click + to create a new trigger. Select DOM Ready as the trigger
6. Under this trigger fires on, select All DOM Ready events
7. Hit Submit and publish your workspace