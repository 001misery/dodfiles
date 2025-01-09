autoload -Uz colors && colors

# Enable syntax highlighting
autoload -Uz compinit && compinit

# Enable autosuggestions
autoload -Uz bashcompinit && bashcompinit

# Enable colors for ls, grep, etc.
if [[ -x /usr/bin/dircolors ]]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dircolors -b)"
    alias ls='ls --color=auto'
    alias dir='dir --color=auto'
    alias vdir='vdir --color=auto'
    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi

set_prompt() {
  if [[ $? -eq 0 ]]; then
    # Last command succeeded (green)
    PS1="%{$fg[green]%}%n@%m%{$reset_color%} %{$fg[blue]%}%~%{$reset_color%} \$ "
  else
    # Last command failed (red)
    PS1="%{$fg[red]%}%n@%m%{$reset_color%} %{$fg[blue]%}%~%{$reset_color%} \$ "
  fi
}

precmd() {
  set_prompt
}
