# easy-ngx-google-analytics
[![Build Status](https://travis-ci.org/sharukworld/easy-ngx-google-analytics.svg?branch=master)](https://travis-ci.org/sharukworld/easy-ngx-google-analytics)
![Li](https://img.shields.io/npm/l/easy-ngx-google-analytics.svg)


> Easy Ngx Google Analytics Angular Module

###### This module used the latest Global Site Tag (gtag.js).

## prerequisite
[Generates a google analytics tracking ID](https://support.google.com/analytics/answer/1042508)
## Installation

```
npm install easy-ngx-google-analytics --save
```

install gtag.js by copying the following snippet and pasting it immediately after the head tag on index.html. Replace GA_TRACKING_ID with the tracking ID of the Google Analytics property you want to send data to
<pre>
  <!-- Global Site Tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=<b>GA_TRACKING_ID</b>"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments)};
  gtag('js', new Date());
  gtag('config', <b>'GA_TRACKING_ID'</b>, { 'send_page_view': false });
</script>
  </pre> 
  
Add below code to your app module.
```
import { EasyNgxGoogleAnalyticsModule, EasyAnalyticsConfig } from 'easy-ngx-google-analytics';
```

Create a config variable, add your  GA_TRACKING_ID as shown below.
```
const easyAnalyticsConfig: EasyAnalyticsConfig = {
  gaTrackingId : 'UA-XXXXXXXXX-X'
};
```

If you have any routes you need to ignore, update the easyAnalyticsConfig as shown

Here we will add /loading to ignore list

```
const easyAnalyticsConfig: EasyAnalyticsConfig = {
  gaTrackingId : 'UA-XXXXXXXXX-X',
  routesToIgnore : [/\/loading$/]
};
```
All routes with loading will be ignored.

Next we import the nodeModule to app module

```
  imports: [
    EasyNgxGoogleAnalyticsModule.forRoot(easyAnalyticsConfig)
  ]
```

Finally, we add the code below to inside our app.component.html(our initial template).
```
<easy-ngx-google-analytics></easy-ngx-google-analytics>
```
## Future Upgrades
trim urls to exclude any authenticating keys/view or as per our requirements.




## License

MIT


