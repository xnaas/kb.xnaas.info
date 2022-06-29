---
title: Bitwarden
description: Bitwarden password manager.
og_title: Bitwarden
---

<!-- Abbreviations -->
*[SDA]: Steam Desktop Authenticator
*[TOTP]: Time-based One-Time Password

# Bitwarden

## Resources

* [Bitwarden](https://bitwarden.com)
* [Bitwarden TOTP](https://bitwarden.com/help/article/authenticator-keys/)
* [Steam Desktop Authenticator](https://github.com/Jessecar96/SteamDesktopAuthenticator) (SDA)

## "Unsupported" Support

### Steam

!!! danger "**WARNING**"
    This is *not* the same experience as using the actual Steam mobile app.
    Some limitations include: not being able to confirm trades, not being
    able to reset your password without removing the "authenticator" first,
    and more. This is purely a convience feature that allows you to have your
    2FA in Bitwarden with everything else.

1. Follow the [install and setup instructions for the SDA](https://github.com/Jessecar96/SteamDesktopAuthenticator).
    
    !!! note
        Do not encrypt/add a password. You're going to delete this after setting it up
        with Bitwarden.

2. Look in the `maFiles` subdirectory where the SDA is installed. One of the files
    will be named `[your_steamID].maFile`. Open it.

3. One of the JSON variables will look like:
    ``` {linenums="0"}
    "uri":"otpauth://totp/Steam:your-username?secret=ABCDEFGHIJKLMN1234OPQRSTUVWXYZ4321&issuer=Steam"
    ```

4. You want your TOTP entry in Bitwarden to look like:
    ``` {linenums="0"}
    steam://ABCDEFGHIJKLMN1234OPQRSTUVWXYZ4321
    ```

5. Get your [SteamGuard recovery codes](https://store.steampowered.com/twofactor/manage)
    and store them in Bitwarden or somewhere else safe.

6. Clear info from and uninstall the
    [SDA](https://github.com/Jessecar96/SteamDesktopAuthenticator) from Step 1.
