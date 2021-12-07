---
title: "Hugo"
date: 2021-10-04T20:48:19-05:00
draft: false
---

### What is this thing?

Hugo is the worlds fastest framework for building websites. In simple terms, it is a static site generator. 
You choose a theme and then write some markdown and hugo whips up all the HTML, CSS and JavaScript your
site needs to function. 

The blog site you are looking at right now was generated with hugo in about 62ms!

### What is that markdown thing?

Markdown is a simple way to have a page formatted without having to know all of the various HTML bits to do so. 
For example, the 'code' below...

```markdown
#### This is a test
Cool it *works*
> This is a block quote
---
```
renders like this...

#### This is a test
Cool it *works*
> This is a block quote
---

### How do I use it here?

Hugo is already installed on this system and is ready to be served up from your home directory. Here is a small script
to get you started!

```bash
#!/bin/sh

cd ~/
mkdir www
chmod 755 www
hugo new site my-site
cd my-site
git clone https://github.com/panr/hugo-theme-terminal.git themes/hugo-theme-terminal
cp -R themes/hugo-theme-terminal/exampleSite/* .
# Config file changes
sed -e "s/example.com/2243.cit.fyi\/~$USER/" \
    -e 's/orange/pink/' \
    -e "s/\"\/\"/\"\/\~$USER\"/" config.toml > cfg.tmp
mv -f cfg.tmp config.toml
# Fix for cover image
sed -e 's/hello.jpg/img\/hello.jpg/' content/post/hello.md > hello.tmp
mv -f hello.tmp content/post/hello.md
hugo new post/my-first-post.md
ln -s ~/www ~/my-site/public
hugo -D
echo ""
echo "Your new site is now live @ https://2243.cit.fyi/~$USER"
echo ""
echo "Some Useful Hugo Commands"
echo "hugo help                : Show Hugo's help"
echo "hugo new post/<title>.md : adds a new post to the site with a title of <title>"
echo "hugo -D                  : causes hugo to generate the site files"
echo ""
```
This script will start you off with the terminal theme. For more details check out the docs here:
https://themes.gohugo.io/themes/hugo-theme-terminal

or visit the main site https://gohugo.io/