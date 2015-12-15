Productivity
============

All the tips to improve your productivity for front end development in mac.

##How to add/edit .bash_profile?
Open the Terminal app and if the file ~/.bash_profile does not already exist create one with the following command.  
```touch ~/.bash_profile```

Open ~/.bash_profile in your favorite editor and add your content and save it.

Most of the below tips depend on this when it says add to .bash_profile.  
Note: You need to run ```source ~/.bash_profile``` in terminal to bring up the changes.

##How to add/modify the PATH in mac OS using Terminal?
To check the current PATH, run  
``` echo $PATH ```  
The result will look like    
``` /usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin ```  

In terminal to add/modify, run  
``` export PATH="/usr/local/myfolder/bin:$PATH" ```   

$PATH at the end ensures that the old PATH is also retained along with new addition.   
``` echo $PATH ``` result will look like ``` /usr/local/myfolder/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin ```  

##How to bring up the simple http server?
By default macbook comes with python installed. So you can just run the below command to bring up the server. This is similar to bringing up the simple apache server.

```python -m SimpleHTTPServer 8000```

Need an alias/shortcut for this?  
Add below snippet to your .bash_profile and from next time you can run ```server``` command in terminal to bring up the server.  
```alias server="python -m SimpleHTTPServer 8000"```

##Opening sublime from command prompt:
In a mac terminal  
Run:  
```sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /bin/subl``` 
OR   
For sublimetext 3/beta   
```sudo ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /bin/subl```

Note: In new mac OS El Capitan, you are not allowed to write to /usr/bin, but writing to /usr/local/bin works. So use the below snippet  
```sudo ln -s "/Applications/Sublime Text.app/Contents/SharedSupport/bin/subl" /usr/local/bin/subl```

This will create a symlink, after this you can run below commands:  
 ```subl``` --> To open editor  
 ```subl .``` --> To open the current folder in Sublime  
 ``subl filename``` --> To open file in sublime  

#How to display git Branch name in OSX terminal?
Open the Terminal app and if the file ~/.bash_profile does not already exist create it with the following command.

```touch ~/.bash_profile```


Open ~/.bash_profile in your favorite editor and add the following content to the bottom.
```
# Git branch in prompt.

parse_git_branch() {

    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/ (\1)/'

}

export PS1="\u@\h \W\[\033[32m\]\$(parse_git_branch)\[\033[00m\] $ "
```

If you are using an existing Terminal session, don't forget to make the changes take effect by sourcing the file with the command 
```source ~/.bash_profile```

Source: https://github.com/mfitzp/martinfitzpatrick.name/blob/master/content/computing/add-git-branch-name-to-terminal-prompt-mac.md

##How to create an alias to bring up xcode ios simulator?
```alias ios="open /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/Applications/iPhone\ Simulator.app"```  
Once this is added to your ```.bash_profile``` do ```source ~/.bash_profile``` in terminal to bring up the changes.
You can run ```ios``` in terminal to bring up the ios simulator

##How to create aliases for normal git commands?
```
alias gl='git pull --prune'  
alias glog="git log --graph --pretty=format:'%Cred%h%Creset %an: %s - %Creset %C(yellow)%d%Creset %Cgreen(%cr)%Creset' --abbrev-commit --date=relative"  
alias gp='git push origin HEAD'  
alias gd='git diff'  
alias gca='git commit -a'  
alias gco='git checkout'  
alias gcb='git copy-branch-name'  
alias gb='git branch'  
alias gs='git status -sb'  
```
Add aliases to ```.bash_profile``` do ```source ~/.bash_profile``` in terminal to bring up the changes.

## How to view the folders in tree structure in terminal
```
brew install tree
```

then you can RUN the various tree commands

```
tree
tree -d
tree -a 
```
Use ```tree --help``` to find all the options

## Command Line shortcuts
### Search your command line history
$ ```history | grep 'queryselector' ```  
### Whats taking your memory
$ ```top -o vsize```  
### Run the last command with SUDO
$ ```sudo !!```  
### Unzip and archive to the current directory
$ ```unzip -l file.zip```    
###Copy to clipboard
$ ```echo 'hello' | pbcopy```  

##How to find the full path of shell commands?
Useful to find the installed paths  
command ```which```  
$ ```which grunt```  
Outputs /usr/local/bin/grunt

##List the contents of a directory
$ ```ls```  
$ ```ls -l```  - To view in list format  
$ ```ls -a```  - To view all files including hidden files  
$ ```ls -la``` - To view all files in list format  

##Download a file from terminal  
$ ```curl http://www.readlot.com/myfilename.doc``` 

##Checking network connectivity
$ ```ping www.techbray.com```

##How to check the latest available versions of your npm dependencies?
$ ```npm install -g npm-check-updates```  

After installing the npm-check-updates module, run the below command from your project root folder where package.json is present  

$ ```npm-check-updates```

This command will only print out all the available updates. This WON'T update your dependencies.  
Module Link https://www.npmjs.com/package/npm-check-updates

## Print the date before issuing each prompt in terminal

```export PROMPT_COMMAND=date```

```
Tue Dec 10 12:24:08 PST 2015  
user-MacBook-Pro $ 
```


