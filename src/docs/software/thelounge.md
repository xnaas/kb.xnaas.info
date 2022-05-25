---
title: The Lounge
description: Details on my hosted The Lounge instance.
og_title: The Lounge
---

# The Lounge

## Custom CSS

I use the [Solarized theme](https://www.npmjs.com/package/thelounge-theme-solarized)
+ my CSS below.

```css
/* Custom Nick Colors */
#chat .msg .user[data-name="xnaas" i],
#chat .userlist .names .user[data-name="xnaas" i] {
  color: #ff79c6;
}
#chat .msg .user[data-name="feek" i],
#chat .userlist .names .user[data-name="feek" i] {
  color: #00ff00;
}
#chat .msg .user[data-name="Sackbot" i],
#chat .userlist .names .user[data-name="Sackbot" i],
#chat .msg .user[data-name="Tasian" i],
#chat .userlist .names .user[data-name="Tasian" i] {
  color: yellow;
}
#chat .msg .user[data-name="fecktk" i],
#chat .userlist .names .user[data-name="fecktk" i],
#chat .msg .user[data-name="jajabro1" i],
#chat .userlist .names .user[data-name="jajabro1" i] {
  color: #ed6f15;
}
#chat .msg .user[data-name="Aegisfate" i],
#chat .userlist .names .user[data-name="Aegisfate" i] {
  color: #117117;
}

/* Make #channels appears as links */
#chat .inline-channel {
  color: #268bd2;
}

/* Make the userlist thinner */
#chat .userlist {
  width: 130px;
}

/* Make the server/channel list thinner */
#sidebar {
  width: 165px;
}

/* Make server/channel list more compact */
#sidebar .network {
  margin-bottom: 7px;
}
.channel-list-item {
  font-size: 0.95em;
  padding: 5px 18px;
}

/* Hide The Lounge logo */
#sidebar .logo-container {
  display: none;
}

/* Increase font size because I'm fucking blind */
/* This is not friendly across all platforms */
#chat .msg {
  font-size: 1.1em;
}
#chat .time,
#chat .from,
#chat .content {
  padding-top: 2px;
  padding-bottom: 2px;
}
#chat-container #form #input {
  font-size: 1.2em;
  min-height: 25px;
  max-height: 95px;
  line-height: 25px;
}
#mentions-popup-container .mentions-popup {
  font-size: 1.1em;
}

/* Hide Insecure Warning */
#sidebar .not-secure-tooltip {
  display: none;
}

/* website thumbnail size, maybe? */
#chat .toggle-content .thumb {
  max-width: 120px;
  max-height: 80px;
}

/* Image & Video Embed Size */
/* This is NOT friendly across all platforms */
#chat .toggle-content img,
#chat video {
  max-width: 100%;
  max-height: 480px;
}

/* I don't even remember */
#chat .toggle-text {
  white-space: initial;
}

/* Bigger CSS Box by Default */
#user-specified-css-input {
  height: 700px !important;
}

/* Functional Hover Spoilers */
/* Credit: https://bit.ly/3H5NGHU */
.irc-fg0.irc-bg0:hover, .irc-fg3.irc-bg3:hover,
.irc-fg7.irc-bg7:hover, .irc-fg8.irc-bg8:hover,
.irc-fg9.irc-bg9:hover, .irc-fg10.irc-bg10:hover,
.irc-fg11.irc-bg11:hover, .irc-fg14.irc-bg14:hover,
.irc-fg15.irc-bg15:hover, .irc-fg42.irc-bg42:hover,
.irc-fg43.irc-bg43:hover, .irc-fg44.irc-bg44:hover,
.irc-fg45.irc-bg45:hover, .irc-fg46.irc-bg46:hover,
.irc-fg53.irc-bg53:hover, .irc-fg54.irc-bg54:hover,
.irc-fg55.irc-bg55:hover, .irc-fg56.irc-bg56:hover,
.irc-fg57.irc-bg57:hover, .irc-fg58.irc-bg58:hover,
.irc-fg65.irc-bg65:hover, .irc-fg66.irc-bg66:hover,
.irc-fg67.irc-bg67:hover, .irc-fg68.irc-bg68:hover,
.irc-fg69.irc-bg69:hover, .irc-fg70.irc-bg70:hover,
.irc-fg71.irc-bg71:hover, .irc-fg74.irc-bg74:hover,
.irc-fg75.irc-bg75:hover, .irc-fg76.irc-bg76:hover,
.irc-fg77.irc-bg77:hover, .irc-fg78.irc-bg78:hover,
.irc-fg79.irc-bg79:hover, .irc-fg80.irc-bg80:hover,
.irc-fg81.irc-bg81:hover, .irc-fg82.irc-bg82:hover,
.irc-fg83.irc-bg83:hover, .irc-fg84.irc-bg84:hover,
.irc-fg85.irc-bg85:hover, .irc-fg86.irc-bg86:hover,
.irc-fg87.irc-bg87:hover, .irc-fg95.irc-bg95:hover,
.irc-fg96.irc-bg96:hover, .irc-fg97.irc-bg97:hover,
.irc-fg98.irc-bg98:hover {
  color: #000;
}
.irc-fg1.irc-bg1:hover, .irc-fg2.irc-bg2:hover,
.irc-fg4.irc-bg4:hover, .irc-fg5.irc-bg5:hover,
.irc-fg6.irc-bg6:hover, .irc-fg12.irc-bg12:hover,
.irc-fg13.irc-bg13:hover, .irc-fg16.irc-bg16:hover,
.irc-fg17.irc-bg17:hover, .irc-fg18.irc-bg18:hover,
.irc-fg19.irc-bg19:hover, .irc-fg20.irc-bg20:hover,
.irc-fg21.irc-bg21:hover, .irc-fg22.irc-bg22:hover,
.irc-fg23.irc-bg23:hover, .irc-fg24.irc-bg24:hover,
.irc-fg25.irc-bg25:hover, .irc-fg26.irc-bg26:hover,
.irc-fg27.irc-bg27:hover, .irc-fg28.irc-bg28:hover,
.irc-fg29.irc-bg29:hover, .irc-fg30.irc-bg30:hover,
.irc-fg31.irc-bg31:hover, .irc-fg32.irc-bg32:hover,
.irc-fg33.irc-bg33:hover, .irc-fg34.irc-bg34:hover,
.irc-fg35.irc-bg35:hover, .irc-fg36.irc-bg36:hover,
.irc-fg37.irc-bg37:hover, .irc-fg38.irc-bg38:hover,
.irc-fg39.irc-bg39:hover, .irc-fg40.irc-bg40:hover,
.irc-fg41.irc-bg41:hover, .irc-fg47.irc-bg47:hover,
.irc-fg48.irc-bg48:hover, .irc-fg49.irc-bg49:hover,
.irc-fg50.irc-bg50:hover, .irc-fg51.irc-bg51:hover,
.irc-fg52.irc-bg52:hover, .irc-fg59.irc-bg59:hover,
.irc-fg60.irc-bg60:hover, .irc-fg61.irc-bg61:hover,
.irc-fg62.irc-bg62:hover, .irc-fg63.irc-bg63:hover,
.irc-fg64.irc-bg64:hover, .irc-fg72.irc-bg72:hover,
.irc-fg73.irc-bg73:hover, .irc-fg88.irc-bg88:hover,
.irc-fg89.irc-bg89:hover, .irc-fg90.irc-bg90:hover,
.irc-fg91.irc-bg91:hover, .irc-fg92.irc-bg92:hover,
.irc-fg93.irc-bg93:hover, .irc-fg94.irc-bg94:hover {
  color: #fff;
}
```
