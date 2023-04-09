# Installation Guide

Getting jekyll themes and plugins to work correctly as a new user can sometimes be a pain. It is for that reason I created this intallation guide. The first step is to install Ruby, rvm, and Jekyll. I use Linux to develop on and Linux nginx for my server and I have not used Windows or Mac since the 1990's. I enjoy Linux and have never had a legitimate need for windows. I will walk you through the process on a linux machine. 

## Installing Ruby + Bundler + Jekyll

Jekyll requires both ruby and bundler to build your site. First we setup ruby and then we will add the gems bundler and jekyll.

### Ruby

```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```

### Edit .bashrc

> add these to your non root user for security reasons

```bash
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
### Install Jekyll

```bash
gem install jekyll bundler
```

Now we can check and make sure Ruby, rvm, jekyll, and bundler are all installed. Simply type the name of the software (i.e. ruby) followed by the version flag (-v). It will give you some type of number. If you get an error go on and jump on discord and I will help. 

## Jekyll

Jekyll requires no Gemfile, it only needs the correct directory tree, and it will serve up your files when you type: `jekyll serve`. If you want to use plugins and other themes you will need to include a Gemfile and inclue the theme name in there `gem "jekyll-base"` and then in your "**_config.yml**" add the line `theme: jekyll-base` or whatever the name of the gem you want to use is.

Jekyll has a few tools it comes with which you can learn more about over on my blog where I discuss not only intallation, but also theme creation with the `jekyll new-theme mytheme` tool and how to create and install plugins you find useful. You can read more on my [blog here](https://jekyllgems.dev/blog)

## Gems

Gems are how you package up themes and plugins to be downloaded by other jekyll users and intigrated with their websites. You can browse https://rubygems.org and see some of the gems available to use in your site. 

Once you have decided on a gem you just go into your jekyll project, open a terminal, `gem install gemName` and it will download and install it into your site. Then you need to go into your `Gemfile` and add the line `gem "jekyll-gemName"` and it will be available when you use `bundle exec jekyll serve`. 

> You can find an example [Gemfile here](https://gist.github.com/leatheresque/7a40854ab9e6c17d1c9821061fc9c97e) to use in your project.

