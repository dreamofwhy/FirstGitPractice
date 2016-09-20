FirstGitPractice
================

A repository to use to get familiar with Git and GitHub


##Preliminary work##

Complete the following online exercise: https://try.github.io/levels/1/challenges/1

## In Class ##

###Linux###

  0. Open a terminal
  1. Make sure git is installed.
  2. Generate SSH keys to use with GitHub.
    * Step 1: [Generate Keys] (https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux)
    * Step 2: [Add key to GitHub] (https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/#platform-linux) 
    * This is a per-machine operation or you need to copy around your SSH keys (`~/.ssh/id_rsa`) to each machine you use!
  3. Stop.


### In your web browser ###
1. Log into GitHub.

2. Fork the cs360f16/FirstGitPractice repository.  cs360f16/FirstGitPractice is the `upstream` repository.  The forked copy will be the `origin` repository.

3. In your forked copy, use the online file editor in your web browser to edit dataFile.md.
This is a file of favorite movies and/or songs.  Make sure you provide a good commit message and look at the [GitHub flavored markdown](https://help.github.com/articles/github-flavored-markdown) and [Markdown Basics](https://help.github.com/articles/markdown-basics)

4. Issue a pull request back to the original repository.  Green button at the top left.

5. Review at least one other student’s pull request to indicate if that student followed directions correctly.   Do this by navigating back to cs360f16/FirstGitPractice and looking through the pull requests.

6. Wait for a few minutes for your pull request to get accepted back to the upstream repository and for everyone to catch up.

### From the GitHub Shell or command line: ###
0. Do not copy and paste these commands.  The " and " do not copy well.

1. `git clone git@github.com:USERNAME/FirstGitPractice.git`

2. `cd FirstGitPractice`
  2. `ls -al` - see the files in this directory
  2. `cat dataFile.md` -  list the contents of the file dataFile.md
 

3. `git remote add upstream git@github.com:cs360f16/FirstGitPractice.git`

4. `git fetch upstream`

5. `git merge upstream/master`
  5. `ls -al`
  5. `cat dataFile.md`

6. Edit dataFile.md with Geany to add a second favorite movie.

7. `git add dataFile.md`

8. `git commit -m “added a second favorite movie”`
You can customize the commit message in this step

9. `git push origin master`

10. ~~`git push upstream master`~~
~~This will generate a pull request back to cs360f16/FirstGitPractice.  You could have done this step in your web browser as you did in step 4.~~  You must generate the pull request from your web browser.

NOTE: Step 4 and 5 could be replaced with the single step:
`git pull upstream master`


##Git with Branches

### From the GitHub Shell or command line: ###
Why would I want to branch?  A branch creates an editable copy of the repository so you can make commits without necessarily putting the commits into the main line of development.  This is good for adding a feature, a bug fix, or some other set of commits that make end up as a pull request back to another Git repository.  

The last reason, for a pull request, is especially important.  If you make a pull request and the target of the pull request asks you to modify the pull request in any way, you can just make changes on that branch and the pull request is altered.  Once the pull request is accepted, or the changes from the branch are merged back into main, the branch can be deleted (but this is not required).

1. Starting from the directory `FirstGitPractice` again
2. Make sure you are up-to-date.
  * `git fetch upstream`
  * `git merge upstream/master`
    * Resolve conflict if necessary
    * edit file, remove >>> ==== <<< lines
    * `git add ...`
    * `git commit -m "message" `
  * `git push origin master`
2. `git branch AddAuthors_PUNetID`
3. `git checkout AddAuthors_PUNetID`
4. Use Geany to edit dataFile.md and add your favorite author to the end of the file
5. `git add dataFile.md`
8. `git commit -m “added an Author”`
You can customize the commit message in this step
9. `git push origin AddAuthors_PUNetID` Push the commits from AddAuthors branch to `origin`.  **Also:** Generate a pull request to cs360f16/FirstGitPractice from your web browser if one is not automatically generated.
10. Go look at your pull request on the AddAuthors_PUNetID branch in cs360f16/FirstGitPractice.
11. Now I want you to change the Author's name to either ALL CAPS or all lowercase letters.  Use Geany to do this locally.
12. `git add dataFile.md`
13. `git commit -m “added an Author ALL CAPS”`
14. `git push origin AddAuthors_PUNetID`
15. Go look at your pull request on cs360f16/FirstGitPractice.  Does it reflect the new commits?  
16. Wait for the pull request to get accepted.
16. `git checkout master`  You may see the following error. That is acceptable.
```
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
```
17. `git fetch upstream master` Get changes from the group repository
18. `git merge upstream/master`
18. `git branch -d AddAuthors_PUNetID`
19. `git push origin master`
20. Optionally delete the `AddAuthors_PUNetID` branch on USER/FirstGitPractice on GitHub.


###Further Documenation###
[Fork A Repo] (https://help.github.com/articles/fork-a-repo)

###A few terms:###
`origin`: git@github.com:USERNAME/FirstGitPractice.git - the address of your GitHub repository

`upstream`: git@github.com:cs360f16/FirstGitPractice.git - the address of the original GitHub repository

`master`: the master branch in the local repository

