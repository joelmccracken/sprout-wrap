# (my sprout wrap readme)

clone this repo

install chef omnibus 

````
curl -LO https://www.opscode.com/chef/install.sh
sudo bash install.sh
````

install things necessary for this repo:

````
unset GEM_HOME
unset GEM_PATH
export PATH="/opt/chef/embedded/bin:$PATH"
sudo gem install soloist
sudo gem install bundler
sudo gem install librarian-chef
bundle install
librarian-chef install
bundle exec soloist
````

^^ the above did not work, so moving to chef solo w/ librarian &
sprout cookbooks.


# sprout-wrap

[![Build Status](https://travis-ci.org/pivotal-sprout/sprout-wrap.png?branch=master)](https://travis-ci.org/pivotal-sprout/sprout-wrap)

This project uses [soloist](https://github.com/mkocher/soloist) and [librarian-chef](https://github.com/applicationsonline/librarian-chef)
to run a subset of the recipes in sprout's [cookbooks]((https://github.com/pivotal-sprout/sprout).

[Fork it](https://github.com/pivotal-sprout/sprout-wrap/fork) to
customize its [attributes](http://docs.opscode.com/chef_overview_attributes.html) in [soloistrc](/soloistrc) and the list of recipes
you'd like to use for your team. You may also want to add other cookbooks to its [Cheffile](/Cheffile), perhaps one
of the many [community cookbooks](http://community.opscode.com/cookbooks). By default it configures an OS X
Mountain Lion workstation for Ruby development.

Finally, if you've never used Chef before - we highly recommend you buy &amp; watch [this excellent 17 minute screencast](http://railscasts.com/episodes/339-chef-solo-basics) by Ryan Bates.

## Installation under Mountain Lion (OS X 10.8)

### 1. Install XCode

[![Xcode - Apple](http://r.mzstatic.com/images/web/linkmaker/badge_macappstore-lrg.gif)](https://itunes.apple.com/us/app/xcode/id497799835?mt=12&uo=4)

Don't forget to start up Xcode once it's installed so that you can agree to the terms&mdash;many commands won't work until the terms have been agreed to.

### 2. Install Command Line Tools

  XCode > Preferences > Downloads

### 3. Clone this project

    git clone https://github.com/pivotal-sprout/sprout-wrap.git
    cd sprout-wrap
    git checkout mountain-lion

### 4. Install soloist & and other required gems

If you're running under rvm or rbenv, you shouldn't preface the following commands with `sudo`.

    sudo gem install bundler
    sudo bundle

### 5. Run soloist

[You may want to modify your Energy Saver preferences (**System Preferences &rarr; Energy Saver &rarr; Computer Sleep &rarr; 3hrs**) because soloist usually takes 2-3 hours to complete.]

    bundle exec soloist
