# meta
Related to the software development :computer: practices to be followed by the Programming Society IIIT-Bh.

## git-workflow

We (the maintainers) tend to be quite strict with our git guidelines. The idea behind this is to train newbies well so that they can get used to git, imbibe these practices and use them in their daily development activities. This would lead them to become better developers and who are more adept at contributing code with other developers and can easily get comfortable with the development workflow of other organizations.

### Creating a PR

Once you have been assigned to an issue you can follow the following steps to get started with making the change:
- Fork the repository.
- Clone the fork to your local machine using `git clone <remote-url>`
- `cd` into your local clone and checkout into a new branch using `git checkout -b <branch-name>` (**Note:** Every change will be made in a separate branch and PRs are never to be submitted from the master branch. Always keep your master clean)
- Make the changes as per the requirements of the issue you are working on.
- Run the tests (if required) and see if they pass.
- Add all the files to the staging area using `git add .`
- Commit all the staged files using `git commit -m "<your-commit-message>"`. (**Important:** Follow the following [guide](http://api.coala.io/en/latest/Developers/Writing_Good_Commits.html) for writing commit messages)

**Note:** For small changes PRs will only contain just one commit but for major feature implementations PRs can have multiple commits that are easy for the reviewer to review. *[More to be added on this later]*

- Now that you have committed your changes push your branch using `git push <fork-remote-name> <branch-name>`
- Go to your fork on github and you will see a `Compare and Pull Request` option once your branch has been pushed. Click that button and then open a PR.
- Await review.

### Workflow during a review

It seldom happens that PRs are merged in one go without any review comments. Most probably you will be asked to make more changes to your existing PRs and change it according to the reviewer/maintainer's satisfaction. Most newbies make the mistake of adding another commit on top of their branche's current tip but don't realize that this is undesireable since the reviewer might suggest a few more changes after the new changes have been pushed and making another commit on top of that will create multiple commits for a PR that is only expected to have just one commit. This messes up our git logs. So instead of making new commits after every review cycle the contributors are expected to follow the workflow described below.

- Once the reviewer has suggested changes go back to your local clone and make sure that you are in the branch from which your PR was made.
- Make the changes suggested in the review.
- Run the tests (if required) and see if they pass.
- Add them `git add .`
- Now instead of committing them as a separate change we will change the history of our git log and we will amend our most recent commit i.e. the commit that is visible on the PR. For that use the following command(s) `git commit --amend --no-edit` (if you don't need to edit your commit message) and `git commit --amend` (if you need to edit your commit message too).
- The commit that will be created by this will technically be a new commit since the commit hash will differ from the commit on your PR (since we made new file changes and hashes depend on the changes in file contents) but it won't be added on top of your previous commit but will be there in place of it so the tip of our branch will still have just one commit.
- Since we are changing history we will need to force push this commit using `git push -f <fork-remote-name> <branch-name>`
- Go to your PR and your changes will be reflected there.
- Await review.
