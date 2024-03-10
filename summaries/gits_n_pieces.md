Alen Sent Us New Things to cry over
---------
**NOTE:**: As a general rule, commit all your working files, so there is less chance something will go hideously wrong

`cd git/pfms-2024a-yourGitUserName`

`git fetch origin subject`

`git merge origin/subject --allow-unrelated-histories`

`git push`

You should now have any new files from Alen `:)`. Cry as required. 


Commiting (not like that...)
---------
Not neccessary, but a good habit, do a pull first 

`git pull`

Check which files have changes (current working files)

`git status`

**Green** - already included in the commit

**Red** - needs to be added

Add any red files/folders to the commit

`git add <file name/path>` 

e.g. if we are adding the week 2 tutorial starter

`git add tutorials/week02/starter`

Now  check again with `git status`, you should see your file is green.

Time to commit (to git)! Include a commit message so you can see on github what is included in that commit.

`git commit -m "Your message here"`

Push it to your repository

`git push`


