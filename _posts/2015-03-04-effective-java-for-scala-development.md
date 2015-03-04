---
layout: post
title:  "Effective Java for Scala development"
date:   2015-03-04 11:44:58
categories: books
tags: [books, scala, java]
---

I have avoided reading 'classical' developer literature for years. I thought

But now, my curiosity has got the better and I took the _"Effective Java (2nd Edition)"_ by Joshua Bloch [\[1\]](#1). I can say that my assumptions were wrong, 'classical' reading can be interesting and helpful if read carefully.

Lets discuss this book from position of Scala developer.

## Overview

Book is written in 2008 and for Java 1.6 so some concepts can be outdated and we have several improvements in Java and JVM in 1.7 and 1.8. But, talking about concepts described in the book, understanding of them will help you to write more readable and robust code and understand design of several features in Scala.

Not all concepts described can be applied strictly to Scala development (for example we have _values_ in Scala to get rid of _something final_ fields). The other part of solutions are applied in Scala by language design (for example nice _toString_ method implementation for _case_ classes). The third part cannot and should not be implemented in Scala programs (_Builder pattern_, for example, we have other solution like parameters with _default values_).

Anyway, after reading _"Effective Java (2nd Edition)"_ you will understand and appreciate Scala design even more and you'll get the some of core Scala developer ideas.

## Interesting chapters

As for me, the most interesting chapters are:

* chapter 3: Methods Common to All Objects
* chapter 4: Classes and Interfaces
* chapter 5: Generics

The 3rd and 4th chapter gives you information on how _case_ classes are implemented and what boilerplate code you get by no cost. Also, you get arguments for using _companion object_ with _apply_ method (that could be overloaded for your needs) with private constructor.

4th chapter answers the question about why you should use _values_ instead of _variables_ as much as possible, too, and gives guides when and how to use _traits_ and _abstract classes_ in your code.

5th chapter describes the way you should use generalized classes, methods, and collections instead of plain ones. This concept should be the same for Java and Scala development.

## Chapters to avoid

I think, you should avoid chapter 9 "Exceptions" and chapter 10 "Concurrency".

The way Scala uses Exceptions in its core and the way we use it in application code is quite different to Java. As more algebraic (as its functional nature) language, Scala provides tools for writing code without side effects and ignoring type safety, so you should use native tools and concepts instead of common-to-Java ones.

On "Concurrency" chapter my argument is the same. _Akka_ is default model for implementing concurrency and parallelism in Scala.
It is build on Erlang concurrency/parallelism model, so we should use Erlang guidelines to implement multithreaded programs in Scala.

## Conclusion

_"Effective Java (2nd Edition)"_ by Joshua Bloch [\[1\]](#1) is a good book if you want to improve your coding style and understand the concepts of JVM programming more deeply.
But, if you are not a full-time Java programmer, and use Scala most of time you should read this type of literature very carefully, reflecting solutions described on guidelines of Scala.
If you are using something like Scheme or Clojure, this reading will be useless for you (as your language has nothing with Object Oriented Design and other OO concepts :)). 

## Links and other sources

[1<a name="1"></a>] "Effective Java (2nd Edition)" by Joshua Bloch, ISBN-13: 860-1300201986, ISBN-10: 0321356683, [amazon](http://www.amazon.com/Effective-Java-Edition-Joshua-Bloch/dp/0321356683)
