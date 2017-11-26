# How to contribute

Your contribution is essential for building a complete list of Star Wars
characters. We could of course create a script to automatically extract
the list of characters from some place (pretty sure there are many such 
listings), but the purpose of this repository is to practice the collaboration
models in github.

We want to keep it as easy as possible to contribute changes, and there are a 
few guidelines that we need contributors to follow so that we can have a chance
of keeping on top of things.

## Getting started

* Make sure you have a [GitHub account](https://github.com/signup/free)
* Read through these contributing guidelines
* Ensure that there isn't already a pull request or issue that handles your issue/
contribution

## Making changes

* Fork the repository on GitHub
* Clone the repository on your machine from the shell

  ```
  git clone [path_to_forked_repository]
  ```
  
* Create a topic branch from the `master` branch in the forked repository

  ```
  git checkout -b [name_of_your_new_branch] master
  ```
  
* Make changes and test them
* Make commits of logical units and follow our commit message guidelines
  * If your change is simple, just write a one-liner (header)
  
    ```
    git commit -m "[brief_change_description]"
    ```
  * Git commit message guidelines:
    * use the imperative, present tense: "Create" not "Created" nor "Creates"
    * capitalize first letter
    * no dot (.) at the end
  * If you need to describe in more details what the change is about, then
  remove the `-m` and an editor will open for you to add a the one-liner 
  (header) plus a more detailed explanatory text. Try to keep it under
  100 characters.
  
    ```
    git commit
    ```
* Push your branch to GitHub in the forked repository

  ```
  git push origin [name_of_your_new_branch]
  ```
  
* In GitHub, submit a pull request to the `master` branch of this repository

The core team will look at Pull Requests on a regular basis and provide feedback if needed. 
If changes are required, make the updates, test, and push changes to the branch. This will
update what is included in the pull request.

## After the pull request is merged

When the pull request has been merged in the original repository, you will probably
want to clean things up and ensure you got the latest changes on your machine.

* Delete the topic branch on GitHub either through GitHub or your local shell

  ```
  git push origin --delete [name_of_your_new_branch]
  ```
* Check out the master branch

  ```
  git checkout master -f
  ```
* Delete the local branch

  ```
  git branch -D [name_of_your_new_branch]
  ```
* Update your master with the latest upstream version

  ```
  git pull --ff upstream master
  ```

## Additional Resources

* [General GitHub documentation](https://help.github.com/)
* [GitHub fork a repo documentation](https://help.github.com/articles/fork-a-repo/)
* [GitHub pull request documentation](https://help.github.com/articles/creating-a-pull-request/)
