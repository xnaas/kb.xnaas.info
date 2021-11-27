---
title: uBlock Origin
description: uBlock Origin is a free and open-source, cross-platform browser extension for content-filtering, including ad-blocking.
og_title: uBlock Origin
---

# uBlock Origin

## Resources

* [GitHub](https://github.com/gorhill/uBlock/)
* [Wiki](https://github.com/gorhill/uBlock/wiki)

## Cosmetic Filtering

!!! info "Special Note"
    With no subdomain specified, filters will match the main domain space as well
    as all subdomains. It is *usually* best to specify no subdomain.

### YouTube

These filters prevent the end of YouTube videos from being covered in garbage
so you can actually finish watching a video.

```
!youtube
youtube.com##.ytp-ce-covering-overlay
youtube.com##.ytp-ce-element-shadow
youtube.com##.ytp-ce-covering-image
youtube.com##.ytp-ce-expanding-image
youtube.com##.ytp-ce-element.ytp-ce-video.ytp-ce-element-show
youtube.com##.ytp-ce-element.ytp-ce-channel.ytp-ce-channel-this
youtube.com##.ytp-cards-teaser
youtube.com##.ytp-ce-element
```

### Reddit

These filters get rid of some bloat from Reddit's UI.

```
!reddit
!chat
reddit.com##chat
reddit.com###chat
reddit.com###header-bottom-right > span.separator:nth-of-type(3)
!logout
reddit.com##.hover.logout
!ads/spam/filler
reddit.com##.goldvertisement
reddit.com##.profilebetabar.infobar
reddit.com##.native-ad-container
reddit.com##.premium-banner
```

### Cookie Notices

This section is deprecated. I would recommend just adding
[*I Don't Care About Cookies*](https://www.i-dont-care-about-cookies.eu/abp/).
