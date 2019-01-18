---
layout: post
title: "Setting up Jekyll"
description: "How to get started with Jekyll on your local machine - windows/mac"
date: 2019-01-18
tags: [jekyll,macos]
comments: true
share: true
---

![Center example image](https://www.quickbase.com/blog/wp-content/uploads/2016/10/How-to-Manage-a-Jekyll-and-Hyde-Employee.jpg "Center"){: .center-image}

<p style="text-align: center;"> 
<a href="https://www.quickbase.com/blog/how-to-manage-an-employee-with-a-jekyll-and-hyde-personality"><i>Image source</i></a>
 </p>



I've been a windows user all my life. I love windows, it just feels like that old friend you know inside out, and you know how they think. I started working on this blog on my windows machine and I was up and running with Jekyll in under 10 minutes. Plain and simple. Loved it.

I recently started using a mac and oh boy, installing Jekyll was so much more interesting. So this post is for anyone who has very limited knowledge of mac os, trying to install any ruby gem (like jekyll) on their machine.

For the sake of comparison, lets walk through the steps for setting up Jekyll on a windows machine.

## Jekyll on Windows

So Jekyll is written in Ruby that means you have to  get ruby installed on your machine first. So here's what we need to do:

1. Install Ruby
2. Install Jekyll

### Installing Ruby on Windows

[RubyInstaller](https://rubyinstaller.org/) for windows is the way to go. Head over there and run the installer. Make sure you add Ruby executables to your PATH environment variable. Pretty standard affair.

And one more thing: at the end of the installer - run the 'ridk install' - this is the installer for MSYS2 and MINGW - needed on windows for ruby gems which with C extensions. Once the installer opens, hit all three options one by one to ensure you've got everything.

Verify your ruby installation by opening up a command prompt and typing:

```
ruby -v
```
This should spit out the version of ruby installed and tell you everything will be okay.

### Installing Jekyll on Windows

Now it's all easy sailing from here. We'll use gem, the ruby package manager to get us some jekyll. Type in the following in your cmd to get jekyll installed:

```
gem install jekyll bundler
```
Verify it's installed the same way you verified ruby.

Done.

## Jekyll on Mac

It turns out mac comes with ruby installed. That means we just need to install jekyll right? Well, not exactly.

If you go ahead and try to install jekyll using gem, you're very likely to be denied permissions by your own machine. Turns out, you would need super user privileges to install gems in the ruby directory Apple bundled with your mac. You could try to stronghand your machine and throw in sudo before the command in your terminal but seriously, don't. Just leave Apple's ruby alone. 

So yeah, now we gotta get our own ruby on mac. There are different ways of managing multiple ruby versions out there but I'll outline something that worked great for me. Here's what you need:

1. [Homebrew](https://brew.sh/)- a package manager for macOS
2. [rbenv](https://github.com/rbenv/rbenv) - ruby environment manager 
3. [Bundler](https://bundler.io/) - fetches you the right gems for a project

 First, install homebrew by executing the following command in your terminal:
  
```
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

Next, install rbenv using brew:

```
brew install rbenv
```

Then set it up in your shell like:
```
rbenv init
```
It will ask you to add the output to your `.bash_profile`. Run the following command to do so:

```
echo 'eval "$(rbenv init -)"' >> ~/.bash_profile
```
Restart your terminal for the changes to your `.bash_profile` to take place.

Finally we can set up ruby using rbenv. Check for all the available versions of ruby by executing `rbenv install -l`. Pick the latest version and install:

```
rbenv install 2.6.0
```

Once the installation is done, we can use `rbenv` to set our desired installation of ruby. You can check for all the versions installed using:

```
rbenv versions
```

From the output, select your installed version and set is as the global version of ruby to be used on your machine by executing the following command:

```
rbenv global 2.6.0
```

Now you just need to get bundler installed.

```
gem install bundler
```

Finally, it's time to get Jekyll installed:

```
gem install jekyll
```

And that's it. Now you can play with jekyll on your machine.


Image