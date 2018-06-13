# Version Control 101

### Workshop Contents: 
- What is Version Control
- Common Version Control 
- Git and Github
- Configuring CLI & Git
- Creating a Repository
- Commits
- Branches
- Merge Conflicts

## What is Version Control
Version control just means the ability to make, track and roll back incremental changes to files. If you've ever had your desktop littered with files named things like 'end-of-term-paper.doc, end-of-term-paper-final.doc, end-of-term-paper-final-FINAL.doc' then you're already doing your own manual version control!

Version control is a great way to ensure that you can always roll back changes and can easily see the incremental differences between versions. It's even more important when you're trying to work as part of a group project since it allows all members of the group to contribute without overwriting each others' work.

## Common Version Control
The most common system you'll hear about is git. Git is actually it's own application, and then there are many different options that provide repository management. The most obvious of these is github but you'll also hear about gitlab and bitbucket. 

## Git and Gitbhub
Since this is the most common pairing this is what we'll focus on. Github is an organisation that works to provide both free and paid repository hosting services. A repository just means a project folder. You can use git the program and host your own repository server, but this requires oversight and work so most people prefer to use github. You can have a paid individual github account too and this adds some additional features, or for companies github offers an 'enterprise' option which you can avail of. We'll assume you're using the free github service here. 

Note: When we refer to 'git' we are talking about the tool, when we say 'github' we are talking about the website/service/company provider

When you create a 'repository' this essentially is just a top tier directory for a project. Once you 'initialise' the repository you're telling git that this is the parent directory for any number of subdirectories and files. You'll still need to manage adding those files to the repository but you'll essentially have set the main repo base as that directory. 

## Configuring the CLI and Git
You should already have a github account. The first thing we'll want to do is to set up SSH keys with the account. This will allow us to interact with github without constantly having to type passwords. 

Follow the steps provided by github here: https://help.github.com/articles/connecting-to-github-with-ssh/
You'll be using the command line to do this, so make sure you're in your home directory first with:
```
cd ~
```

When you first try to use the command 'git' you may receive an error, if you do run the command ```git`` on its own and you should be prompted for the option to install it via installing xcode tools. You can do this or you can manually install xcode tools via the app store. 

## 


