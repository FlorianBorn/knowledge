# How to: Set up history search via arrow keys
```
echo "# Respect default shortcuts.
\$include /etc/inputrc

## arrow up
\"\e[A\":history-search-backward
## arrow down
\"\e[B\":history-search-forward" > ~/.inputrc
```