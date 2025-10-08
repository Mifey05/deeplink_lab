# deeplink_lab
## Reflection

### TL;DR (summary)
Let's keep this short. Android intent filters are just navigation routes with extra steps. while navigation routes are hard-coded into the codes, intents allows for users to enter a specific part of the app quickly via a link. This is apparently what's called "deep linking". One example I can think of is of Duolingo's streak reminder notification, which immediately puts you in a course to complete when you pressed that notification. As for difficulties, aside from the fact that I changed the driver from D: to E: which for some reason some particular part refuses to refactor, or that flutter wants to use android sdk 35.0.0 while only having 36.1.0, everything else seems fine. Nothing significant really happened.



### Reflection
Concept Check:
What is the difference between a route inside Flutter and a deep link at the Android level? Why does Android need an intent filter?

Routes in flutter are conceptually a stack, meaning insertion is through LIFO. Depending on how it's designed, a regular flutter navigation could be quite long when attempting to reach a particular part of the app. Intent Filters, however, could immediately push a particular page to the top of the stack. This essentially means there's a quick access to a particular page, it's why intent filter exists.

Technical Understanding:
Explain the role of the app_links package.
What happens if a deep link is opened while the app is already running?

App Links acts as an async listeners that receives the special Links filtered through the android manifest file.
As for the latter, it depends on the design and flow of the code. In this app's case, it pushes the relevant page onto the stack

Debugging Insight:
Suppose your adb command opens the app but it doesn’t navigate to the detail page.
What part of your code or manifest would you check first, and why?

*It depends* on how the display is. if the links aren't received properly, there could be a typo in the intent filters in the manifest. Should the links be received properly however, the problem would be in the code itself, especially in the functions that processes the link.