---
title: "Introduction to Spacemacs"
date: 2020-04-10
publishdate: 2020-04-10
lastmod: 2020-04-10
draft: false
tags: ["rails", "workflow", "command-line"]
---

Hi Good Evening. Welcome to the April edition of Roro Syd.

The topic for today's talk is Hitchhikers Guide to the Spacemacs. 

This is a beginner level talk. 
Its useful even if you are not a ruby / rails dev.   

This is a good length talk and I am going to pace myself. I will err on being slow.

--- Next Slide----
- Intro, 



--- Next Slide----

The best editor is neither emacs nor vim, it is emacs and vim!.

--- Next Slide---- 
Spacemacs takes the goodness of both emacs and vim and packages into a new distribution.    
--- Next Slide----
3 Qualities of Spacemacs, 
- Ergonomics - means its easier to use, easier on the hands. The keybindings are such, you don't have to do gymnastics with your hand to do simple tasks on spacemacs 
- Mnemonics - Key bindings are oraganised by mnemonic prefixes, like f for file, p for project, g for git etc
- Consistency - Similar tasks will have similar key bindings. For example If you learn the key bindings for Ruby, you don't have re learn a lot if you switch to Python. And you can mostly guess the key bindings of similar tasks. For example q is for quit in a lot of contexts. similarly f is for file. s if for save or status. 

So why is spacemacs called spacemacs?
--- Next Slide----

 bcos you press a series of keys  one after the other to accomplish a task, but you always start with a SPC. 

--- Next Slide----
This is how you install Spacemacs. You need to install emacs-plus and link it so it is accessible from your Application in your Mac. 

```shell
$ brew tap d12frosted/emacs-plus
$ brew install emacs-plus
$ sudo ln -s /usr/local/Cellar/emacs-plus/26.3/Emacs.app /Applications
```
Then you need to execute the following git clone command so that your emacs, magically turns into spcamacs. 

```shell
$ git clone https://github.com/syl20bnr/spacemacs ~/.emacs.d
```

That would get you started with spacemacs. 

Now lets get started. 
Let me start spacemacs.
 
--- Next Slide----
Lets us learn some very basic commands. 
- When you start emacs either fromy e you Applications or by executing emacs command from the console, you start Spacemacs. 

The first thing I want to do is to adjust the zoom so you can view what I am doing. 

I want to turn on Key Castr, so you can see the keys I am pressing for different tasks. 


Then zoom out, restart spacemacs and quit Spacemacs
```
SPC z f +  → zoom In 
SPC z f -  → zoom Out
SPC q q    → Quit
SPC q R    → Restart
```
--- Next Slide----
One of the first fun things that I did with Spacemacs is to explore the themes. You can cycle through the themes using the command SPC T (n or p).


One of the important thing about spacemacs is that you don't necesarily need to know all the commands. You can figure out as you go along. Like Once we press SPC T, then we have all the commands related to themes displayed at the bottom and we can select what we want. This is the mnemonic charecteristic of Spacemacs. 
```
SPC T n    → Cycle thru Themes
SPC T s    → Select theme
SPC T F    → Fullscreen
SPC b h    → Home screen
```
You can spend quite a lot of time changing themes. Its really additive, but now lets move on. 
--- Next Slide----
All the configs of Spacemacs are stored in a file .spacemacs in your home direc/tory. You could either search it by filename or you could open it via a short cut. 

What I want to show here is the layers I have installed. Layers are like Gems that you add to your rails project. You can see I have installed ruby and ruby on rails layers , also the shell layer and the version control layer. We will explore these layers as we go along.

But now, we shall change the default theme, save the theme and restart spacemacs to see that the theme has take affect. 

```
SPC f e d  → Open configs
SPC f s    → Save configs
SPC q R    → Restart Apply configs
```
--- Next Slide----

We can search for files the way we search in any file browser. 
We can open the file and make edits to the file. and save the file.  
Then we can also create a new file. Lets create a new controller, blog1_controller.rb. Now we have our new controller. We see that Spacemacs has guessed that its a controller file, it has created a new class and subclassed it from ApplicationController. Isn't that cool. 
```
SPC f f    → Search for files
SPC f s    → Save file
SPC f f    → to create a new file
```
--- Next Slide----
I will show something cooler next. We can even browse your project just like you would do it in an IDE. You have the project tree on the left side and the editor on the right. 
You can also search for a file within a project.
```
SPC p p    → Search for a project
SPC p t    → Open project tree
SPC p f    → file within Project
```
--- Next Slide----
How do we switch between the project tree and the editor?
Space 0, or 1 . We can also switch b/w recently opened files. Its called switching buffers. 
```
SPC 0      → Project Tree
SPC 1      → Editor Window
SPC TAB    → Switch buffer
```

--- Next Slide----

We can split windows either horizontally or vertically.
We can even lose the windows (or buffers as they are called in spacemacs terminology). And if you get bored, you can even return to the home buffer. 
```
SPC w -    → Split window
SPC b x    → Close current buffer
SPC b h    → Home buffer
```
--- Next Slide----
Now on to rails. SPC m when you have a rails file opened take you to major mode, where you have options for rails. 
 
```
SPC m f i  → Major mode
SPC m x s  → rails s
SPC m k k  → run rake task
```

Some options for bundle comamnds
```
SPC m b i   → bundle install mb
SPC m b u → bundle update
SPC m f c c   → rails generate
```
Some git commands
```
SPC g s  → git status
SPC g b   → git blame
SPC g f d   → git diff
```

```
SPC g S  → Stage a file
SPC g b   → git blame
SPC g f d   → git diff
```

```
SPC g s  + l → git log
SPC g s  + cc → Start commit
Add a commit message and exit
```

In Summary, Spacemacs has learning curve but its highly rewarding. We looked at how to do everything from editig files, starting a rails server, opening up a rails console to doing a commit. And I have not even scratched the surface with Sapcemacs. 

My goal for this talk was to introduce you to some tip and tricks that could make your life easier immediately and to Spacemacs that can make your life difficult in the short run and way cooler in the long run. 






