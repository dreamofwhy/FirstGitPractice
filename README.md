FirstGitPractice
================

A repository to use to get familiar with Git and GitHub.  

**Note:** that GitHub generally guides you through the user interface using `big green buttons`.

**Note:** I don't use `--no-ff` with upstream/master below to simplifiy the history. I recommend that with GitHub, you don't use `--no-ff` in this instance.  If you merge a local branch to master, I would use `--no-ff`

##Preliminary work##

Complete the following online exercise: https://try.github.io/levels/1/challenges/1

## In Class ##

###Linux###

  0. Log into GitHub
  0. Open a terminal
  1. Make sure git is installed.
  2. Generate SSH keys to use with GitHub.
    * Step 1: [Generate Keys] (https://help.github.com/articles/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent/#platform-linux)
    * Step 2: [Add key to GitHub] (https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/#platform-linux) 
    * This is a per-machine operation or you need to copy around your SSH keys (`~/.ssh/id_rsa`) to each machine you use!
    * [Test your SSH keys] (https://help.github.com/articles/testing-your-ssh-connection/#platform-linux).  If you receive an error message let the instructor know.
  3. Stop.


### In your web browser ###
1. Log into GitHub.

2. Fork the `cs360f16/FirstGitPractice` repository.  `cs360f16/FirstGitPractice` is the `upstream` repository.  The forked copy `you/FirstGitPractice` will be the `origin` repository.

3. In your forked copy, use the online file editor in your web browser to edit dataFile.md.
This is a file of favorite movies and/or songs.  Make sure you provide a good commit message and look at the [GitHub flavored markdown](https://help.github.com/articles/github-flavored-markdown) and [Markdown Basics](https://help.github.com/articles/markdown-basics).  
  * Commit directly to master branch.

4. Go back to the forked repository. Issue a pull request back to the `upstream`  repository.  
  * The New Pull Request button on the top left then...
  * Big green button to Create pull request then...
  * Add a short comment. Then press the green Create pull request button.
  * DONE!

5. Review at least one other student’s pull request to indicate if that student followed directions correctly.   Do this by navigating back to [cs360f16/FirstGitPractice] (https://github.com/cs360f16/FirstGitPractice) and looking through the Pull Requests (top left).  Write a comment and if the student's pull request contains an error, Request Changes, if the student's pull request is correct, Approve.

6. Wait for a few minutes for your pull request to get accepted back to the upstream repository and for everyone to catch up.
7. Stop.

### From the command line: ###

0. Do not copy and paste these commands.  The " and " do not copy well.
1. In the following commands, anything past a `#` is a comment for your understanding.

1. `git clone git@github.com:USERNAME/FirstGitPractice.git # clone the repository to your local machine`

2. `cd FirstGitPractice`
  2. `ls -al` - see the files in this directory
  2. `cat dataFile.md` -  list the contents of the file dataFile.md
 

3. `git remote add upstream git@github.com:cs360f16/FirstGitPractice.git # connect your local repos to the shared repos`
4. `git remote -v`

4. `git fetch upstream`

5. `git merge upstream/master`
  5. `ls -al`
  5. `cat dataFile.md`

6. `geany -i dataFile.md & #` Edit dataFile.md with Geany to add a second favorite movie .

7. `git add dataFile.md`

8. `git commit -m “added a second favorite movie” # commit to your local repos`
You can customize the commit message in this step

9. `git push origin master # push your commit to you/FirstGitPratice on GitHub`

10. You must generate the pull request from your web browser.

NOTE: Step 8 and 9 could be replaced with the single step:
`git pull upstream master`


##Git with Branches

### From the command line: ###
Why would I want to branch?  A branch creates an editable copy of the repository so you can make commits without necessarily putting the commits into the main line of development.  This is good for adding a feature, a bug fix, or some other set of commits that make end up as a pull request back to another Git repository.  

**The last reason, for a pull request, is especially important**.  If you make a pull request and the target of the pull request asks you to modify the pull request in any way, you can just make changes on that branch and the pull request is altered.  Once the pull request is accepted, or the changes from the branch are merged back into main, the branch can be deleted (but this is not required).

1. Starting from the directory `FirstGitPractice` on zeus again

2. Make sure you are up-to-date.
  * `git fetch upstream # get commits from the group repository`
  
  * `git merge upstream/master # merge those commits to your local repository`
  
    * Resolve conflict if necessary
    * edit file, remove >>> ==== <<< lines
    * `git add ...`
    
    * `git commit -m "message" # commit to your local repos`
    
  * `git push origin master # push to you/FirstGitPractice on GitHub`
  
2. `git branch AddAuthors_PUNetID # add a branch locally`

3. `git checkout AddAuthors_PUNetID`

4. `geany -i dataFile.md & #` Use Geany to edit dataFile.md and add your favorite author to the end of the file

5. `git add dataFile.md`

8. `git commit -m “added an Author” # commit to your local repos`
You can customize the commit message in this step

9. `git push origin AddAuthors_PUNetID` Push the commits from AddAuthors branch to `origin`.  This creates the branch `AddAuthors_PUNetID` on `you/FirstGitPractice` on GitHub.

10. Generate a pull request to cs360f16/FirstGitPractice from your web browser if one is not automatically generated.  Make sure you are looking at branch `AddAuthors_PUNetID` in your web browser.

10. Go look at your pull request on the AddAuthors_PUNetID branch in [cs360f16/FirstGitPractice] (https://github.com/cs360f16/FirstGitPractice).

11. Now I want you to change the Author's name to either ALL CAPS or all lowercase letters.  Use Geany to do this locally.

12. `git add dataFile.md`

13. `git commit -m “added an Author ALL CAPS” # commit locally`

14. `git push origin AddAuthors_PUNetID # push new commits on this branch to you/GitFirstPractice on GitHub`

15. Go look at your pull request on [cs360f16/FirstGitPractice] (https://github.com/cs360f16/FirstGitPractice).  Does it reflect the new commits?  

16. Wait for the pull request to get accepted.

16. `git checkout master # switch back to the master branch locally`  You may see the following error. That is acceptable.
```
Switched to branch 'master'
Your branch is ahead of 'origin/master' by 2 commits.
  (use "git push" to publish your local commits)
```
17. `cat dataFile.md`

17. `git fetch upstream master # Get changes from the group repository`

18. `git merge upstream/master # merge changes form the group repository to master in the local repos`

17. `cat dataFile.md`

18. `git branch -d AddAuthors_PUNetID`

19. `git push origin master # push the newly received changes from the group repos to you/FirstGitPractice on GitHub`

20. Optionally delete the `AddAuthors_PUNetID` branch on USER/FirstGitPractice on GitHub.


###Further Documenation###
[Fork A Repo] (https://help.github.com/articles/fork-a-repo)

###A few terms:###
`origin`: git@github.com:USERNAME/FirstGitPractice.git - the address of your GitHub repository

`upstream`: git@github.com:cs360f16/FirstGitPractice.git - the address of the original GitHub repository

`master`: the master branch in the local repository

