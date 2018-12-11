---
layout: post
title: "Getting started with Jekyll blogging on Windows"
date: "2017-05-29 11:33:49 +0100"
---

Jekyll is awesome. It is a framework built with Ruby that allows you to simply generate static websites using templates and simple formatting using markdown. GitHub Pages uses Jekyll. This blog is hosted on GitHub Pages actually (which I am really grateful for). It is coded in Ruby so the first thing to do when starting to use Jekyll from a Windows machine is to install Ruby.

### Ruby setup

You can download the installer for Ruby [from here](https://rubyinstaller.org/downloads/). The latest version of Ruby, 2.4+, works fine. When going through the installer, make sure that the option to "Add Ruby executables to your PATH" is selected (it should be by default).

![]({{ "assets/images/JEKYLL_1_Add_to_path.png" | relative_url }})

At the end of the install, you will be asked if you want to install MSYS2. This is optional for a base Jekyll install but recommended to ensure that any plugins or 'gems' that you may want to install function as intended. When going through the MSYS2 install process, you should go through in the numerical order of the menu. Default options for MSYS2 will be sufficient. After step 3 has completed, you can close the command prompt window.

### Installing Jekyll

Now that Ruby is installed and added to the PATH environment variable, it's time to install the actual Jekyll software. Firstly, open up a Command Prompt. You can do this either through the Start menu or by holding the Windows key then pressing R to bring up the run window then entering 'cmd' and pressing Enter. Type in the below command:

``` shell
gem install jekyll bundle
```

This will download and install all of the dependencies required for Jekyll.

### Testing the Jekyll install

Time to test that fancy new install of Ruby and Jekyll. While you still have the Command Prompt open, you can use `jekyll new test` to create a new blog in a folder called test. You can of course replace test with whatever name you wish as the name of the folder will not be reflected in the name of the website at all. If you are going to be using GitHub Pages, then it's best to name the folder with the pattern [username].github.io .

![]({{ "assets/images/JEKYLL_3_new_blog.png" | relative_url }})

After the blog is created, you can build the website and start hosting it on a local server using the below commands:

``` shell
cd test
jekyll serve
```

What the above command does is brings the Command Prompt into the test folder (remember to swap for whatever name you chose), then tells Jekyll to build the website and host it on the local machine. By default, the site is hosted at http://127.0.0.1:4000 / http://localhost:4000 which is the computer that you are currently using.

![]({{ "assets/images/JEKYLL_4_jekyll_serve.png" | relative_url }})

If you open up a web browser then you'll be able to load the blog by putting the above addresses into the web browser. This is what you'll see with the default settings.

![]({{ "assets/images/JEKYLL_5_default_blog.png" | relative_url }})

Now that you have Jekyll installed and can put together a simple default blog, you can now go through the _config.yml file in order to change some basic information and then edit the page layouts to alter the appearance of your blog. To get started, I would recommend going through [the Jekyll documentation](https://jekyllrb.com/docs/structure/) as well as installing the [Atom text editor](https://atom.io/) to make editing and working on your blog easier.
