---
layout: single
title: How to permanently save Github credentials on Cloud 9
categories: Coding
tags: 
- Cloud9
- Github 
---

How to save Github credentials on Cloud9?
<br />
Steps:
1. Git clone the repo into C9 using the SSH link, not the HTTPS link.
![Clone with SSH link]({{ site.url }}/assets/posts/2017-10-1-SaveGithubcredentialsonC9/cloneSSH.png)
2. Go to c9.io/account/ssh and copy the SSH key.
3. Go to github.com/settings/keys. Click on new SSH key button.
4. Paste in the copied SSH key
5. Go back to your project on C9.io. If you have already clone your project using
the HTTPS link, type in the following command in the cmd line.
```
git remote set-url origin git@github.com:username/projectname.io.git
```
where the SSH clone link replaces the part "username/projectname.io.git".
<br />
<br />
That is all.