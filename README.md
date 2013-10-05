# my-uncrate

## Dependencies
* Install git
* Install ruby (Only tested using RVM with ruby 1.9.3)
* Install bundler

### Ubuntu dependency bootstrap script

`wget -O - https://raw.github.com/uncrate/my-uncrate/dev/uncrate.sh | bash`

## Source the uncrate environment

Source the uncrate environment in your `~/.bashrc` or `~/.zshrc` by adding the following line at the end of your config:

```sh
[ -f /opt/uncrate/env.sh ] && source /opt/uncrate/env.sh
```
