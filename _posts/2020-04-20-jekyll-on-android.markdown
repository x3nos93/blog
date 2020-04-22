---
layout: post
title:  "Jekyll on Android Without Root - Part 1"
date:   2020-04-20 04:20:00 -0600
categories: jekyll ruby github blogging
---

First you will need to install Termux on your Android device. Once it is installed open a terminal window and enter the following commands to install the prereqs for Jekyll.
```terminal
pkg install autoconf build-essential
```
```terminal
apt update && apt-install libffi clang ruby make
```

Next, we are going to install Jekyll 3.8.5. I tried installing 4.0.0 but ran into several compatibility issues on the android so we will downgrade to the previous stable release which is Jekyll 3.8.5.

Before we do that however, you will want to navigate to your home dir and creating a new working directory for your site.  You can call this whatever you like.

Once you have created the dir, cd into it and install jekyll.
```terminal
cd working_dir
```
```terminal
gem install jekyll -v 3.8.5
```
Next we are going to create the Jekyll site by invoking ```jekyll new```.

```terminal
jekyll new site_name
```
Be sure to change directories into the site directory you just created during the new site build.
```terminal
cd site_name
```
Next, we need to serve up the site on localhost.
```terminal
bundle exec jekyll serve
```
Now you should be able to open a browser on your local android host and navigate to http://127.0.0.1:4000 or http://localhost:4000.

![Jekyll Running on Android](/assets/2020-04-20.png)

Up next in part 2, we will explore editing the ```_config.yml``` and creating your first blog post!

<!---
You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. You can rebuild the site in many different ways, but the most common way is to run `jekyll serve`, which launches a web server and auto-regenerates your site when a file is updated.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll-docs] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll Talk][jekyll-talk].

[jekyll-docs]: https://jekyllrb.com/docs/home
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-talk]: https://talk.jekyllrb.com/

--->
