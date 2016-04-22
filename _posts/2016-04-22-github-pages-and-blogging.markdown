---
layout: post
title: Github Pages and Blogging
date: 2016-04-22T08:59:04-04:00
---

If you guys noticed, I made a couple changes to the overall layout of the blog, and I thought it is high time that I explain how the overall blog is setup. If you didn't realize it by now, my blog is hosted on Github Pages, with the use of a static site generator to make blogging a tad bit easier. Basically, the way it works is I write a post, then build the blog, which compiles the post into a HTML page. 

I write my posts in the form of Markdown, which is a mixture of HTML and plain text. It gives you more control over your text than perhaps you would in plain text, but at the same time it takes a bit more time to pick up. The structure of my directory is quite simple, as shown below:

![Directory](../../../images/directory.tiff)

Any folder with a _ in it will not be included in the final build of the site, which is in the _site folder. And .md file that is not in the posts folder is converted into a HTML page, which is then displayed in my navigation bar.  When I push this repository to github, basically publishing it online, Github displays everything from the site folder onto my domain, which is nostack.github.io. So how do you go about actually setting up a blog like mine? Instructions are as follows:

1. Create a github account, and create a repository named what you want your github pages URL to be, for example nostack.github.io
2. Then clone the repository to your computer.
3. Install jekyll (you can look this up, there are millions of guides).
4. Download a theme for jekyll, or use the sample one.
5. Create a sample post to test if the overall blog works.
6. Push the blog to the repository you had created using terminal or the Github application.
7. Congratulations, your blog is set up!

That is basically how I set my blog up. I had a lot of trouble when I first set it up, so if you need any help be sure to e-mail me! Until next time, ciao!