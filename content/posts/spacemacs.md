---
title: "Introduction to Spacemacs"
date: 2020-04-10
publishdate: 2020-04-10
lastmod: 2020-04-10
draft: false
tags: ["rails", "workflow", "command-line"]
---
Why would you use Spacemacs at all? It has a steep learning curve and you will not be productive for quite some time. And it will be quite frustrating working with it atleast for the first few weeks. 

If I want to answer that question with an image, It would be this.

{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/spacemacs_scr1.png" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto;" >}}  
 

But I would also like to tell you a story. Please bear with me, its a small story but very relevant to the point I am trying to make here.   

{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/artic_circle_exploration_ad.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto;" >}}  


The story goes that the famed Antarctic Explorer Sir Ernest Shackleton put out the above ad to recruit for his crew before he went on the expedition. The ad pretty much captures the essence of the expedition. You would think that the expedition hardly had any takers. You can't be more wrong, Shakleton got 5000 response for the ad.    

Now you would think, who would like to go on an expedition where the chances of return would be less and that too for meagre wages? The last line of the advertisement would give you a clue of why the ad got so many responses  "Honor and Recognition in case of success"". 

So If I would sell you Spacemacs to you similarly it would be the below ad. 
```
Men\Women wanted to learn Spacemacs 
Arduously difficult initially
Long weeks of frustration editing files
super powers guarenteed in case of success
RESPECT in the eyes of Colleagues and self for trying
```

I myself started with Spacemacs recently. Thanks to my colleague, Amit who introduced me to Spacemacs. 
  
This is the article(s) I wish I had when I started with Spacemacs. 
 
The best editor is neither emacs nor vim, it is emacs and vim!. Spacemacs takes the goodness of both emacs and vim and packages into a new distribution.    

Spacemacs has the following charecteristics.  
- Ergonomics - It means its easier to use, easier on the hands. The keybindings are such, you don't have to do gymnastics with your hand to do simple tasks on spacemacs.  
- Mnemonics - Key bindings are organised by mnemonic prefixes, like f for file, p for project, g for git etc
- Consistency - Similar tasks will have similar key bindings. For example If you learn the key bindings for Ruby, you don't have re learn a lot if you switch to Python. And you can mostly guess the key bindings of similar tasks. For example q is for quit in a lot of contexts. similarly f is for file. s if for save or status. 

**So why is spacemacs called spacemacs?**

Because you press a series of keys, one after the other to accomplish a task, but you always start with a SPC. 

**Installing Spacemacs**

This is how you install Spacemacs on your Mac. You need to install emacs-plus and link it so it is accessible from your Applications in your Mac. 

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

To open Spacemacs type emacs on your command line, Or Go to Applications, find emacs icon and click on it.  

Now lets get started. 

**Start and Zoom**

Lets us learn some very basic commands. 
You start emacs either from your Applications by clicking on the shortcut or by executing emacs command from the console. Starting from your console will work both in Linux and Mac. 

```shell
emacs & 
```

The first thing I want to do is to adjust the zoom to what is convenient to you. 
Then zoom out, restart spacemacs and quit Spacemacs.

```ruby
SPC z f +  → zoom In 
SPC z f -  → zoom Out
SPC q q    → Quit
SPC q R    → Restart
```

**Colorful Spacemacs**

One of the first fun things that I did with Spacemacs is to explore the themes. You can cycle through the themes using the command SPC T (n or p).

One of the important thing about spacemacs is that you don't necesarily need to know all the commands. You can figure out as you go along. Like Once we press SPC T, then we have all the commands related to themes displayed at the bottom and we can select what we want. This is the mnemonic charecteristic of Spacemacs. 

```ruby 
SPC T n    → Cycle thru Themes
SPC T s    → Select theme
SPC T F    → Fullscreen
SPC b h    → Home screen
```

You can spend quite a lot of time changing themes. Its really additive, but now lets move on. 


**Viewing and Changing Configs**


All the configs of Spacemacs are stored in a file .spacemacs in your home directory. You could either search it by filename or you could open it via a short cut. 

What I want to show here is the layers I have installed. Layers are like Gems that you add to your rails project. You can see I have installed ruby and ruby on rails layers , also the shell layer and the version control layer. We will explore these layers as we go along.


```ruby
SPC f e d  → Open configs
SPC f s    → Save configs
SPC q R    → Restart Apply configs
```

**Searching for Files**

We can navigate files and directories the way we do in any conventional file browser. 
We can open the file and make edits to the file. and save the file.  
Then we can also create a new file.

```ruby
SPC f f    → Search for files
SPC f s    → Save file
SPC f f    → to create a new file
```

**Viewing Projects**

I will show something cooler next. We can even browse your project just like you would do it in an IDE. A project is any directory with a .git file in it. As long as you have opened a file, the whole directory is stored You have the project tree on the left side and the editor on the right. 
You can also search for a file within a project.
```ruby
SPC p p    → Search for a project
SPC p t    → Open project tree
SPC p f    → file within Project
```

**Switching between windows**

How do we switch between the project tree and the editor?
Space 0, or 1 . We can also switch b/w recently opened files. Its called switching buffers. 

```ruby
SPC 0      → Project Tree
SPC 1      → Editor Window
SPC TAB    → Switch buffer
```

**Slitting Windows**

We can split windows either horizontally or vertically.
We can even lose the windows (or buffers as they are called in spacemacs terminology). And if you get bored, you can even return to the home buffer. 

```ruby
SPC w -    → Split window
SPC b x    → Close current buffer
SPC b h    → Home buffer
```

**Summary**

In Summary, Spacemacs has learning curve but its highly rewarding. We looked at how to do everything from zooming, opening a file, editig files, and opening up a project. And I have not even scratched the surface with Spacemacs.

The rest of the Articles in this series aims to dig deeper into features of Spacemacs.


