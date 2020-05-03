---
title: "Introduction to Spacemacs"
date: 2020-04-10
publishdate: 2020-04-10
lastmod: 2020-04-10
draft: true
tags: ["rails", "workflow", "command-line"]
---

Hi Good Evening. Welcome to the April edition of Roro Syd.

The topic for today's talk is Dev Environment on Steroids. 

This is a beginner level talk. Topics discussed here can be incorporaed by beginners even if they don't know ruby or rails well. And I am sure even experienced developers may find something useful in this talk.
   
In this talk I would like to introduce you to some of the tips and tricks that would make your life easier as a ruby/rails developer. 
Some of the topics are relevant to any and all software developers and not just a ruby on rails developer.

This is a good length talk and I am going to pace myself. I will err on being slow.

--- Next Slide----
 

What do I mean by making your life easy as a developer. 2 things actually
- Reduce the frustration that is so much a part and parcel of our daily lives. 
- Increase the happiness and the sense of accomplishment, and that is the reason we bear the frustration, don't we.

Improving your productivity and improving you DEV environment is a continuous process. Its like loosing weight, you can't notice the differece every day, but when if you eat right and exercise daily you will start seeing the difference in few weeks. 

My aim is to introduce you to some tools and provide you with a framework to continue improving.    

I will share a link to the presentation and a blog that is essentially this whole talk. So you can sit, relax and enjoy the show. 

--- Next Slide----
What would be a framework for improving your DEV environment?
I would say
Step 1 : Start where you are. Really does not matter where. You could be starting out or an expert.   
Step 2 : Notice a point of friction. Something that you think are doing fine, but you think you can do better.
Step 3 : Find a way to do it better. By google search or an article on the internet or a talk like this.
Step 4: Document the new way and try to use it. Repeat it as much as possible. Repetition is the key, so that you don't have to think about it the next time you need it . 
 
In this talk I am going to use an example developer workflow. I am going show you to do something and then we will try to improve it iteratively. 

--- Next Slide----

Before we start , some simple tools to install to your mac. 
A window manager app which allows you to move and resize your windows easily.
``
Before spectacle, I would manually move windows haphazardly and try to adjust it on my screen.
Now I can use easy shortcuts to place windows on my screen. 

--- Next Slide----

Let jump right in to very simple workflow. 
We will create a simple rails app, the simplest of all. 

--- Next Slide----
--- Change Layout----

```shell
➜ rails new example_site
``` 
So we have created a simple rails app. Few tips about the bundle command to speed things up.

--- Next Slide----
You may have a large project with a lot of Gems. To speed things up you can use the --jobs option to install Gems in parallel. 

```shell
➜bundle install --jobs 4
```
You can also install Gems from the local cache, using the --local option. 
Install bundle from local cache
```shell
➜bundle install --local
```
--- Next Slide----

Now lets start the rails server. Oh no we see an error. 
Lets debug, 
Oh As you see we see that this is caused by the following line 
```
/Users/hemanth/.rvm/gems/ruby-2.6.3/gems/bootsnap-1.4.6/lib/bootsnap/compile_cache/iseq.rb:19: [BUG] Segmentation fault at 0xffffffffa603f150
```

This is a simple app, we can easily search for the keyword `bootsnap`, but if this were a large app, how would we search for the keyword. 
Yes, modern editors do provide a powerful search functionality, but there are more powerful tools. 

There is a tool called ``Silver Searcher``, ag for short.
I have already installed silver SEarcher to save time. 

``brew install ag``

Once we have installed ag, we need to know how to use it. We can use man pages, but there is another cool tool called tldr.
Lets use tldr to find out about Silver Searcher.

```
tldr ag
tldr man
tldr zip
tldr tar
```
--- Next Slide----
Now lets use ag to find the offending term. We use the -l option to list just the files that need to be changed. 
 
```
ag "bootsnap" 
ag "bootsnap"  -l
```
If you want take one thing from this presentation, and forget everything, it would be this command. This can radically improve the way you would debug. 

There is another more powerful tool. Called Ripgrep. When I heard about Silver Searcher aka "ag", I thought this is awesome, what could be more awesome than that?

I was wrong Ripgrep is more powerful than ag/ Silver Searcher. You can use Ripgrep to search for a pattern in only .rb files or only controllers or any pattern, literally handing you a lot of superpowers.  

```
rg 'bootsnap'
rg 'bootsnap' -g "Gemfile*"
rg 'bootsnap -j "*.rb"
```
Now that we know the offending files, lets change it and look at our shiny app .

```shell
rails s 
```

--- Next Slide----

If you want to look up routes of your app, you are better off looking at the UI rather than the command ``rake routes``.
Why, bcos its faster and easy to search. rake routes would take time to execute, but the app is already loaded in the server, looking it up on the UI is quicker. 

```html
http://localhost:3000/rails/info/routes
```
--- Next Slide----

Now the most amazing part at the end. Imagine your self. debugging a large project with 10s of Gems. And some of the Gems owned by your own team. Now you want to search for a function definition or a keyword inside these gems. How would you do it?

```
 rg 'bootsnap' $(bundle show --paths)
 rg 'logger' $(bundle show --paths)
```
--- Next Slide----

 To summarize. we have looked at the following.
 - Spectacle
 - tldr
 - Silver Searcher & Ripgrep 
 
A Small tip now
Have you ever been in the following situation.
You working through a project integrating a Gem that you have just written. And you just edited a file inside the Gem and you have made some changes. But you are unable to see the changes on your app. You have restarted the app, verified the file more times than you can count. Added debug statements, all over the function. But still you are not able to see your changes. 

I have been there and after you do it few times you start to identify the real culprit. Its the notorious Spring. Spring loads files to memory and keeps it there, it makes it faster to render your app, but its notorious for intractable problems. The best thing to do is to stop Spring when you are in development mode. This gets aggravated when you are trying to integrate your Gem to your app. 
--- Next Slide----
  
```shell
➜ spring stop
```

We have looked at few tools that may make your life easier by various degrees depending on how well you master them.

Now I want to introduce you to something that will make your life more difficult, hmm yes more difficult before it makes it easy. 

Folks I want to introduce you to spacemacs.

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






