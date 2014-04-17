# Git Handbook

### Creating a new repo
1. First create a new repo on GitHub. [More information](https://help.github.com/articles/create-a-repo)

2. In Terminal, navigate to the root directory of the project that you want create the repo from. 
    
  In terminal, you can use `cd` to change your current working directory. For example `cd Desktop` will change the current working directory to your desktop if you are in your home directory. 
    
  If you are unsure what directories you can access from the current working directory, then you can use `ls` to list the contents of a directory.

3. Once your current working directory is your project root, then you can initialize the git repo by running: 
	```sh
	git init
	```

4. Next you need to add your project files to be staged for the next commit. If you want to add all files within the project project directory and child directories then you can run:
	```sh
	git add .
	```
	#### Or...
	If you only want to add individual files, you can run `git add` followed by the filename. 
	```sh
	git add index.html
	```

5. After you have staged you changes, the next step is to commit them by running `git commit` and including a commit message. 

	What you include in your commit message is up to you. A good commit message should tell you what you changed, if you were to come back to this project in 6 months time. For example:
	```sh
	git commit -m "Changed color scheme"
	```

6. In order to push your changes to the remote repo on GitHub you will first need to tell your local repo where the remote repo on GitHub is. In the example below, we are creating a new remote repo with the git URL and assigning it the name 'origin'
	```sh
	git remote add origin https://github.com/username/repo-name.git
	```
  *Note that you need to use the remote repo URL, for your repo, that you created on GitHub*

7. Once your local repo knows where the remote repo is on GitHub, and you have changes committed and ready to push to the remote repo, then you can run the following command in Terminal to push the changes. 
  
	In the example below we are pushing changes to the remote repo we created in step 6 and ensuring the changes go the the (default) master branch.
	```sh
	git push origin master
	```
	*You may need to enter your Github username and password in order to complete this step.*

8. You local project should now be on GitHub. You can check that you project files and changes have successfully be push to Github by visiting the GitHub repo page (e.g. https://github.com/username/repo-name). 

9. #### Relax, your code is now being version tracked.

### Pushing changes to an existing repo
1. Add or remove changes to be staged for commit

  To stage the addition of all new and modified files, you can run:
  ```sh
  git add .
  ```
  #### Or...
  To stage the addition of an individual file, you can run:
  ```sh
  git add index.html
  ```
  *In the above example replace the index.html with the name of the file you want stage the addition of.*
  #### Or...
  To stage the remove of an individual file, you can run:
  ```sh
  git rm index.html
  ``` 
  *In the above example replace the index.html with the name of the file you want stage the removal of.*
  
2. Commit the changes, with a message that describes the change.
  ```sh
  git commit -m "Included jQuery slider"
  ```

3. Push the changes to the remote repo on GitHub
  ```sh
  git push origin master
  ```
  *In the above example, 'master' is the name of the branch on the remote repo that you want to push your changes to.*

### Using additional branches created on GitHub
If you create additional branches directly on Github and need to use them locally on your development machine, you need fetch changes to structure of the repo before you can use them.

1. Fetch changes from the remote repo
	```sh
	git fetch origin
	```

2. To change branches you can use the `git checkout` command:
	```sh
	git checkout gh-pages
	```
	*In the above example, 'gh-pages' is the name of the remote branch that you want to create locally*

3. You have now created and changed to the a local branch of the remote branch you want to make changes to. You can follow the steps in 'Pushing changes to an existing repo' to push changes to the branch.

  *Note: when pushing to the remote repo you will need to specify the name of the branch you want to push the changes to. For example, to push changes to the 'gh-pages' branch you can run: *
  ```sh
  git push origin gh-pages
  ```

4. If you need to check which branch you are on you can run `git branch` which will produce an output similar to the below, where the selected branch is identified with a `*` in front of the branch name.
	```sh
	  * master
	     gh-pages
	```

### Cloning a repo
To copy an existing repo to your local machine (for example, to access and update your repo from another computer) you run `git clone` followed by the git url of the existing repo.

```sh
git clone https://github.com/username/repo-name.git
```

Using this technique you can download public repos for existing libraries and frameworks such as jQuery, Lightbox2, Foundation, etc...

### Merging branches
*To be completed...*