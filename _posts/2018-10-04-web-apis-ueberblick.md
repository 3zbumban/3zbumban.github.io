---
layout: post
title: "CSS Cheatsheet"
comments: true
description: "CSS zusammenfassung"
keywords: "CSS, wt"
---

# [Browser API's](https://developer.mozilla.org/en-US/docs/Web/API)

- [Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Storage_API)
  - only avalible in https
  - lets all API's and technologys store data

- [Web Storage API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API)
  - mechanism to store key/value pairs more intuitive than cookies

- [XMLHttpRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest)
  - HTT, ftp , XML and other requests

- [Canvas API](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
- [clipboard API](https://developer.mozilla.org/en-US/docs/Web/API/Clipboard_API#Accessing_the_clipboard)

  Example:

  ```js
  navigator.clipboard.readText().then(
  clipText => document.queryElementSelector(".editor").innerText += clipText);  
  ```

- [Credential Management API](https://developer.mozilla.org/en-US/docs/Web/API/Credential_Management_API)
  - store and retrieve user data from storage

- [Encoding API](https://developer.mozilla.org/en-US/docs/Web/API/Encoding_API)
  - mechanism for Encoding various character encodings (utf-8, ...)

- [Gamepad API](https://developer.mozilla.org/en-US/docs/Web/API/Gamepad_API)

- [Geolocation API](https://developer.mozilla.org/en-US/docs/Web/API/Geolocation_API)
  - only aveliable with https

- [HTML Drag and Drop API](https://developer.mozilla.org/en-US/docs/Web/API/HTML_Drag_and_Drop_API)
- [Performance API](https://developer.mozilla.org/en-US/docs/Web/API/Performance_API)
- [Media Capture and Streams API (Media Stream)](https://developer.mozilla.org/en-US/docs/Web/API/Media_Streams_API)
- [Navigation Timing API](https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API)
- [Page Visibility API](https://developer.mozilla.org/en-US/docs/Web/API/Page_Visibility_API)
- [Payment Request API](https://developer.mozilla.org/en-US/docs/Web/API/Payment_Request_API)
- [Performance API](https://developer.mozilla.org/en-US/docs/Web/API/Performance_API)
- [Performance Timeline](https://developer.mozilla.org/en-US/docs/Web/API/Performance_Timeline)
- [Pointer events](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_events)
  - for regognizing pen/stylus and touch

- [Pointer Lock API](https://developer.mozilla.org/en-US/docs/Web/API/Pointer_Lock_API)
  - information about mouse movement over time

- [Selection API](https://developer.mozilla.org/en-US/docs/Web/API/Selection_API)
  - information about selcted text by the user

- [Touch events](https://developer.mozilla.org/en-US/docs/Web/API/Touch_events)
- [User Timing API](https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API)
  - application specific timestamps

- [Vibration API](https://developer.mozilla.org/en-US/docs/Web/API/Vibration_API)
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API)
- [Web Authentication API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Authentication_API)
- [Notifications API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API)
- [Web Workers API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Workers_API)
  - makes it possible to run script operation in other thread

- [WebGL: 2D and 3D graphics for the web](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)
- [WebRTC API](https://developer.mozilla.org/en-US/docs/Web/API/WebRTC_API)
  - real time communication