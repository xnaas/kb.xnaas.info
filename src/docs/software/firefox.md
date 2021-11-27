---
title: Firefox
description: Information and tweaks for Mozilla Firefox.
og_title: Mozilla Firefox
---

# Firefox

## Resources

* [/r/FirefoxCSS](https://www.reddit.com/r/FirefoxCSS/)

---

## Customizations

=== "about:config"
    | Preference                                            | Value       |
    | :---------------------------------------------------- | :---------- |
    | media.peerconnection.enabled                          | false       |
    | toolkit.legacyUserProfileCustomizations.stylesheets   | true        |
    | default-browser-agent.enabled                         | false       |
    | alerts.useSystemBackend                               | true        |
    | browser.tabs.loadBookmarksInTabs                      | true        |
    | browser.tabs.loadBookmarksInBackground                | true        |
    | media.default_volume                                  | 0.1         |
    | extensions.pocket.enabled                             | false       |
    | network.IDN.use_whitelist                             | true        |
    | browser.menu.showViewImageInfo                        | true        |
    | fission.autostart                                     | true        |
    | browser.urlbar.suggest.calculator                     | true        |
    | browser.urlbar.unitConversion.enabled                 | true        |
    | browser.compactmode.show                              | true        |
    | browser.uidensity                                     | 1           |

=== "userChrome"
    ```{.css title="userChrome.css"}
    @import "remove_megabar.css"; /* Megabar Bad */

    /* Always Show Reader View Button */
    #reader-mode-button { 
      display: -moz-box !important; 
      visibility: visible !important;
    }

    /* Bookmarks: Show Keyword Field & URL/Location Field */
    #editBMPanel_keywordRow,
    #editBMPanel_locationRow
    {
      visibility: visible !important;
    }

    /* Change Selected Tab Color */
    .tab-line[selected="true"] {
      background-color: #ff79c6 !important;
    }
    ```

    ```{.css title="remove_megabar.css"}
    /* REMOVE MEGABAR START
     * VERSION 1.0.5 (my own modification)
     * CODE AT: https://github.com/WesleyBranton/Remove-Firefox-Megabar/blob/master/remove_megabar.css */
    @-moz-document url(chrome://browser/content/browser.xhtml) {
      /* DISABLE EXPANDING START */
      #urlbar[breakout][breakout-extend] {
        top: calc((var(--urlbar-toolbar-height) - var(--urlbar-height)) / 2) !important;
        left: 0 !important;
        width: 100% !important;
      }

      #urlbar[breakout][breakout-extend] > #urlbar-input-container {
        height: var(--urlbar-height) !important;
        padding-block: 0 !important;
        padding-inline: 0 !important;
      }

      #urlbar[breakout][breakout-extend] > #urlbar-background {
        animation-name: none !important;
        box-shadow: 0 1px 4px rgba(0, 0, 0, .05) !important;
        border-color: var(--lwt-toolbar-field-border-color, hsla(240,5%,5%,.25)) !important; /* Removes the awful blue outline/border */
      }
      /* DISABLE EXPANDING END */

      /* REMOVE URL RESULT PADDING START */
      .urlbarView {
        margin-inline: 0 !important;
        width: 100% !important;
      }

      .urlbarView-row {
        padding-block: 0 !important;
      }
      /* REMOVE URL RESULT PADDING END */

      /* MOVE URL RESULT TYPE ICON TO LEFT START */
      .urlbarView-type-icon {
        min-width: 16px !important;
        height: 16px !important;
        margin-bottom: 0 !important;
        margin-inline-start: 0 !important;
      }

      .urlbarView-favicon {
        margin-inline-start: 20px !important;
      }
      /* MOVE URL RESULT TYPE ICON TO LEFT END */

      /* DISPLAY GO BUTTON WHEN TYPING START */
      #urlbar-input-container[pageproxystate="invalid"] #urlbar-go-button {
        display: block !important;
      }
      /* DISPLAY GO BUTTON WHEN TYPING END */
    }
    /* REMOVE MEGABAR END */
    ```

=== "userContent"
    ```{.css title="userContent.css"}
    /* Changes the scale of the PiP button */
    .pip-wrapper {
      transform: scale(0.8);
    }

    /* Always Show Volume Slider */
    #controlsContainer:not([hidden]) #controlBar #muteButton:not([noAudio]) ~ #volumeStack {
        display: inline-block !important;
    }

    #controlsContainer:not([hidden]) #pictureInPictureToggle[hidden] ~ #controlBar #muteButton:not([noAudio]) {
        display: none !important;
    }
    ```
