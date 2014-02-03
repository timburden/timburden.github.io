---
layout: post
title: A new direction
---

I suppose after 14 years of doing anything it can start to feel a little stale. Especially in the world of programming, where new languages, techniques and paradigms bubble up rapidly. So after 14 years as a LAMP stack developer I'm going to branch off into something new and exciting: the full-stack JavaScript ecosystem.

One of the first things I'll have to do, of course, is learn JavaScript. Sure, I've been using JavaScript for all of those 14 years to do simple things on web pages. But I only ever learned enough of it to get done what I needed to get done. I learned what I know the same way most of us learned HTML: by viewing source on web pages and modifying other people's scripts. And then with the advent of awesome JavaScript libraries like Prototype and jQuery, the inner workings of JavaScript were more abstracted away.

But the first thing I noticed as I started to dig into this was how frighteningly little I know about JavaScript. For example, my JavaScript code looks a lot like how I do PHP: very procedural. This thing happens and then the next thing happens, and even if you've squirrelled some functionality off into a function somewhere, everything happens in script order. But JavaScript programming, especially in Node.js, is different. It's all about functions, functional programming, events, and asynchronous callbacks. In JavaScript, functions can have methods. You can pass functions as arguments to other functions, and return functions from functions. There's no classical concept of class, but you can modify the methods and properties of the prototypes of even basic types like Strings and Numbers and Objects and Functions. You have to pay a lot more attention to lexical scope, but the reward is powerful (and confusing) constructs called closures.

And it's hard. Try [these exercises](http://nodeschool.io/#functionaljs) and you'll see what I mean. Not to be too self-deprecating, I have been using JavaScript for 14 years with no idea what a closure is. Who needed it? It's like demanding that a guitarist in a rock band have a working knowledge of the Mixolydian mode. But to do server-side programming in JavaScript I'm going to need to understand it clearly.

So here's my plan:

1. Read _JavaScript: The Good Parts_ by Douglas Crockford
2. Read _Secrets of the JavaScript Ninja_ by John Resig. (There is a [companion website](http://ejohn.org/apps/learn/) with exercises.)
3. Work through all of the games at [NodeSchool](http://nodeschool.io/)
4. Read _Node.js for PHP Developers_ by Daniel Howard
5. Do a reasonably simple project for myself in the [MEAN stack](http://mean.io/). I have one in mind I call Twitter Link Bookmarker.
6. Do a more complicated project in MEAN for my employer.

This is not to say I'll never do PHP again. Of course I will, it's my bread and butter, it's what I do for work and I have no plans to leave there any time soon. I just feel like I have to branch out a little bit to keep fresh.

The other thing I want to change up is how I actually do development. For many years my dev environment and flow has been (purposely) extremely lean:
1. Edit files in a decent text editor (e.g., Notepad++)
2. FTP or SCP these changes to a stage server
3. Commit these changes in git
4. Pull these changes onto the production server.

Recently we have developed a better flow at my place of work where we're starting to use Vagrant and full git flow.* This gets rid of the FTP step, and adds some professional niceties, but it's essentially the same thing. If you want to work from home some days it's hard to keep your working files in sync. You either have to cart your laptop around or use a remote desktop or commit everything to a dev branch before you leave home or work. None of these are ideal.

What if instead you could sit down at any computer, log into Chrome and have a full, complete dev environment with all your projects at hand and all the tools you need right in the browser? Seem far-fetched? Turns out it might be possible.

Let's have a look at the bare minimum a dev needs to do everything he needs to do:
1. A text editor
2. A simple image editor
3. Version control (specifically, a git client)
4. A test environment
5. An SSH terminal client

A couple of notes here. Because at work we keep everything in version control and deploy to production by pulling from origin/master, thus obviates the need for an SCP client. And because I work mainly on back-end stuff, and am not a designer, I don't need Photoshop. But I do need to have some kind of image editor to do basic things like file type conversion and resizing. Finally, as someone accustomed to working in a basic text editor I don't need a full-fledged IDE; I can do quite well without coloured code and autocompletion, thanks.

It turns out there are Chrome apps to fill all these needs:
1. Text editor: [Codenvy IDE](https://chrome.google.com/webstore/detail/codenvy-ide/lefigjbiimiemfhjmibbgemkpenelmag)
2. Image editor: [Pixlr](https://chrome.google.com/webstore/detail/pixlr-editor/icmaknaampgiegkcjlimdiidlhopknpk)
3. Version Control: there's a git client built right into Codenvy
4. A test environment: Support for various PaaS cloud services is built right into Codenvy. For Node I'll be using [OpenShift by Redhat](https://www.openshift.com/)
5. An SSH client: [Secure Shell](https://chrome.google.com/webstore/detail/secure-shell/pnhechapfaindjhompbnflcldabbghjo)

All from your browser, and all free or with free levels of service that appear to more than suffice for my development needs. And if you need other tools, there are video editors, sound editors, flow chart editors, productivity tools, and on and on. If this works out I might be able to have a full dev environment in a Chromebook. Wish me luck.

* I'm actually quite proud of what we've accomplished there. You can clone our Vagrant repo, type `vagrant up somesite`, and have a working local copy of any of our websites, with each website's app repo freshly cloned, and last night's production database backup provisioned and ready.