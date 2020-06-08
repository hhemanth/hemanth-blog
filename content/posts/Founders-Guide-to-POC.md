---
title: Founders guide to building Proof Of Concept.  
description: "Tech advice on building the version 0 of the product "
date: 2020-06-08
lastmod: 2020-06-08
tags: [enumerables, collections, select, flat_map, detect, arrays]

---
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/startups.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 



I have spent most of my career with startups. I have co-founded 2 technology startups and failed badly at both of them. In my current avatar @ Redant, I consult with Startups, helping them build their version 0 of their product or take their product to the next level. So I am not only qualified, I also feel responsible to write this article.

This a note to myself on how I would do a startup this time around. I will concentrate on building the version 0.0 of the product in this article. A startup is much more than version 0.0 of the product, but that is the focus of this article. I want to write this article as if I am sitting across a founder at the idea stage, wanting to build the first version of the product. But this is more of advice (strategic and tactical) to myself to refer to, before taking the plunge. 

## Go long, really long
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/long_road.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 


If you want to start, think long term really long term. Think 10 , 20 , heck think 50 years. That really changes the way you think about the product development process. You want to build a product that lasts, you want to build multiple products. You want to learn what goes into building a product, you want to build relationships with developers and product managers so they can help you build more and more. If you think long term, you want to learn as much, so you can get better at doing it year after year. 

The product you are building now, may not succeed, but the one you build next or the one after will probably succeed. So learning and quantifying learning along the process is important. 
## Less is more
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/kaap-it-simple.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 

It's very tempting to get the finest tools for the job and spend big bugs. My strong advice is to resist that temptation. Use the simplest of tools for the job. I would recommend gmail, google drive and slack, for your communication, brainstorming, documentation and proposals. Don’t even have to get an email with your domain name, use the simple gmail.com mail at this point. I would however recommend you get a domain name and put up a blog at your domain name.

Use the restriction that the free tools impose upon you to build a discipline. I will give you an example, when you use the free plan of Slack you cannot search beyond 10000 messages. In a way you are forced to record important conversations and documents some place else. I suggest those discussions and documents go in your google drive neatly stored and annotated. In this way these documents can become fodder for a blog post, or a requirements document. If you had a full version of slack, you could search all you need, and you wouldn’t be mindful about documenting your thoughts and discussions in google drive. Before you know it you will have a collection of these documents which are pure firepower for your startup. 

And start writing on your blog. Write about yourself, the product you are building, the industry, your target audience. Write as if you are directly speaking to your target audience and your investors. Use the firepower you have collected by meticulously documenting your thoughts and conversation in your Google drive folder. Writing provides a clarity to your thoughts like no other. And by writing regularly, you are already engaging your target audience before writing a single line of code. If you write well and regularly ( I would recommend a well thought out piece once a week), you could be regarded as an expert in your domain. Who wouldn’t want to buy from an expert?

When I say less is more, it's not just about the money you pay for the tools. You need to familiarize yourself with the tools and provide your mindshare to it. So simpler tools are better for you.

## Get down to the brass tacks 
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/team_work.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 

You are thinking long term, using simple tools, writing regularly , now get down to business and get your hands dirty building the product you want to sell. 

I have not qualified any of my statements till now. I mean I have not used Ifs and Buts in dishing out advice, I have taken a firm stand. But I am going to qualify my statements here a bit. The following section is relevant IF you are building a technology enabled SAAS product. It is not relevant if you are building a hardware product, or you are building a new technology itself. For example what I am about to say applies, if you are building a web application like twitter, airbnb, tripadvisor, imdb.com, but it's not so relevant if you are building your own OS or database or even building your own sensor or mobile hardware. 
  
I would recommend you use ruby on rails to build the first version of your product, heroku to host applications, github to host your code and Jira for project management, Balsamiq to flush out the design of your pages. 

Why am I being so specific in my choice of tools and providing you zero flexibility? I will explain in a bit. One I believe flexibility and choice increases confusion in your mind and provides me deniability. While deniability is a good thing when providing advice, it does not serve my purpose here. As I said at the start, this is what I would do if I would start. Second this is one less thing to decide for me and you. Third, all of the tools are free except Balsamiq. 

### Ruby on Rails
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/ruby.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 

You may have heard Ruby on Rails is not scalable and there are better languages out there. Believe me I have heard that too. There is some truth to it. Having said that Ruby on Rails is scalable enough for you and me to build the version 0 of the product and beyond. You can build a workable prototype of a web application using Ruby on Rails in a reasonable amount of time. You can hire good agencies to build the product for you. Heck I have known some founders (Some Tech and some non tech as well) who learnt Ruby on Rails to build a product themselves. 

### Heroku

Heroku provides a free plan to host your Ruby on Rails apps. And it integrates well with github and your developers (or yourself) can easily deploy to Heroku from their local machines with a single command. Why not AWS? Sure, only after you see significant traffic to your site. AWS can quickly become overwhelming as you would need to touch upon 5-8 services just to deploy your app properly and securely. 

### GitHub
Github provides a free plan to host private code repositories now and you can also use Github Actions for CI/CD. I have used bitbucket and gitlab as well, but I like Github. 

### Jira
Jira is a project management app where you create tasks, bugs and track them, assign them to developers and yourself.  You can create sprints, move tasks in and out of sprints and do basic project management. Jira provides much more advanced features in the paid plan, but use the basic free plan for now. 
### Balsamiq
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/wire-framing.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 

Balsamiq is a wireframing tool. I used Balsamiq about 10 years ago and fell in love with it. So I paid for the desktop version. Please buy the desktop version rather than the cloud version. You can create wireframes of your webapp in it and it even feels like you have drawn it on a napkin!

I have explained my choice of technologies and tools. I would like to add one more thing before I summarize. 

## Invest into good Design and Great Copy.
{{< imgAbs 
pathURL="https://hemanth-blog.s3-ap-southeast-2.amazonaws.com/design.jpg" 
alt="Some description" 
class="" 
style="display: block; margin-left: auto;margin-right: auto; margin-bottom:30px" >}} 

I would advise that you invest generously in designing your application and writing great copy. I learnt by making costly mistakes that good design and great copy can increase the chances of success for your business. 

## Summary
To summarize. I am writing this piece as an advice to myself for my next startup. But I definitely know this will be useful for anybody trying to startup. 

Think Long term, in the sense that, keep in mind that the current product you are building is first of many you will build. So concentrate on learning and building good relationships. 

Less is more, use simple everyday tools. Resist the temptation to splurge on fancy tool. Free tools like Gmail, Google Drive and Slack would suffice initially. 

When you get down to building the product, keep things simple and I would recommend the following technologies and tools. Ruby on Rails for building the web app, Github for hosting code, Heroky for hosting the app, Jira for project management and Balsamiq for wireframing. 

Last but not least, good design and great copy can save you the day. Understanding this is very important when building the first version of the product. 

