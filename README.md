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

# Contributor Covenant Code of Conduct

## Our Pledge

In the interest of fostering an open and welcoming environment, we as
contributors and maintainers pledge to making participation in our project and
our community a harassment-free experience for everyone, regardless of age, body
size, disability, ethnicity, sex characteristics, gender identity and expression,
level of experience, education, socio-economic status, nationality, personal
appearance, race, religion, or sexual identity and orientation.

## Our Standards

Examples of behavior that contributes to creating a positive environment
include:

* Using welcoming and inclusive language
* Being respectful of differing viewpoints and experiences
* Gracefully accepting constructive criticism
* Focusing on what is best for the community
* Showing empathy towards other community members

Examples of unacceptable behavior by participants include:

* The use of sexualized language or imagery and unwelcome sexual attention or
  advances
* Trolling, insulting/derogatory comments, and personal or political attacks
* Public or private harassment
* Publishing others' private information, such as a physical or electronic
  address, without explicit permission
* Other conduct which could reasonably be considered inappropriate in a
  professional setting

## Our Responsibilities

Project maintainers are responsible for clarifying the standards of acceptable
behavior and are expected to take appropriate and fair corrective action in
response to any instances of unacceptable behavior.

Project maintainers have the right and responsibility to remove, edit, or
reject comments, commits, code, wiki edits, issues, and other contributions
that are not aligned to this Code of Conduct, or to ban temporarily or
permanently any contributor for other behaviors that they deem inappropriate,
threatening, offensive, or harmful.

## Scope

This Code of Conduct applies both within project spaces and in public spaces
when an individual is representing the project or its community. Examples of
representing a project or community include using an official project e-mail
address, posting via an official social media account, or acting as an appointed
representative at an online or offline event. Representation of a project may be
further defined and clarified by project maintainers.

## Enforcement

Instances of abusive, harassing, or otherwise unacceptable behavior may be
reported by contacting the project team at [psocietyiiitbh@gmail.com]. All
complaints will be reviewed and investigated and will result in a response that
is deemed necessary and appropriate to the circumstances. The project team is
obligated to maintain confidentiality with regard to the reporter of an incident.
Further details of specific enforcement policies may be posted separately.

Project maintainers who do not follow or enforce the Code of Conduct in good
faith may face temporary or permanent repercussions as determined by other
members of the project's leadership.

## Attribution

This Code of Conduct is adapted from the [Contributor Covenant][homepage], version 1.4,
available at https://www.contributor-covenant.org/version/1/4/code-of-conduct.html

[homepage]: https://www.contributor-covenant.org

