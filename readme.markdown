build-lists: true

# [fit] Git & GitHub

---

### Or: A breezy introduction to version control for better collaboration and risk-taking

---

# Andrew Ek

### Full Stack Developer, PaymentSpring

## andrewek@gmail.com
## github.com/andrewek

---

## http://www.github.com/andrewek/fff-git-intro

The slides were generated dynamically from this document

---

# Agenda

1. Problem Statement
2. Important Concepts and Vocab
3. Workflow Outline
4. Workflow Demonstration (Command Line)
5. Brief discussion of GUI clients
6. Brief discussion of GitHub
7. Q & A (if time allows)

---

# [fit] Problem Statement

---

# Problem Statement

As projects become larger and as teams become larger, these things are generally true:

1. Making changes to code (or adding code) takes more work
2. If those changes don't work out, reverting them is harder
3. We can't easily work on more than one thing at once
4. Collaboration becomes much harder

---

## More generally, it becomes harder to plan and harder to change course

---

# [fit] Let's flip this around

---

# Our Ideal Workflow

We want to be able to work in a way that lets us:

1. Painlessly collaborate with as many people as we want
2. Freely take risks and experiment with our code
3. Always know we have a stable base to return to
4. Be able to work on multiple things at once

---

# [fit] So how do we do it?

---

# [fit] Git

---

# Git

---

# Git

Git is a piece of *version control software*, invented by Linus Torvalds. More generally, it is one of many tools we might use to achieve our ideal workflow.

---

# Version Control Software

While git is popular, it's not the only VCS out there:

1. Subversion
2. Mercurial
3. TFS
4. Fossil

... and sso on

---

# You should consider VCS if...

1. You've run across any of the problems above
2. You desire a cleaner path towards the ideal workflow
3. You want to start collaborating more (or more easily)
4. You have the brain space necessary to take on some cognitive overhead

---

# So how do we use it?

1. From the command line
2. From a GUI client

---

# Key Phrases

+ **Repository**
+ **Stage**
+ **Commit**
+ **Branch**
+ **Merge**

---

# Status Reports

We'll check our work with `$ git status`

(The `$` is a terminal prompt)

---

# Repository

The repository is basically a git-tracked directory (with subdirectories) for our code.

---

# Repository

A repository lives in a folder and keeps track of that folder

---

# Repository

We create a new repository by:

1. Navigating to the folder we want
2. `$ git init`

---

# Repository

A repository is made up of **commits**, which are basically snapshots of tracked files as they change.

We can commit a file in two steps:

1. Stage the files in question (if they have changed since the last time they were committed)
2. Commit all staged files

---

# Stage

Staging a file simply means marking it to be included in the next commit.

```bash
  $ git add my_awesome_site.html
```

---

# Stage

Or we can stage all files in the repository's directory and subdirectories:

```bash
  $ git add -A
```

---

# Commit

When we commit, we take a snapshot of all staged files (and ignore unstaged files)

```bash
  $ git commit
```

---

# Commit

This will open up our text editor (make sure to set this!) and prompt us to write a commit message.

---

# Commit

If a commit is a snapshot, the commit message is what you write on the back so that you know what the picture is.

---

# Commit

Your commit message should answer two main questions:

1. What did you do?
2. **Why** did you do it? What problem were you trying to solve?

---

## Q: How often should I commit?

---

## A: As often as you feel like.

---

# Commit

In general, each commit should be a fairly small, fairly atomic unit of work.

Keep your commits big enough to be meaningful, but small enough to throw away.

---

# Branch

With a series of commits, we have a timeline of changes. But we can have multiple parallel timelines that act independently of each other.

---

# Branch

By default, we start on the **master** branch. This is our most stable, and (if it's code) should be ready to go at a moment's notice.

---

# Branch

But we can split off the master branch (say, if we want to create a new feature that we know will temporarily break things).

```bash
  $ git checkout -b my-awesome-branch
```

(the `-b` flag creates a new branch)

---

# Branch

Now we have two branches, which we can work on independently.

```
  + master
    + my-awesome-branch
```

---

# Branch

We can have as many branches as we like.

```
  + master
    + user-authentication
    | + password-encryption
    + initial-styling
    | + try-out-sass
    | | + resolve-precompiler-issue
    | + try-out-less
    + landing-page-content
```

---

# Branch

Work done in branches is independent (and does not affect) other branches.

Now we can work on multiple things at once, and work with multiple people.

Our **master** branch stays pristine.

---

# Branch

Switch between branches with:

```bash
  $ git checkout my-branch-name
```

(Note the missing `-b` flag)

---

# Merge

When we've finished with a branch, we'll want to merge it back into its root (or destroy it).

---

# Merge

```
  + master
    + user-authentication
      + password-encryption
```

Let's say I'm done with `password-encryption` and I want to combine it with the rest of my `user-authentication` work.

---

# Merge

```bash
  # make sure I'm on user-authentication
  $ git checkout user-authentication
  # merge password-encryption in
  $ git merge password-encryption
```

So long as nothing in `user-authentication` has changed since I branched off it to create `password-encryption`, this will work just fine.

---

# Merge

```bash
  # Make sure password-encryption is up to date
  $ git checkout password-encryption
  $ git merge user-authentication
  # make sure I'm on user-authentication
  $ git checkout user-authentication
  # merge password-encryption in
  $ git merge password-encryption
```

---

# Cleaning up branches

We can destroy branches once they are merged into their parent:

```bash
  $ git branch -d my-branch-name
```

---

# Cleaning up branches

If we want to discard a branch entirely, we can do that too:

```bash
  $ git branch -D my-branch-name
```

---

# Workflow

1. Come up with an idea for a feature
2. Create a new branch for that feature
3. Work on the feature until it's done
  + Create a new branch for a small unit of work
  + Once that's successful, merge into my feature branch
  + If it's not successful, discard it and try again
4. Merge back into master

---

# Guiding Principles

1. Branches are inexpensive. Create them freely (but deliberately)
2. Use lots and lots of little one-off branches to isolate units of work
3. Use branches to safely take risks
4. Name your branches well
5. Don't create more branches than you can keep track of
6. Git should help, rather than hinder you

---

# Git GUI

There are plenty of graphical git clients.

+ GitKraken
+ GitHub Desktop
+ Sourcetree
+ GitCola

Use whatever is most comfortable. The guiding principles apply still.

---

# GitHub

GitHub and its ilk (BitBucket, GitLab, etc.) exist to let you collaborate, to publish your code, and to have conversations around your code.

These platforms exist purely as a place to store your code.

---

# GitHub

It's probably easiest to set up GitHub per the "Learn Enough Git to be
Dangerous" directions (see "Further Resources")

---

# Further Resources

The following resources are free and high-quality.

+ [**Learn Enough Git to be Dangerous**](https://www.learnenough.com/git-tutorial) - Michael Hartl
+ [**http://try.github.io**](http://try.github.io) - Try Git
+ [**http://git-scm.com**](http://git-scm.com) - Git Manual
+ [**GitHub Help**](https://help.github.com/) - GitHub reference

---

# Further Resources

+ [**Lorem Ipsum Generator**](http://generator.lorem-ipsum.info/)
+ [**Bootstrap**](http://getbootstrap.com/css/)
+ [**Bootstrap CDN**](http://getbootstrap.com/getting-started/#download-cdn)

---

# Questions?
