FirstGitPractice
================

A repository to use to get familiar with Git and GitHub


##Preliminary work##

Complete the following online exercise: https://try.github.io/levels/1/challenges/1

Prepare either your own laptop or a machine in the CS Lab by doing the following before class:

###Windows###

  
  1. Install GitHub for Windows. You should be able to do this with a non-administrator account.  You can do this in the CS lab.
  2. Connect
    * Give your GitHub account information
    * Login
    * At this point you may receive an email from GitHub indicating that a new public key was added to your account. This is legit.
  3. Configure
    * Your username and email is auto-filled in.
    * Change these values if you need to.
    * Continue
  4. Repositories
    * Skip.

  5. Stop. You are done until class.
    
  You should now have an icon for GitHub and an icon for GitShell on your Desktop.

###Linux###

  1. Make sure git is installed.
  2.  [Generate SSH keys to use with GitHub by following these directions] (https://help.github.com/articles/generating-ssh-keys) Step 4 in the GitHub directions must be successful before class.
  3. Stop. You are done until class.

###Mac###

  I do not recommend using a Mac for this course.  The best option for a Mac is to install either Windows or Linux in VirtualBox.

  If you must use OS X then either follow the Linux instructions above or use the GitHub for Mac application for Mac OS X 10.7 and above.  I have never used GitHub for Mac.


## In Class ##

### In your web browser ###
1. Log into GitHub.

2. Fork the cs360f14/FirstGitPractice repository.  This is the upstream repository.

3. In your forked copy, use the online file editor to edit dataFile.md.
This is a file of favorite movies and/or songs.  Make sure you provide a good commit message and look at the GitHub flavored markdown. https://help.github.com/articles/github-flavored-markdown

4. Issue a pull request back to the original repository.  Green button at the top left.

5. Review at least one other student’s pull request to indicate if that student followed directions correctly.   Do this by navigating back to cs360f14/FirstGitPractice and looking through the pull requests.  The upside-down U icon on the right of the repository.

6. Wait for a few minutes for your pull request to get accepted back to the upstream repository and for everyone to catch up.

### From the GitHub Shell or command line: ###

1. `git clone git@github.com:USERNAME/FirstGitPractice.git`

2. `cd FirstGitPractice`
  2. `dir` - see the files in this directory
  2. `cat dataFile.md` -  list the contents of the file dataFile.md
 

3. `git remote add upstream https://github.com/cs360f14/FirstGitPractice.git`

4. `git fetch upstream`

5. `git merge upstream/master`
  5. `dir`
  5. `cat dataFile.md`

6. Edit dataFile.md with Geany to add a second favorite movie.

7. `git add dataFile.md`

8. `git commit -m “added a second favorite movie!”`
You can customize the commit message in this step

9. `git push origin master`

10. `git push upstream master`
This will generate a pull request back to cs360f14/FirstGitPractice.  You could have done this step in your web browser as you did in step 4.

NOTE: Step 4 and 5 could be replaced with the single step:
`git pull upstream master`


##Git with Branches

### From the GitHub Shell or command line: ###
Why would I want to branch?  A branch creates an editable copy of the repository so you can make commits without necessarily putting the commits into the main line of development.  This is good for adding a feature, a bug fix, or some other set of commits that make end up as a pull request back to another Git repository.  

The last reason, for a pull request, is especially important.  If you make a pull request and the target of the pull request asks you to modify the pull request in any way, you can just make changes on that branch and the pull request is altered.  Once the pull request is accepted, or the changes from the branch are merged back into main, the branch can be deleted (but this is not required).

1. Starting from the directory `FirstGitPractice` again

2. `git branch AddAuthors`

3. `git checkout AddAuthors`

4. Use Geany to edit dataFile.md and add your favorite author to the end of the file

5. `git add dataFile.md`

8. `git commit -m “added an Author!”`
You can customize the commit message in this step

9. `git push upstream AddAuthors` Push the commits from AddAuthors branch to upstream.  

10. Go look at your pull request on cs360f14/FirstGitPractice.

11. Now I want you to change the Author's name to either ALL CAPS or all lowercase letters.  Use Geany to do this locally.

12. `git add dataFile.md`

13. `git commit -m “added an Author ALL CAPS!”`

14. `git push upstream AddAuthors` 

15. Go look at your pull request on cs360f14/FirstGitPractice.  Does it reflect the new commits?

16. Finally, `git merge AddAuthors` copy the commits from AddAuthors over to main

###Alternate Path ###
You could have also done the following:
1. Starting from the directory `FirstGitPractice` again

2. `git branch AddAuthors`

3. `git checkout AddAuthors`

4. Use Geany to edit dataFile.md and add your favorite author to the end of the file

5. `git add dataFile.md`

8. `git commit -m “added an Author!”`
You can customize the commit message in this step

9. `git push origin AddAuthors` Push the commits from AddAuthors branch to origin.  

10. On the web: Go to your GitHub account and make a Pull Request back to cs360f14/FirstGitPractice

10. Go look at your pull request on cs360f14/FirstGitPractice.

11. Now I want you to change the Author's name to either ALL CAPS or all lowercase letters.  Use Geany to do this locally.

12. `git add dataFile.md`

13. `git commit -m “added an Author ALL CAPS!”`

14. `git push origin AddAuthors` 

15. Go look at your pull request on cs360f14/FirstGitPractice.  Does it reflect the new commits?

16. Finally, `git merge AddAuthors` copy the commits from AddAuthors over to main

###Further Documenation###
[Fork A Repo] (https://help.github.com/articles/fork-a-repo)

###A few terms:###
`origin`: https://github.com/USERNAME/FirstGitPractice.git

`upstream`: https://github.com/cs360f14/FirstGitPractice.git

`master`: the master branch in the local repository

