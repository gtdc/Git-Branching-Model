```
Paper here: http://nvie.com/posts/a-successful-git-branching-model/

Summary of above paper:

In the below example we are going to pretend to create an issue 1000 and then show the steps needed to create a remote branch, work on it, and delete it. Although the following steps show how to work on issue 1000, the following steps will work for any issue number!

    * `master` = branch only with releases that are working

    * `develop` = branch to merge all issue branches to make sure everything is working before
      pushing to the master branch
      
      * `issue-number`
        
        * Step 0) `cd` into wAlnut folder
        * Step 1) first move to develop branch = `git checkout develop` and make sure you have the most
          recent version of develop with `git pull origin develop`
        * Step 2) creating a new branch = `git checkout -b issue-1000 develop`
          
          * Example command: `git checkout -b issue-1000 develop`
        * Step 3) push for the first time with -u = `git push -u origin issue-1000`
        * implement your issue :) You will spend most of your time here...
          
          * Step 4) `git add .` = add all changes you have made since last commit
          * Step 5) `git commit -m "what changed"`
          * Step 6) `git push origin issue-1000`
          * Step 7) Repeat steps 4 to 6 until done with issue.
        * make commits and push to your issue branch frequently
        * ending issue branch =
          
          * Step 8) `git checkout develop`
          * Step 9) `git pull origin develop` = make sure you have the MOST recent version of develop branch
          * Step 10) `git merge --no-ff issue-1000` = --no-ff causes merge to always create a
            new commit object so we don't lose the
            info that this once was a issue branch
          * Step 11) `git push origin develop` = oh sh!t your code is on
            https://github.com/quinnliu/WalnutiQ/tree/develop now
          * Step 12) `git checkout master` and `git pull origin master`
          * Step 13) `git merge --no-ff develop`
          * Step 14) `git push origin master`
          * Step 15) `git branch -d issue-1000` = delete local branch issue-1000
          * Step 16) `git push origin --delete issue-1000` = delete remote branch issue-1000
          ```