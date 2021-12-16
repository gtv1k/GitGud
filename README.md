# How to Git Gud with GitKraken

A small preface here, nothing I say here is gospel and it's all subject to change, this is just how I do it. <br>
If you have your own way of doing it, do that. But if you have none yet then this might be for you.

### What is Git?
<details>
<summary> expand </summary>

As you collaborate on a project and work progresses files will change. A lot.  <br>
Things will get messy, and might break completely at some point. <br>
When that happens you might want to roll back to the most recent working version of your project. With version control, or in our case *git*, that's easy.

GitKraken is just one tool for Git, but I think it's one of most visual and easiest ones. <br>
It gives a nice overview of all previous changes and releases which will help you get a good mental map of the project.
  
</details>

## Git Flow
<details>
<summary> expand </summary>

[Tutorial](https://youtu.be/eTOgjQ9o4vQ)
  
Branches are used to develop features isolated from each other. <br>
Git flow makes it so you don't have to manually handle those yourself, it creates and deletes them for you. <br>

It follows a pattern where you have different type of branches: <br>
- The `stable` branch is the latest release of your project. <br>
- The `develop` branch is your WIP version, merge features into this and test it, once it's stable you can make a new release.  <br>
- The `feature/` branches are where you'll be working.
- The `release/` branches are saved versions of your project.

---
### Features
Feature branches are used for working on new features (duh) and bug fixes. <br>
You should basically never work on the `develop` branch directly, split off into a feature branch first, break shit and once it's stable and you've tested it you can **finish** the feature.
  
When **finishing** a feature branch, GitKraken will merge the feature branch into `develop`, and delete the feature branch from the local repository.

You are encouraged to commit even broken stuff onto your feature branch as it's completely separate, it doesn't affect the project for other people _until_ you **finish** it and merge it with `develop`.

---
  
### Releases
Releases are stable versions of your product.

When **finishing** a release, GitKraken will merge the `release` branch into both `develop` and `stable`. <br>
This creates a tag with the release name for future reference.

Ideally this should be the only way you're merging with `stable`. (except for hotfixes)

---
  
</details>

## Commits
<details>
<summary> expand </summary>
Imagine each commit as a snapshot of a point in time where you can return, to access your project in its earlier state, if necessary.

I prefer doing them very small and incremental steps, I usually commit for invidual functions or files added.

### Staging

[Tutorial](https://support.gitkraken.com/working-with-commits/staging/)

Staging is prepping your files for a commit, you can manually select what to commit. <br>
Say you started on something but plan to change it in the next commit anyways just don't commit it now, make the changes and commit it then. <br>

You can do this per file, line, or block of code. <br>
But most of the time `Stage all changes` will do just fine.
  
---

### Commit Messages

To identify each commit, you provide them with a message - they're a brief statement of what exactly happened in between the last commit and this one. <br>
Put a bit of thought into it, this is the only place where viewers can see not just what has changed, but why. <br>
Think about what future you or other people would want to know about the stuff you just added or changed. <br>
Also make sure it's searchable, so define the scope in the title.

If you're using automated Git Projects you can make [automatically close issues and move cards](https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue)

Here's my template:
**Summary**
`NEW/CHANGE/FIX/DOCS [SCOPE] (WHAT) EXPLANATION`
**Description**
```
FURTHER DETAIL OF IMPLEMENTATION

LINK TO ISSUE
```

Example:
```
NEW [Player] (Function) Jump()

Added a jump to the player.
o If you press the jump key shortly it jumps 32px
o If you hold it longer it jumps up to 96px

Closes #12
```

---

</details>

## Online vs Offline
<details>
<summary> expand </summary>

Git works both offline and online, the problem is that it doesn't automatically sync with the online version. <br>
This means you'll have to do this manually, by downloading and uploading changes. <br>
In git terms we call this **pushing** and **pulling**.

---
### Push <img align="left" height="32" src="https://user-images.githubusercontent.com/77513543/146288232-02dad3d8-5ef8-466c-a407-e87bec635dcf.png">
_This is basically uploading your changes._ <br>

What is does is take any **local** changes, and applies them to the **remote**. <br>

If your local branch doesn't exist yet it'll create a new one for it, if there is one it'll apply your changes to said branch. <br>
Ideally you shouldn't have changes on it, since there would usually only be one person working on a feature branch in projects our size.

---

### Pull <img align="left" height="32" src="https://user-images.githubusercontent.com/77513543/146287840-b20794cc-d584-48d0-bd67-ab0381a39668.png">
_This is basically downloading your teammates changes._ <br>

What it does is update your **local** project with any changes from the **remote** project. <br>

It's secretly a combination of two actions, **Fetch** and **Merge**. <br>
**_Fetch_** downloads all the changes from the remote project. <br>
**_Merge_** applies said changes to the local project. <br>

Before starting a new feature make sure to _always_ Pull develop first, this reduces the changes of _merge conflicts_.

---

</details>


## (Optional) Groups
