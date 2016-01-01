+++
date = "2016-01-01T12:48:14+05:00"
draft = true
title = "How to setup a blog using Hugo"
Description = "In this post I tell you about some really cool features of hugo while guiding you through it's intallation."
categories = ["open source", "tutorial", "hugo"]
featuredimage = "https://gohugo.io/img/hugo.png"
author = "Hannan Ali"
+++

## Hugo is easiest of them folks
Hey there! I've tried many of the static templating engines in the past. Most of them were based on **[node.js](https://nodejs.org)** such as [Wintersmith](https://github.com/jnordberg/wintersmith), [Hexo](https://hexo.io), [BlackSmith](https://github.com/flatiron/blacksmith) but since I've tried Hugo I am not going back now. Hugo is the best Static Website Engine **EVER**. Some of the features that are very impressive about Hugo include:

- It's speed and performance (check out this impressive [Hugo Benchmark Video](https://www.youtube.com/watch?v=CdiDYZ51a2o))
- It's ultra flexibility
- It's awesome collaborative community  


Within 9ms it renders the whole content for me again. I am literally like **WOW**

![WOW! HUGO IS AWESOME](../wow.gif)
This was me after seeing the rendering time and speed of hugo.

Click [here](https://www.youtube.com/watch?v=w7Ft2ymGmfc) to see how you can create a functional site with [Hugo](https://gohugo.io) under 2 minutes.


## Let's get started with Hugo

Enough of the talk. Let's get to the real thing here.

### Downloading and Installing Hugo
Installing hugo is relatively easy and you have to deal with less **CLI** sometimes when intalling Hugo. It's also really cool to install it too. You can go to [Hugo Release Page](https://github.com/spf13/hugo/releases) and download the binary for your computer depending on your Operating System version. You can also compile the source code yourself but we won't go into that *Nittttty Grittty*.

Note: At the time of the writing this the current Hugo release is [v0.15](https://github.com/spf13/hugo/releases/tag/v0.15).

The installation process, as you know, varies depending upon the operating system but it's relatively simple. For me it was just a couple of clicks and I am using [KUbuntu 15.10](https://kubuntu.org/)


### Setting up a new blog

It couldn't have been simpler than what Hugo has made it for us. Let's setup a blog called **My desi journeys**. Here we'll post our desi journey.

You can play with Hugo yourself and explore all the options Hugo provide by typing
```bash
hugo help
```
or better you can go to [Hugo Docs](https://gohugo.io/overview/introduction/) for details and instructions on pretty much everything about Hugo


So to start with our desi journeys we'll type
```bash
hugo new site "my-desi-journey"
cd my-desi-journey
```
this will generate the bare bones of our hugo static site in a directory `my-desi-journey` and `cd` will change our `working directory` to this blog. Now let's create a new post. This is also relatively very simple
```bash
hugo new welcome/content.md
```
a `welcome` folder will be generated in the `content` folder. This folder is what hugo calls section and contains our `markdown` files. To read more about them go [here](http://gohugo.io/content/sections/)

If you are not familiar already with Markdown you should be. It's the thing these days but the great thing is it's also very simple. Click [here](http://git.io/vCMcp) to read more about it.

You will notice something like this on top of `content.md`
```toml
+++
date = "2016-01-01T12:39:20+05:00"
draft = true
title = "Welcome"
+++
```
This is not very markdown style in my honest opinion. This is called Front Matter in this case it's [TOML](https://github.com/toml-lang/toml). Front matter will contain your post meta data such as title, date etc. Read more about Front Matter [here](http://gohugo.io/content/front-matter/)

Down below the front matter you can add standard markdown finally. For this blog post I am adding this

```md
# Welcome to a blog about my desi journeys

This is where we discuss all that desi cool + odd stuff.
OH YES! THIS IS THE SITE!!!
```

So after adding the markdown let's run the very first static version of site. Luckily for editing purposes hugo offers a really reliable and **EXTREMELY FAST** server which also watches for changes as you make them. Pretty cool? Yeah I know 😉😂😉.

So let's run it
```bash
hugo server
```
Now go to to the link it specifies for the running web server and you will see a nice clean blank HTML page. That's all good but where's the content. This is where Hugo themes come in the equation. They teach Mr. Hugo some rendering.

### Getting a nice cool Hugo theme

The awesome community of Hugo has made some really cool themes for Hugo. You can go and check'em out here at [themes.gohugo.io](https://themes.gohugo.io) and select the one you really love ❤️ ❤️ ❤️ .
I am using [**ALLEGIANT**](https://themes.gohugo.io/allegiant/) the same one as this blog.

Let's  execute some commands to use this theme
```bash
mkdir themes
cd themes
git clone https://github.com/brycematheson/allegiant.git
cd ..
```

The first command will create a themes directory. We then change our `working directory` to this directory.
After that third command will clone the `allegiant` themes repository in the local themes folder.

Executing this will use the allegiant theme and build the drafts too
```bash
hugo --theme=allegiant --buildDrafts server
```
Now if we go on to our web server. We can see our beautiful site with some content too.
That's pretty nice.

### Configuring our hugo blog
There are some changes you still have to make to the blog hugo generated for you. You have to especially change the configurations. Modifying the `config.toml` will do it. The `config.toml` contains values for different variables our hugo blog uses for generating the static content.
I have modified `my-desi-journey` configuration file to look like this

```toml
baseurl = "https://abdulhannanali.github.io/my-desi-journey"
languageCode = "en-us"
title = "My open source journey"
author = "Hannan Ali"
copyright = "Site Licensed under GNU GPL V3.0"
canonifyurls = true
```

You can also specify the theme in the configuratin file by adding the line below
```toml
theme = "allegiant"
```
This will save you the hassle of specifying the same theme in the command line each time you run your Hugo Server.

These are the configurations which are necessary in most cases. `allegiant` also has it's own configurations variables which you can set too. Read about configuring allegiant [here](http://themes.gohugo.io/allegiant#configuration)

To read more about configurations and what else can you do with them click [here](http://gohugo.io/overview/configuration/)

### Generating static content for uploading

Now there's just one step left, generate the static content to upload to our site. This is done by omitting `server` keyword from the command we used above
```bash
hugo --theme=allegiant --buildDrafts
```

You will have a `public` folder generated in your hugo blog root directory. The contents of this `public` folder are what we need to upload to the static server in order to display it's contents. We are done here YAYYY! You have your very own cooked desi blog. Congrats!

![WOOO!](../woo.gif)


### Source code and Hugo Docs
I have made the source code of my-desi-journey available on Github if you want to take a look. Here is the repo [link](https://github.com/abdulhannanali/my-desi-journey). Also don't forget to check out the [hugo docs](https://docs.hugo.io).


![Hugo Image](../images/hugo.png)
