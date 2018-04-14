---
layout: post
title: Simple cmds for using git and github
---

It is not long since I started my computer science program so I didn't get a chance to collaborating with other programmers and show up in a project.

This semester I started to do some experiments following one professor. I think doing experiment is a good starting point before digging into real research. Also this gives me a great opportunity to learn how to use Github to share.

The project has already had all require functionality implemented and what I am going to do is to modify using new heuristic and check the running time. If the running time decreases significantly, then I do the following experiment to check whether other costs.

This [article](http://dont-be-afraid-to-commit.readthedocs.io/en/latest/git/commandlinegit.html) helped a lot.


To start with, clone the existing repository:

```
git clone the/url/of/the/repository
```

Next, create a new branch for my own experimet because I am not going to interfere with others' work or ruin the whold project. Here `git checkout -b` creates a new branch and switches to it.

```
git checkout -b my_branch_name
```

Then I can do whatever I want under this branch. Just remember to check the modified code and commit them in the end:

```
git status
git add modified/code/in/your/branch
git commit -m "What I have done to this branch"
git push origin my_branch_name
```

This will go under this branch without interfering with the master.

To keep updated with the repo:

```
git pull
```

Also, when I finished changing codes, I may send Professor a pull request. But so far, my codes are still in this branch.


<!--![Image description](/images/my-image.jpg)-->

<!--Next you can update your site name, avatar and other options using the _config.yml file in the root of your repository (shown below).-->

<!--![_config.yml]({{ site.baseurl }}/images/config.png)

The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.-->