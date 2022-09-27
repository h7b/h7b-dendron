---
id: 7qji5ydxk5iq51lnyokyyp3
title: Sign in to Tweaked Google App
desc: Sign in to Tweaked Google App Youtube uYouplus
updated: 1661177200430
created: 1659816551404
tags: cat.tut
---
# How to sign in to tweaked Google app (YouTube/YouTube Music)

ref: [r/sideloaded](https://www.reddit.com/r/sideloaded/comments/wh0g35/how_to_sign_in_to_tweaked_google_app/)

The situation:
- Google has added a new implementation that prevents users from signing in to modified YouTube apps (see [Google Account Help](https://support.google.com/accounts/answer/6010255?hl=en)). Basically, If the bundle ID of the app is modified, Google won't let you sign in. But if you're already signed in, you will be fine. Just don't remove the app, so you don't need to sign in again.

Currently, there are two workarounds
- Method 1: Keeping the original bundle ID of YouTube when sideloading YouTube. Not available for free users. You’ll need a paid developer certificate & a wildcard provisioning profile to achieve it
- Method 2: available for everyone
    - First, try to login to YouTube like normal, you’ll see the "You can't sign in to this app…" warning.
    - Hold and copy the URL like [this](https://camo.githubusercontent.com/be528e9123cba5a5348ddbf2912b70397c8a1e742d54df0a7a8d14bdfe152bfe/68747470733a2f2f6d656469612e646973636f72646170702e6e65742f6174746163686d656e74732f3835383635373535333738313232373537302f313030353035313538303530363139343030312f494d475f32303232303830355f3136353630312e6a7067).
    - Open the URL in a new Safari private (incognito) window, you should be able to sign in to Google now.
    - After signing in to Google, you will be asked to "Open in YouTube" > Done!