# my-uncrate

## Dependencies

### Mac OS X
* Install Xcode from the App Store
* Install Xcode Command Line Tools
* Install ruby (Only tested using RVM with ruby 1.9.3)

### Ubuntu
* Install git
* Install ruby (Only tested using RVM with ruby 1.9.3)

## Setup
Create a new repository to store your uncrate configuration.  Use `my-uncrate` as a skeleton for your own uncrate setup using the following steps:
```shell
sudo mkdir -p /opt/uncrate
sudo chown ${USER}:${GROUP} /opt/uncrate
git clone https://github.com/uncrate/my-uncrate /opt/uncrate/repo
cd /opt/uncrate/repo
git remote rm origin
git remote add origin <location of your new git repository>
git push -u origin master
```

## Source the uncrate environment

Source the uncrate environment in your `~/.bashrc` or `~/.zshrc` by adding the following line at the end of your config:

```sh
[ -f /opt/uncrate/env.sh ] && source /opt/uncrate/env.sh
```
