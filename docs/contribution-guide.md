
## How to Create a Feature Branch in Git?
When creating a feature branch GitHub, you must start with the main branch. Here's how to create a feature branch workflow.


Start the Main Branch
The main branch is the central trunk in which all feature branches integrate. The command for fetching the main branch is:

git checkout main

git pull

The command will pull the latest resets and commits. It will also switch the repo to the central branch.

Create a New Branch
You can create a separate branch for each feature. Here's the command:

git checkout -b new-feature

The command will create a new feature branch on the main branch. When it comes to feature branch naming, start with a category. The main types are:
Bugfix
Feature
After the category, add a '/' and write the reference of the ticket or issue you're working on. In the absence of a reference, write no'ref.

Push Changes and Make Commits
Now, you can update this branch by pushing changes and making commits. Here are some commands for that:

git add <some-file>

git commit

Push It to Remote
You should push the feature branch to remote to keep a backup in the central repository. It helps you collaborate with other developers since they can see the commits you've added to the new branch. Here's the command:

git push -u origin new-feature

Resolve Feedback
Now that everyone in your team can see the feature branch, they can provide feedback. Keep an eye on the comments, fix bugs, and resolve all feedback before merging it into the main branch.

Merge Pull Requests
If other developers in the team have made changes to the repo, you must resolve conflicts before merging your feature branch. After you approve the pull request, you can merge it with the main branch.

When developers complete a feature, they do not immediately merge it into the master branch. Instead, they push this branch to the central server, filing a pull request. The pull request asks the team to review any changes before adding them to the main branch.
src= 'https://blog.mergify.com/feature-branch-a-quick-walk-through-git-workflow/'

## Naming Conventions for Branches
Basic Rules
Lowercase and Hyphen-separated: Stick to lowercase for branch names and use hyphens to separate words. For instance, feature/new-login or bugfix/header-styling.
Alphanumeric Characters: Use only alphanumeric characters (a-z, 0–9) and hyphens. Avoid punctuation, spaces, underscores, or any non-alphanumeric character.
No Continuous Hyphens: Do not use continuous hyphens. feature--new-login can be confusing and hard to read.
No Trailing Hyphens: Do not end your branch name with a hyphen. For example, feature-new-login- is not a good practice.
Descriptive: The name should be descriptive and concise, ideally reflecting the work done on the branch.
src= 'https://medium.com/@abhay.pixolo/naming-conventions-for-git-branches-a-cheatsheet-8549feca2534#:~:text=Lowercase%20and%20Hyphen%2Dseparated%3A%20Stick,or%20any%20non%2Dalphanumeric%20character.'
## Steps to test changes locally before committing.
STEP 1: INSTALL PRE-COMMIT NPM MODULE
There are some ways to setup GIT hooks, but it can be a bit complicated, and you need to do the same job for every repository.

Much easier way is to use npm module called pre-commit, it creates GIT hooks automatically.

Let’s try that:

npm install --save-dev pre-commit
STEP 2: SETUP TESTING SCRIPT
Ok so we have the tool for automatic testing, now we need to define a test script. In our case, it will be checking JavaScript Standard Style compliance in all files inside src/js folder.

Let’s add the script in package.json file:

"scripts": {
    "lint": "standard 'src/js/**/*.js'"
}
It is good to test what we’ve already done so let’s run the script manually to check if it’s working:

npm run lint;
STEP 3: ADDING A TEST SCRIPT TO PRE-COMMIT
Ok! When the testing script is created we need to add it to the pre-commit configuration (also in package.json file):

"pre-commit": [
    "lint"
],
STEP 4: LET’S GIVE A TRY
Once everything is set up, you can try to do the commit.  Pre-commit hook should automatically do the testing and prevent you from committing in case problems with the code.

automatic testing
pre-commit test run pre-commit blocked the commit because of JavaScript issues in source code
src='https://pagepro.co/blog/how-to-test-code-before-pushing-to-the-repository/'