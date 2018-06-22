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

Once you've done this you can configure options such as your username, the email address associated with it, as well as any additional details needed. 
Again we'll ues the official documentation as a guide here: git configure username


## Creating a Repository
You can create a repository directly from the command line or directly from the github UI. The easiest way to do this is probably through the github website. Once you've created your first repository there will be some directions provided on the website that will walk you through how to clone the respitory locally. Simply navigate to the directory you would like the repository located in and run the command. 

If you created aa readme or added a licence these will now be downloaded. Git works by taking *local* files and tracking these against an *origin*. At any point in time you can have multiple *branches* of a repository that may contain different code. When you change a file locally you must first *commit* it to git (often referred to as staging) and then you must *push* the change to the remote branch (aka the repository). Git is weird to get your head around at first but keep going!

We'll use a simple example where all our commits go to our main master branch. We create a repository called 'Zeus' in the cli. We will then clone our repository to our local machine using ```git clone``
Once we've done that we can create a file, for example:
```
touch lightning
```
We will now need to tell git that we want to add this file to our repository. You'll only need to ever do this once per file, that's because once git knows a file is part of a respoitory it will begin to track it and any changes made to it. 
```
git add lighting
```

We can now commit the new file:
```
git commit -am "adding a new file, lightning"
```
Here we've said -am which stands for 'add' and 'message'. It's a good idea to keep your messages verbose so others can easily understand what changes you're making. Remember to commit often, small changes are easier to track bugs down in than big changes.

Now that we've committed it git knows it will want to make a change, but we haven't actually sent the change to the repository. If we wanted to see any 'staged' changes, aka changes waiting for a push we can by checking 

```
git status
```


Now we need to *push* the change up to the repository (in this case our origin)
```
git push
```
You might get some complaints about squashing and pushing to unconfigured origins. That's okay, git is quite good at telling you what commands you need to run to resolve the problem, but you can also use the more verbose format of:
```
git push origin master
```
This essentially says 'push to my configured origin repository (this will have been automatically set when you cloned the repository) the master branch'.
Eventually you might end up needing to do more complex things and this is where it is useful to know you can add more specifics to your push requests. Master is the default but later we'll discuss branches and forks and you'll see cases where you'd want to specify a branch other than master. 
You'll see the push succeed and you should then be able to refresh the repository in a browser window and see the new file appear!

To see recent commits to a repository we can then view the log with
```
git log
```
You'll see a long hash in the output by each commit. This hash is how a commit is uniquely identified within a project. You'll start interacting with commits via their IDs as you become more familiar with the system,. This will let you start doing sweet stuff like pick a change from one branch to another, or create a new branch from a previous commit. 
 
##Undo! Undo!
The neat thing about git is that everything can be undone. You can always revert to any previous commit, whether it's pushed to the remote or not. There are a lot of excellent git tutorials out there, so rather than go in depth here we'll just point out to some of these:

General Git:
https://www.git-game.com/

Git Branching:
https://learngitbranching.js.org/

##Branching, PRs & General Best Practice
Generally speaking here's a few rules you should adhere to:
- When making changes, create a branch dedicated to those changes and once completed pull those changes into the appropriate main branch. Get used to doing this even if it's just your own small project, you can have a master branch and then branch off of that when making changes. Try to get out of the habit of pushing to master. 
- If you'd like to contribute to a project you should fork the repo and create a branch for your changes. You can then submit a PR from your forked repo to the main repo's branch. 
- Always check for a hacking.md file before contributing to a project and try to adhere to the instructions in there. 
- Be polite when suggesting a change that hasn't been requested, especially if you have an accompanying PR. 





