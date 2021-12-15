---
title: Shells
description: Info for various Linux shells.
og_title: Linux Shells
---

!!! warning "Incomplete"
    This page is incomplete and basically useless. Just saving a note for myself, more than anything.

# Shells

## bash

### Show all terminal colors.

```sh
for COLOR in {1..255}; do echo -en "\e[38;5;${COLOR}m${COLOR} "; done; echo;
```
