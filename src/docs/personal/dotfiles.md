---
title: Dot Files
description: Some of my dotfiles.
og_title: My Dot Files
---

# Dot Files

### `~/.bash_aliases`

```bash
alias l="exa -al"
alias cat="bat"
alias ccat="/usr/bin/cat"
alias dcu="docker-compose up -d --no-deps --build --remove-orphans"
alias dcp="docker-compose pull"
alias dis="di.sh"
alias size="du -mh --max-depth 1 | sort -rh"
alias cd..="cd .."
alias tracert="traceroute"
alias tmuxmk="tmux new -s"
alias tmuxa="tmux a -t"
alias tmuxrm="tmux kill-session -t"
alias tmuxls="tmux ls"
alias cpr="rsync -ahvP"
alias cprd="rsync -ahvP --remove-source-files"
alias cprr="rsync -ahvPr"
alias tlu="docker exec --user node -it thelounge thelounge upgrade"
alias storage="duf -hide fuse,special"
alias ga="git add ."
alias gc="git commit -m"
alias gp="git push"
alias gpl="git pull"
alias gcleanup="git gc --aggressive"
alias pep8="autopep8 --in-place --aggressive --aggressive --max-line-length 79"
alias bin="gh gist create"
alias gist="gh gist"
alias btop="bpytop"
```
