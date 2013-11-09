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

``` shell
sudo mkdir -p /opt/uncrate
sudo chown ${USER}:${GROUP} /opt/uncrate
git clone https://github.com/uncrate/my-uncrate /opt/uncrate/repo
cd /opt/uncrate/repo
git remote rm origin
git remote add origin <location of your new git repository>
git push -u origin master
```

### Source the uncrate environment

Source the uncrate environment in your `~/.bashrc` or `~/.zshrc` by adding the following line at the end of your config:

``` shell
[ -f /opt/uncrate/env.sh ] && source /opt/uncrate/env.sh
```

### Customization
The recipes that are run can be customized using the `soloistrc` and `Cheffile` files.  The `Cheffile` defines the location of each of the cookbooks needed to run your recipes.  In `soloistrc` you define each recipe to run and can set/override the recipe attributes.

#### Including Cookbooks
Add the cookbooks you want to include to the Cheffile located in the uncrate repo (/opt/uncrate/repo/Cheffile):

```
# Cookbooks in the uncrate org (github.com/uncrate/*-crate) can be included using the github method.
github "sublime_text-crate", "master"
github "intellij-crate", "master"

# Cookbooks hosted elsewhere can be included using the cookbook method
cookbook 'some-crate',
  :git => 'git://github.com/uncrate/vim-crate.git',
  :ref => 'master'
```

#### Including Recipes and Configuring Attributes
Add the recipes you want to run and configure any attributes in the soloistrc file located in the uncrate repo (/opt/uncrate/repo/soloistrc):

```
recipes:
  - uncrate_base # base recipe must be included
  - sublime_text-crate
  - intellij-crate
node_attributes:
  uncrate:
    user: johnlcox # use your OS username
  intellij:
    install_flaver: intellij_community_edition
```
