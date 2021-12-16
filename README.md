# How to Git Gud with GitKraken

A small preface here, nothing I say here is gospel and it's all subject to change, this is just how I do it. <br>
If you have your own way of doing it, do that. But if you have none yet then this might be for you.

## Git Flow

## Commits

## Branches

## Online vs Offline

Git works both offline and online, the problem is that it doesn't automatically sync with the online version. <br>
This means you'll have to do this manually, by downloading and uploading changes. <br>
In git terms we call this **pushing** and **pulling**.

---
### Push <img align="left" height="32" src="https://user-images.githubusercontent.com/77513543/146288232-02dad3d8-5ef8-466c-a407-e87bec635dcf.png">
_This is basically uploading your changes._ <br>

What is does is take any **local** changes, and applies them to the **remote** repository. <br>

If your local branch doesn't exist yet it'll create a new one for it, if there is one it'll apply your changes to said branch. <br>
Ideally you shouldn't have changes on it, since there would usually only be one person working on a feature branch in projects our size.

---

### Pull <img align="left" height="32" src="https://user-images.githubusercontent.com/77513543/146287840-b20794cc-d584-48d0-bd67-ab0381a39668.png">
_This is basically downloading your teammates changes._ <br>

What it does is update your **local** repository with any changes from the **remote** repository. <br>

It's secretly a combination of two actions, **Fetch** and **Merge**. <br>
**_Fetch_** downloads all the changes from the remote reposity. <br>
**_Merge_** applies said changes to the local repository. <br>

Before starting a new feature make sure to _always_ Pull develop first, this reduces the changes of _merge conflicts_.

---


## Commit Messages


## (Optional) Groups
