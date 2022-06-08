---
title: uBlock Origin
description: uBlock Origin is a free and open-source, cross-platform browser extension for content-filtering, including ad-blocking.
og_title: uBlock Origin
---

<!-- Abbreviations -->
*[uBO]: uBlock Origin

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

### Misc.

This is just a collection of...everything else in my uBO filters.

```
! 10/27/2019 https://slickdeals.net
slickdeals.net##.abc

! 10/31/2019 https://techreport.com
techreport.com##.et_social_mobile_on.et_social_sidebar_flip.et_social_rectangle.et_social_animated.et_social_slideright.et_social_visible_sidebar.et_social_sidebar_networks

! 11/1/2019 https://smite.guru
smite.guru##header > div:nth-of-type(1)
smite.guru###smite_horizontal_adhesion

! 11/4/2019 https://smite.guru
smite.guru###smite_horizontal_btf

! 11/9/2019 https://smite.guru
smite.guru###smite_vertical_atf
smite.guru###smite_desktop_300x250

! 12/31/2019 https://www.dell.com
www.dell.com##.alert-warning.alert

! 3/26/2020 https://zapier.com
zapier.com##.top-bar--justify-between.top-bar

! 5/30/2020 https://myportal.seagate.com
myportal.seagate.com##.in.fade.modal-backdrop
myportal.seagate.com###am-spp-renewal

! 6/1/2020 https://hub.docker.com
hub.docker.com##.styles__repoUsage___1GVBC

! 6/8/2020 https://killedbygoogle.com
killedbygoogle.com##.cWuQrA.sc-bdVaJa

! 6/24/2020 https://www.spotify.com
www.spotify.com##.Hero__rootWithNavigationPadding--3o5hL.container-new-family.Hero__root--3HX6f

! 7/3/2020 https://tesletter.com
tesletter.com##.show.modal-monitor-backdrop

! 7/16/2020 https://www.pokecommunity.com
www.pokecommunity.com###navbar_notice_408
www.pokecommunity.com###navbar_notice_4

! 7/16/2020 https://www.ign.com
www.ign.com##.links-container

! 7/31/2020 https://www.howtogeek.com
www.howtogeek.com##.email-overlay
www.howtogeek.com##.overlay-inner

! 8/4/2020 http://www.imagebam.com
www.imagebam.com###hideifpossible

! 8/7/2020 https://www.wired.com
www.wired.com##.paywall-bar__expanded
www.wired.com###failsafe-clickthrough

! 8/7/2020 https://www.thomas-krenn.com
www.thomas-krenn.com###xtxNavigationOffCookiePolicy > div
www.thomas-krenn.com###xtxNavigationOffCookiePolicy
www.thomas-krenn.com##.xtxNavigationOffCanvasOverlay

! 2020-08-14 https://help.twitch.tv
help.twitch.tv##.cCreateCase.slds-spinner_container

! 2020-08-15 https://www.servethehome.com
www.servethehome.com###custom_html-6

! 2020-08-20 https://twitter.com
twitter.com##.r-xnswec.r-urgr8i.css-1dbjc4n

! 2020-08-27 https://getsharex.com
getsharex.com##.popover-body
getsharex.com##.arrow

! 2020-09-03 https://onezero.medium.com
onezero.medium.com##.yt.ys.tu.yr.yq.yp.yo.tt.yn.ym.yl.yk.lu.yj.yi.yh.yg.yf.ye.yd.yc.yb.ya.xz.xy.xx.xw.xv.xu.xt.xs.ab.xr.gs.hx.by

! 2020-09-26 https://www.youtube.com
www.youtube.com###clarify-box

! 2020-10-18 https://pypi.org
pypi.org##.notification-bar--survey.notification-bar

! 2020-11-04 https://www.washingtonpost.com
www.washingtonpost.com##.paywall-overlay.bottom-0.right-0.left-0.fixed

! 2020-11-24 https://www.dataquest.io
www.dataquest.io##.tve_white.tvu_set_01.thrv_wrapper.tve_element_hover.tve_no_icons.tve_no_drag.thrv_ult_bar

! 2020-11-30 https://streamable.com
streamable.com##.owner-ad.topbanner

! 2020-12-02 https://www.evga.com
www.evga.com##div.message-block:nth-of-type(2)
www.evga.com##div.message-block:nth-of-type(3)
www.evga.com##div.message-block:nth-of-type(4)

! 2020-12-04 https://fanart.tv
fanart.tv##div.container:nth-of-type(4)

! 2020-12-12 https://music.apple.com
music.apple.com##.upsell-banner

! 2020-12-18 https://www.netburner.com
www.netburner.com##.custom-position.fixed.active.pum-position-fixed.size-medium.responsive.pum-responsive-medium.pum-responsive.theme-19569.popmake.pum-container

! 2021-07-11 http://rpi
rpi##div.col-lg-3.col-sm-6:nth-of-type(3)
rpi##div.col-lg-3.col-sm-6:nth-of-type(4)
rpi##html:style(filter:hue-rotate(180deg) invert(1))
rpi##html:style(background-color: #3e3e42 !important)

! 2021-08-13 https://www.thedigitalfix.com
www.thedigitalfix.com###nn_bfa_wrapper

! 2021-09-02 https://www.tvmaze.com
||static.tvmaze.com/images/cinereus/160600_d.png$image

! 2021-10-26 https://deeprockgalactic.fandom.com
deeprockgalactic.fandom.com##.unified-search__layout__right-rail

! 2022-02-22 https://pypi.org
pypi.org##.notification-bar--banner.notification-bar

! 2022-03-19 https://crystalmathlabs.com
crystalmathlabs.com##[href="https://bit.ly/3vtAfhW"] > div

! 2022-03-25 https://gregoryvigotorres.github.io
gregoryvigotorres.github.io##.wy-side-scroll
gregoryvigotorres.github.io##.wy-nav-side

! 2022-05-20 https://www.formula1.com
www.formula1.com##.trustarc-banner-container
www.formula1.com###trustarc-banner-overlay

! 2022-05-20 https://domainnamewire.com
domainnamewire.com##.widget-area.sidebar-primary.sidebar
domainnamewire.com##.after-header
```

### Cookie Notices

This section is deprecated. I would recommend just adding
[*I Don't Care About Cookies*](https://www.i-dont-care-about-cookies.eu/abp/).
