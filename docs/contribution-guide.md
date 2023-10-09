## How to Create a Feature Branch in Git?
git checkout main.
git pull.
git checkout -b new-feature.
git add <some-file>
git commit.
git push -u origin new-feature.

## The naming convention for branches.
Lowercase and Hyphen-separated: Stick to lowercase for branch names and use hyphens to separate words. For instance, feature/new-login or bugfix/header-styling . Alphanumeric Characters: Use only alphanumeric characters (a-z, 0–9) and hyphens. Avoid punctuation, spaces, underscores, or any non-alphanumeric character.

## Steps to test changes locally before committing.
Remove the changes that you don't want to push. Easiest done by using "stash" first, then removing the changes.
Pull the latest state of the branch. Any conflicts are best handled at this time. Make sure that your code works with these changes.
Push your complete code. You always push what you have tested.

