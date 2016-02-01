

Simple Introduction to Git
 
**Install**:
* **OSX** (requires Brew - for a tutorial on installing brew look here: http://brew.sh/)

  * In the command line simply enter:
    ```
    brew install git
    ```

* **Linux/Unix**
  ```
  sudo apt-get install git
  ```


* **Windows**

  * Download and follow install instructions here (BASH shell version): https://msysgit.github.io/


**Setup**:

1. The first thing you will want to do is set your global username and email (at the terminal type the following)
 
  ```
  git config --global user.name "Your Name Comes Here"
  git config --global user.email "Your email goes here"
  ```
2. Next, you will want to setup a project and initiate git
  * This can be done in two ways
    * cloning a repository/project to your local machine
      ```
      git clone your-git-repo-url-here
      ```
    * initializing git in a folder that contains your project
      ```
      git init
      ```


**Workflow in git**

1. The local repository on your machine consists of three basic tree-like structures
  * The first is your working directory which holds all of the files
  * The second is the Index which is the staging area 
  * The last is HEAD which simply points to your last commit

 
**General usage**: (tracking changes, committing, and pushing/pulling)

* Once you have a project with git initialized, you can check the current tracking status of files in that directory by typing
  ```
  git status
  ```
  
* If a file has changes you can have git add it to the tracked changes by typing
  ```
  git add your-file-name-here
  ```
  
* (To add all untracked files): 
  ```
  git add *
  ```
  
* After you have all the files you want to track added you can commit those changes with
  ```
  git commit -m "Your commit message  here"
  ```

* Once you are ready to push and you have committed your changes simply type
  * If you are already tracking a remote (happens automatically when cloning): 
    ```
    git push origin master
    ```

  * If you need to push to a new repository (when you initialize a new project):
    ```
    git remote add name-here url-here  
    ```
      * The URL you can get after you create a new repository on the GitHub website (or whatever git hosting site you use). 

* If you use a repository that others make changes to, you will at some point need to get those changes from the remote server. This is accomplished with the pull command
  ```
  git pull
  ```
  * Assuming no conflicts are present (you both edited the same line of a file etc), this automatically takes care of merging for you and updates all your files in the project.

**Adding an existing project to GitHub**
* The first step is to create a new repository on GitHub. To avoid errors, do not initialize the new repository with a README, license, or gitignore files (these can all be added later).
  * In the upper-right corner of any page, click +, and then click **New Repository**
  * When you are finished selecting the options for the repository select **Create Repository**
* Next navigate the current working directory to your local project. 
* Initialize the local directory as a Git repository
  ```
  git init
  ```
  
* Add the files in your local repository you wish to push to git (this stages them for the first commit).
  ```
  git add .
  ```
  
* Commit the files that you have just staged
  ```
  git commit -m "Commit Message"
  ```
  
* Add the URL for the remote repository to which your local repository will be pushed.
  ```
  git remote add origin remote_repository_URL
  # This sets the new remote
  git remote -v
  # This verifies the new remote URL
  ```
  
* Last, simply push your changes!
  ```
  git push origin master
  ```
  
**Git Tagging / Releases**
* A tag is created to point to a specific commit and does not change afterwards, even if the branch moves on. This means tags are immutable references.
* There are two types of tags that one can create with git
  * The first is called a lightweight tag and can be created as follows (where tag-name can be something like v0.1, beta release one, etc):
    ```
    git tag tag-name-here
    ```
    
  * The next type is called an annotated tag and can be created as follows:
    ```
    git tag -a v1 -m "Version 1 release"
    ```
    
* To push tags to your remote, you can do two things

  * To push only a specific tag use (a standard git push will not push tags):
    ```
    git push tag-name
    ```
    
  * To push all tags at once use:
    ```
    git push --tags
    ```

* To pull tags from your remote, you can again use two methods

  * To pull only a specific tag use:
    ```
    git fetch tag-name
    ```
    
  * To pull all the tags at once use:
    ```
    git fetch --tags
    ```

