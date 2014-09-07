Productivity
============

All the tips to improve your productivity for front end development

##How to bring up the simple server?
By default macbook comes with python installed. So you can just do

python -m SimpleHTTPServer 8000

##Opening sublime from command prompt:
In a mac terminal  
Run:  
```sudo ln -s "/Applications/Sublime Text 2.app/Contents/SharedSupport/bin/subl" /bin/subl```  
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

How to create an alias to bring up xcode ios simulator?
```alias ios="open /Applications/Xcode.app/Contents/Developer/Platforms/iPhoneSimulator.platform/Developer/Applications/iPhone\ Simulator.app"```
