---
layout: post
title: "Setting up a Blog using Octopress and Github for Dummies"
date: 2014-07-31 00:49:21 -0700
comments: true
categories: 
---
I always wanted to setup a technical blog but after a long time I found a great blog today which had  step by step instructions to create a blog using Octopress with Github Page - http://code.dblock.org/octopress-setting-up-a-blog-and-contributing-to-an-existing-one .  
After reading the blog I was very much motivated to create my own blog. I am not planning to copy the steps from the link pasted above but instead I am going to paste all the commands from my history and explain the steps. 

Installation 
============

Step 1: Create a new Repo in Github

You can create a blog thats available at username.github.io . So first go to your github repository and create a repository with the name username.github.io .  After you create a repo a success screen will pop up with some commands. Just copy the following lines and paste it in textedit or textmate.

```plain github

Push an existing repository from the command line

git remote add origin git@github.com:arunpn/arunpn.github.io.git
git push -u origin master

```

Step 2: Download Octopress and install it

```plain github https://github.com/imathis/octopress
git clone git://github.com/imathis/octopress.git octopress
cd octopress/
bundle install
bundle exec rake install

```

Step 3: Setup Octopress to point to your git repo


```plain github 

rake setup_github_pages
```
When prompted for the repository url paste the address that was copied in Step 1

Repository url: git@github.com:arunpn/arunpn.github.io

```plain
rake setup_github_pages
Enter the read/write url for your repository
(For example, 'git@github.com:your_username/your_username.github.io.git)
           or 'https://github.com/your_username/your_username.github.io')
Repository url: git@github.com:arunpn/arunpn.github.io
Added remote git@github.com:arunpn/arunpn.github.io as origin
```

Step 4: Update _config.yml with blog title , author , why , when , etc

```plain
mate _config.yml
```

Step 5: Create a new Post

```plain 
rake new_post["Test Post"]
rake generate
rake preview
```

To view the preview of the blog , point your browser to http://localhost:4000/

Step 6: Commit your changes in Git and push it to Git Repo in github.

```plain 
git add .
git commit -m "Test blog post."
git push origin source
rake deploy
```
Give yourself 10 mins and you should see your new blog at username.github.io

Step 6: To update the same post

Open the file  source/_post/ file name and edit it. Then

```plain
rake preview 
git add .
git commit -m "Updating a post"
git push origin source
rake deploy
```

Step 7: Optional customization for Google Analytics and Discus for comments

Signup for Google Analytics and get your tracking id  
Signup for Discuss and get your discus short name   
Finally update _config.yml

```plain
# Disqus Comments
disqus_short_name: <your discuss short name>
disqus_show_comment_count: false

# Google Analytics
google_analytics_tracking_id: <your google analytics tracking id>
```


More Links -   
You can learn blogging basics at - http://octopress.org/docs/blogging/   
You can learn code highlight at - http://octopress.org/docs/blogging/code/

Happy Blogging.




