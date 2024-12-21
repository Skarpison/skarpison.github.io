---
layout: default
title: Creating a Github Personal Access Token
---
[Go back to the beginning](/)

![GitHub fine-grained personal access tokens banner with highlighted explanation text about repository-scoped tokens for API use and HTTPS](/images/github-pac-banner.png)

## What?
Github doesn't want you using your username/password to interact with your code from command line. So to push code to your Github repo you'll need to create a "Personal Access Token". These are randomly generated strings that you use as your password when prompted for a password when pushing code via commandline. They should be set with as few a permissions as possible and should have an expiration date. 

## How?
 - Go to Settings/Developer settings
 - Click Personal access tokens/Fine-grained tokens
 - Click Generate new token
 - Give it a name, an expiration date(DO IT! Security is good), and put a descritpion that actually matters.
 - Only give it access to the only repositories it needs
 - Click into Repository permissions to set the permissions that the token will have
   - Set Contents to Reac and write. This allows you to do commits, push code, download, merge. Some basics.
 - In Overview 2 permissions will be selected. The Contents and Metadata. Metadata is selected because this is the basic information about the repo such as the name of it.
 - Click Generate token
 - Copy this token somewhere secure. Bitwarden or something. There are git credential managers but I've never used one yet. Example: [git-credential-manager](https://github.com/git-ecosystem/git-credential-manager)

You can now use this token until it expires to work with your repo from command line. 

## Next?
Go push some code to Github.

