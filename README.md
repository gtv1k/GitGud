# How to Git Gud with GitKraken

A small preface here, nothing I say here is gospel and it's all subject to change, this is just how I do it. <br>
If you have your own way of doing it, do that. But if you have none yet then this might be for you.

### What is Git?
<details>
<summary> expand </summary>

As you collaborate on a project and work progresses files will change. A lot. Things will get messy, and might break completely at some point. <br>
When that happens you'll likely want to roll back to the most recent working version of your project. With version control, or in our case *git*, it is.

It also allows one to roll out fixes for old releases of your project, you can just jump back in time to that version and apply your fixes.
  
</details>

## Git Flow
<details>
<summary> expand </summary>

[Tutorial](https://youtu.be/eTOgjQ9o4vQ)
  
Branches are used to develop features isolated from each other. <br>
Git flow makes it so you don't have to manually handle those yourself anymore. <br>

It follows a pattern where you have different type of branches: <br>
- The `stable` branch is the latest release of your project. <br>
- The `develop` branch is your WIP version, merge features into this and test it, once it's stable you can make a new release.  <br>
- The `feature/` branches are where you'll be working.
- The `release/` branches are saved versions of your project.

---
### Features
Feature branches are used for new features (who would've guessed) and bug fixes. <br>
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
Imagine each commit as a snapshot of a point in time where you can return, if necessary, to access your project in its earlier state.

### Commit Messages


</details>
  
## Branches
<details>
<summary> expand </summary>


  
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
