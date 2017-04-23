---
layout: post
title: "Long Journey to Emacs"
#date: 2017-04-23 12:00:00
categories: experience
tags: [experience, tools]
preface: "The story about my adventures in the lands of Emacs."
---

Half a year ago I finally changed my main text editor to Emacs. It was a long journey, full of adventures and discoveries.

## The Steps Taken

As I already said it was a long journey.

My first experience with code editing I received long ago in the text editor if Xcode. I don't really remember it, I just started to learn how to code, I was doing exercises from Apple Developer Portal on MacOS development at the early days of MacOS X. The 10-12 years old boy tried his typed words into text field, pressed 'Build' button, looked into console output and tried to decrypt alien symbols of compiler error. The only thing from that times I carried through the years is the love of colors and fancy conde highlighting (except curiosity, of course).

The next stop for me was TextMate. We had Fortran course in the university. We used some sort of IDE on windows machines, but at home I had Mac. TextMate became my best friend, while I was learning how to compile programs using command line `gfortran`. At the time I realised that a thing that compiles and works on Mac could fail on Windows, so my friend and I decided about checking my code on his Windows machine too. I wrote code, sent it to the friend of mine, he compiled it and sent errors back if any. Code highlighting was really useful again.

A year later (it was 2007-2008), my beloved Mac died. I tried to repair it, but unsuccessfully. At the time I had to do quite a lot of chores for math and physics, which included a lot of repeating tasks, and I was curious about using programming to solve problems of physics (we, naive students, had not been told that they use computers successfully to do so for years). I had no choice but to buy PC laptop. This brought me to the land of frustration and anger. Every single thing that I tried was bad, unresponsive, ugly,... I tried a lot of things. There were Visual Studio, Eclipse, Notepad++, a bunch of other things on Windows. I tried to live with Linux, but it was almost unusable for my studies (we had custom software for homeworks, that was not built for Linux and could not be run on it even with Wine). Fortunately, Visual Studio 2008 and then 2010 happened and I found enough perseverance to set up Notepad++. That time I played with C/C++ and Fortran for the university tasks and tried to dive into the land of web with Ruby, JavaScript and C# (Ruby on Windows? huh...).

Next stop of my journey was in the lands of Java. I started working as a Software Test Engineer in an enterprise company, that was writing software on IBM platform. Part of my job was to automate testing. I was introduced to IntelliJ products and I worked with Eclipse too due to policy restrictions of our customers. Also that period of my life taught me some vi/vim (and yes, I closed it by killing it from another session or terminating ssh access several times before I learned about modes and key sequences).

I changed job, but IntelliJ IDEA was still with me. I believe it still is the best IDE for Java. Then the language changed from Java to Scala. Fortunately, IDEA already had a plugin for Scala, so I had not change my tool. I had two instances of IDEA installed for the case if Scala plugin breaks, but it was ok.

While doing heavy Java/Scala coding in IDEA, I used Sublime Text for JavaScript/Ruby/other thing. The feel of using Sublime was very pleasurable. Multiline editing, formatting, code highlighting, plugins and ability to customize were so good.

After some time of happy coding, I saw a post that GitHub would release Atom. The product of GitHub could not be bad, could it? So, I gave it a try. After several month of usage, when the euphoria of GitHub product usage weathered, I realised that it is slower than Sublime and it cannot handle large files (database dump editing? no chance). I switched back to Sublime.

I also tried VSCode recently, but it was not so good to consider switching from Sublime.

## Introduction to Emacs

I was introduced to Emacs when started to read the Clojure for Brave and True book. It has a whole chapter dedicated to Emacs and working with Clojure in it. I worked through several chapters of the book, but gave up. There were two reasons for it: the learning curve for both Emacs and Clojure combined was too steep and I had no motivation to learn more, as I had no chance to use Clojure at daily life. But there was a side effect, playing with Emacs awaked forgotten feelings of learning tool and excitement of discoveries (like on Mac when you realise that there is a fancy hidden feature).

Some time passed, I decided to go back and try Emacs again. I don't really remember why I decided to do so. I remember that I started to work on my own config, setting up plugins, theme,... The only thing that I did not do was actual work. I did not use Emacs for any tasks except setting it up. The result is pretty predictable. I gave up on that. But feelings were there, the magic of brackets of Emacs Lisp was there, excitement of learning was there...

Half a year ago, after buying new laptop, I made a decision to finally switch to Emacs. I installed Emacs and only it. I forbade myself to use Sublime. I started tweaking Emacs as I was doing programming as I needed and here I am. I happily use it for a half a year, it is still not polished, it does not have some fancy features, but speed of development and excitement of usage cool tool increased.

## Details

The ability to do you tasks when opening Emacs for the first time is awesome. It can be slower than in other editors as you almost cannot use mouse, but you still have ability to navigate around words and letter with arrow keys, keyboard strokes do what you expect to do and then you start learning that there are other ways to do things, command sequences to make magic with code. Step by step learning brings a lot of excitement. I don't feel this in Vim as you have to learn some of it before using it, for example.

What I really love about Emacs is its endless customizability. Full-sized language embedded into text editor is a great thing. Brackets can be intimidating, but there is some kind of magic behind Lisps.

Also, having full-sized language as customization tool enables ability to constantly polish your experience and invent tools that you need as you go without need of doing complex writing. It also deepens learning curve, so user has endless potential to learn.

There is a selfish feeling of being a part of the cool community. All cool kids use Emacs and Vim, don't they?

I don't want to go into details of my customizations and code, but I have to write about some tools I fell in love with. One of them is neotree - filesystem browser like one we have in Sublime. Org-mode is very cool. `scratch` buffer is very nice, I know there are extensions for other text editors that implement this, but having this for free is not that bad. There are lots of mods for almost every language and task you can encounter. The only thing that I did not find was good integration with flow type checker for JavaScript.

The only bad detail I have is that Emacs does not have good native look and feel on Mac, but I use it in full screen mode anyway, so it's not a problem.

I also cannot leave one of the best sources of information that helped me a lot with my first steps, it was a blog of [Sacha Chua](http://sachachua.com/blog/).

As a conclusion, now I am happy Emacs user. I still use IntelliJ IDEA for Scala, but I'd love to migrate to Emacs even this. Also, I wish there was a book like Practical Vim but about Emacs.
