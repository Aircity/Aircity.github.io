# Catman

Catman is a responsive theme for Hexo based on [Pacman](https://github.com/A-limon/pacman).

[Demo](http://blog.leafh.pw/catman/) || [Leaf's Blog](http://blog.leafh.pw/)

##Installation
###Install
```
$ git clone https://github.com/leaf-hsiao/catman.git
```
**Catman requires Hexo 2.7 and above.** 
###Enable
Modify `theme` setting in blog folder` _config.yml` to `catman`.
###Update
```
cd themes/catman
git pull origin master
```
**please backup your `_config.yml` file before update.** 
##Configuration

Modify settings in  `/themes/jacman/_config.yml`. 
```
##### Menu
menu:
  Home: /
  Archives: /archives
  Tags: /tags
  Categories: /categories
  About: /about
## you can create `tags` and `categories` folders in `../source`.
## And create a `index.md` file in each of them.
## set `front-matter`as
## layout: tags (or categories)
## title: tags (or categories)
## ---

#### Widgets
widgets: 
- tagcloud
- rss
- category
- tag
- links
## provide six widgets:category,tag,rss,archive,tagcloud,links.
## modify links in `/layout/_widget/links.ejs`.

#### RSS
rss: /atom.xml## RSS address.

#### Image
imglogo:
  enable: true             ## display image logo true/false.
  src: img/logo.svg        ## `.svg` and `.png` are recommended,please put image into the theme folder `/catman/source/img`.
favicon: img/favicon.ico   ## size:32px*32px,`.ico` is recommended,please put image into the theme folder `/catman/source/img`.     
apple_icon: img/catman.jpg ## size:114px*114px,please put image into the theme folder `/catman/source/img`.

#### Author Avatar Picture
author_img_enable: true ## display author avatar picture
dataURI: false
## if the picture's format is dataURI please set the value to true,otherwise set the value to false.
## convert an image into base 64 data URIs http://websemantics.co.uk/online_tools/image_to_data_uri_convertor/ .
author_img_data: ''
## paste the dataURI in ONE LINE and included it by ''.
author_img: img/author.jpg ## size:220px*220px.
## if the picture's format is `.png` or `.jpg`  instead of dataURI,you should set the `dataURI` value to false.

#### Font
ShowCustomFont: true  
## you can change custom font in `variable.styl` and `font.styl` which in the theme folder `/catman/source/css`.

#### Toc
toc:
  article: true   ## show contents in article.
  aside: true     ## show contents in aside.
## you can set both of the value to true of neither of them.
## if you don't want display contents in a specified post,you can modify `front-matter` and add `toc: false`.

#### Fancybox
fancybox: false
## if you use gallery post or want use fancybox please set the value to true.
## if you want use fancybox in ANY post please copy the file `fancybox.js`.
## in theme folder `/catman/scripts` to your hexo blog folder `../scritps`.

#### Author information
author:
  google_plus: ## eg:106117262320878386876 for https://plus.google.com/u/0/106117262320878386876
  intro_line1: ## eg: "Math&Code"
  intro_line2: ## eg: "Photo&Music"
  weibo: ## e.g. leafhsiao for http://weibo.com/leafhsiao
  twitter: ## e.g. LLLLeaf for https://twitter.com/LLLLeaf
  github: ## e.g. leaf-hsiao for https://github.com/leaf-hsiao
  facebook: ## e.g. leaf.hsiao.9 for https://favebook.com/leaf.hsiao.9
  tsina: ## e.g. leafhsiao  Your weibo ID,It will be used in share button.
  linkedin:  ## e.g. in/jeffweiner08 for https://www.linkedin.com/in/jeffweiner08

#### Comment
duoshuo: 
  enable: false ## duoshuo.com
  short_name: ## duoshuo short name.

#### Share button
jiathis:
  enable: false ## if you use jiathis as your share tool,the built-in share tool won't be display.
  id:    ## e.g. 1501277 your jiathis ID. 
  tsina: ## e.g. 1664838973 Your weibo id,It will be used in share button.

#### Analytics
google_analytics:
  enable: false
  id:   ## e.g. UA-1766729-8 your google analytics ID.
  site: ## e.g. yangjian.me your google analytics site or set the value as auto.
## You MUST upgrade to Universal Analytics first!
## https://developers.google.com/analytics/devguides/collection/upgrade/?hl=zh_CN
baidu_tongji:
    enable: false
    id: ## e.g. 24acf16ea7dbfdbf06706025545fab07 your baidu tongji id

#### Custom Search
google_cse: 
  enable: false
  cx: ## e.g. 017960104424732819065:ypw4slmkl7g your Custom Search ID
## https://www.google.com/cse/ 
## To enable the custom search You must create a "search" folder in '/source' and a "index.md" file
## set the 'front-matter' as
## layout: search 
## title: search
## ---
swift_search:
    enable: false
  id: ## e.g. sSFdHE8NyqRzN9ytSTQd your Custom Search ID

#Mathjax
mathjax: false
# Add
# mathjax: true
# in the 'front-matter' if you need that
```
