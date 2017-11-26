# Tutorial on collaboration models in GitHub

This is a repo for practicing git collaboration models. Feel free to contribute (read the [Contribution Guidelines](CONTRIBUTING.md)).

## Prerequisites

* You have some basic experience using using Git and GitHub and are familiar familiar with concepts like: clone, push, pull, checkout, commit, branch, fork.
* DataCamp’s [Introduction to Git](https://www.datacamp.com/courses/introduction-to-git-for-data-science) free course is good for beginners and also a good review of the basic commands if you feel like you need a refresher.

## Types of collaborative development models

From GitHub's [documentation](https://help.github.com/articles/about-collaborative-development-models/):

* In the **shared repository model**: "collaborators are granted push access to a single shared repository and topic branches are created when changes need to be made."
  * This model is popular with organizations collaborating on private projects
* In the **fork and pull model**: "anyone can fork an existing repository and push changes to their personal fork without needing access to the source repository. The changes can be pulled into the source repository by the project maintainer."
  * This model is popular with open source projects
  
## Workflow

This tutorial will focus on the second type of model, with the aim of giving an introduction to how to contribute to open-source projects.

The basic idea is the following:
* Fork the project
* Make changes
* Perform a Pull Request (PR)

### Step-by-step

* Look for contribution instructions on the repository (usually in a CONTRIBUTING file). 
If available, follow those instructions.
* In GitHub, create a fork of the repository.
* Clone the forked repository on your machine. That forked repo on GitHub is the `origin`.

  ```
  git clone https://github.com/[your_username]/[forked_repo].git
  ```
  
* Add the original repository as a remote called `upstream`. (Check which remotes are defined
with `git remote -v`)

  ```
  git remote add upstream https://github.com/[original_owner]/[original_repo].git
  ```

* Create a new branch. The contribution guidelines usually mention from which branch to 
work on. If none is specified, use `develop` if that is available, otherwise the `master` branch.

  ```
  git checkout -b [name_of_your_new_branch] [upstream_branch]
  ```
  
* Make changes and test them. Keep changes to logical units (otherwise consider multiple Branches/
Pull Requests). Follow the code guidelines (or style, if no guidelines provided), run tests, add 
comments and documentation as needed. 
* Make commits that follow the commit message guidelines. (A good practice is to use the imperative, present tense: "Change" not "Changed" nor "Changes")

  ```
  git commit -m "[brief_change_description]"
  ```
* Some repos guidelines require that the Pull Request contains only one commit, or at least that you keep your commit history clean of unnecessary commits. You can create multiple commits and then squash them into a single one. 
  
  ```
  squash example
  ```

* Push your branch to GitHub in the forked repository (remote `origin`)

  ```
  git push origin [name_of_your_new_branch]
  ```
  
* In GitHub, submit a Pull Request to the original repository, selecting the branch from which you 
based your changes (in the original repository) and `[name_of_your_new_branch]` (from your forked 
repository).

* The Pull Request will then be reviewed. 
  * If there are changes required to the Pull Request, make the updates to `[name_of_your_new_branch]`, 
  and optionally squash the commits as described above. Then rebase and the pull request will be automatically updated.
  
   ```
   git rebase master -i
   git push -f
   ```

* When the Pull Request is approved and merged into the repo, you will most likely want to clean up 
  a bit and ensure that you have the latest changes locally.
  
  * Delete the extra branch
   
    ```
    # Delete from GitHub (can also be done from web interface)
    git push origin --delete [name_of_your_new_branch]

    # Switch to the master branch
    git checkout master -f

    # Delete the extra branch from local repo
    git branch -D [name_of_your_new_branch]
    ```

 * Pull the changes from `upstream` to your local repo
  
    ```
    git pull --ff upstream [upstream_branch]
    ```
    
 * Commit the merge, review the changes, and push the merge to your GitHub repository.

## Let's practice!

### Premise

* This public GitHub repository contains list Star Wars characters. We have one file per character, and it contains the name and a short description of the character.
* I am looking for other people to contribute to my Star Wars characters project. (Yes, I could have written a script to get the full list of characters, but that is not the point...)
* You don’t have *push* access to my repository, so you will have to create a Pull Request.

### Task

* Contribute to this project by adding one Star Wars character that is currently not in the repo.

*Hint*: you can find a long list of Star Wars characters on [Wikipedia]( https://en.wikipedia.org/wiki/List_of_Star_Wars_characters)

### A bit of help

In case you get stuck on the task or your pull request is rejected:

* Follow the CONTRIBUTING.md file in the repo
* Ensure that there isn’t already a pull request or issue reported that handles your intention of contribution


## Additional resources

* [General GitHub documentation](http://help.github.com/)
* [GitHub's documentation on Git Rebase](https://help.github.com/articles/about-git-rebase/)
* [GitHub's documentation on Configuring a Remote for a Fork]https://help.github.com/articles/configuring-a-remote-for-a-fork/
