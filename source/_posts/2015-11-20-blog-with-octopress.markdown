---
layout: post
title: "Blog with Octopress"
date: 2015-11-20 05:46:05 -0800
comments: true
categories: 
---

## Step 1 Register an account at github
## Step 2 Install Octopress
### Install git and Ruby
{% codeblock lang:bash %}
sudo apt-get install git ruby ruby-dev
{% endcodeblock %}
### Install Octopress
{% codeblock lang:bash %}
git clone git://github.com/imathis/octopress.git octopress
cd octopress 
ruby --v
{% endcodeblock %} 
This should print out Ruby 1.9.3
### Install dependencies
{% codeblock lang:bash %}
gem install bundler
bundle install
{% endcodeblock %}
### Install the default theme
{% codeblock lang:bash %}
rake install
{% endcodeblock %}
## Step 3 Deploy to github
### Create a new repository: username/username.github.io
### Deploy
{% codeblock lang:bash %}
rake setup_github_pages
{% endcodeblock %}
This will ask for the address of the repository you just created, simply follow the tip.
{% codeblock lang:bash %}
rake generate
rake deploy
{% endcodeblock %}
These two commands will generate a blog for you.
### Commit the source for your blog
{% codeblock lang:bash %}
git add .
git commit -m 'your message'
git push origin source
{% endcodeblock %}
## Step 4 Publish a blog
{% codeblock lang:bash %}
rake new_post["Your First Blog"]
{% endcodeblock %}
This line will create source/_posts/2015-11-20-your-first-blog.markdown file for you with the following content:
{% codeblock lang:bash %}
---
layout: post
title: "Your First Blog"
date: 2011-07-03 5:59
comments: true
external-url:
categories:
---
{% endcodeblock %}
You can switch the comment function on/off here. And if there are more than one author, you can add `author: Your name`. If you are editing a draft, you can add `published: false`.
## Step 5 Generate and preview
{% codeblock lang:bash %}
rake generate
rake preview
{% endcodeblock %}
## Step 6 Push to github
{% codeblock lang:bash %}
rake generate
rake deploy
git add .
git commit -m 'Your message'
git push origin source
{% endcodeblock %}





