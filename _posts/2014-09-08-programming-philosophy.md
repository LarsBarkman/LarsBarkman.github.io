---
layout: post
title: My Current Programming Philosophy
---

An articulated and communicated programming philosophy is fundamental to continuously deliver quality in "software development".

It's also very important to have a personal philosophy as a beacon when navigating "dangerous waters" in projects and as a filter for marketing buzzwords/new products that is supposed to make everything better...

The word philosophy could be replaced by principles/qualities and programming with architecture/development without changing the outcome. I personally like the softer and more artisan feel of <a href="http://en.wikipedia.org/wiki/Unix_philosophy" target="_blank">Unix philosophy</a> then the more business oriented <a href="http://msdn.microsoft.com/en-us/library/ee658124.aspx" target="_blank">Key Principles of Software Architecture</a>, that's the reason I call this "Programming Philosophy" rather then "Principles...".

It's a number of years since I was a professional programmer but strangely I appreciate good craftsmanship from programmers much more as an architect then I ever did as a developer...

So what do I base my principles on (besides the experience I gained myself)?

- The book "The Practice of Programming" written by B.W. Kernighan and R. Pike gives a number of rules (rather than philosophy) but it is nevertheless a very good summary of the basic principles of programming (<a href="http://abel.harvard.edu/computing/programming/rules.html">Summary of the rules</a>).
- Microsoft has a number of very good principles (<em><a href="http://msdn.microsoft.com/en-us/library/ee658124.aspx">Microsoft Developer</a></em><a href="http://msdn.microsoft.com/en-us/library/ee658124.aspx"> Network</a>).
- Eric Raymond's 17 Unix rules (<em><a href="http://en.wikipedia.org/wiki/Unix_philosophy">Wikipedia</a></em>)
- Mike Gancarz’s book “Linux and the Unix Philosophy”(<a href="http://read.pudn.com/downloads63/ebook/222048/Linux%20and%20the%20Unix%20Philosophy.pdf">PDF</a>, <a href="http://flylib.com/books/en/2.506.1.1/1/">HTML</a>)
- Doug McIlroy (<a href="http://en.wikipedia.org/wiki/Douglas_McIlroy">Wikipedia</a>), the man behind (among other things) <a href="http://en.wikipedia.org/wiki/Pipeline_(Unix)">Unix pipelines</a> have said many very sound things related to writing code for Unix, the principles, however, is universally applicable regardless of operating system.
- <a href="http://c2.com/cgi/wiki?SevenPrinciplesOfSoftwareDevelopment">Seven Principles of Software Development</a>
- And been inspired by <a href="http://en.wikipedia.org/wiki/List_of_software_development_philosophies">many more</a>

So when I now summarize my programming philosophy, I can proudly quote Sir Isaac Newton
> "If I have seen further it is by standing on the shoulders of giants"
> 
> - Sir Isaac Newton</blockquote>

(I have tried to link the more famous principles if you would like to read more about them)

+ **Designing the solution with this in mind...**
  - <a href="http://en.wikipedia.org/wiki/Separation_of_concerns">Separation of concerns</a>
  - <a href="http://en.wikipedia.org/wiki/Law_of_Demeter">Principle of Least Knowledge</a>
  - <a href="http://en.wikipedia.org/wiki/Don't_repeat_yourself">Don't Repeat Yourself (DRY)</a>
  - Do not duplicate functionality within an application
  - Prefer composition to inheritance
  - Be explicit about how layers communicate with each other
  - Use abstraction to implement loose coupling between layers
  - A component or an object should not rely on internal details of other components or objects
  - Do not overload the functionality of a component
  - Understand how components will communicate with each other
  - Define a clear contract for components
  - "<a href="http://c2.com/cgi/wiki?PrematureOptimization" target="_blank">Premature optimization</a> is the root of all evil"
  - with minimal upfront design
  - avoid <a href="http://flylib.com/books/en/2.506.1.34/1/">captive user interfaces</a>
  - design their programs to be flexible and open
  - design for the future by making their protocols extensible
  - design for visibility and discoverability by writing in a way that their thought process can lucidly be seen by future developers
  - design robust programs by designing for transparency and discoverability
  - design programs that fail in a manner that is easy to localize and diagnose or in other words “fail noisily”

+ **Build with this in mind...**
  - prototype as soon as possible
  - use automated QA techniques during development to maintain system quality

+ **BWrite code that...**
  - values portability over efficiency
  - <a href="http://flylib.com/books/en/2.506.1.17/1/">do one thing and do it well</a>
  - work together
  - handle text streams (I choose to include text-based protocols (JSON / XML / CSV) for http APIs here)
  - are "<a href="http://flylib.com/books/en/2.506.1.14/1/">Small, simple and beautiful</a>"
  - <span style="font-size: 14px; line-height: inherit;">store data in <a href="http://flylib.com/books/en/2.506.1.29/1/">flat </a></span><a href="http://flylib.com/books/en/2.506.1.29/1/">text files</a>
  - use <a title="Shell script" href="http://en.wikipedia.org/wiki/Shell_script">shell scripts</a> to increase leverage and portability
  - works as a <a title="Filter (Unix)" href="http://en.wikipedia.org/wiki/Filter_(Unix)">filter</a>

+ **Programmers should...**
  - build a program out of simple parts connected by well defined interfaces
  - write programs as if the most important communication is to the developer
  - write programs that can communicate easily with other programs
  - choose to make data more complicated rather than the procedural logic of the program when faced with the choice
  - value developer time over machine time, because machine cycles in 2014 are relatively inexpensive compared to prices in the 1970s