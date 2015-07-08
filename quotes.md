---
layout: page
title: QUOTES FOR SOFTWARE ENGINEERS
---

> ”Premature optimization is the root of all evil”
> 
> – Donald Knuth

Donald Knuth's quote is naturally important but incredibly hard to relate to if you work with "organizations" who do not understand and appreciate refactoring of code.

Kent Beck have also addressed that optimization should not be done too early...

> “Make It Work, Make It Right, Make It Fast”
> 
> - Kent Beck

This is the quote that I have had as my main guiding principle in recent years. It brilliantly weaves together the ideas of first creating a prototype to show that the initial concept is correct, then refactor the code to "production quality" and then as a last step improve the performance if there is a concrete need for it.



> ”It is pointless to do with more what can be done with fewer”
> 
> – William of Ockham  

I guess some Swedish politicians might argue with this ;-)


> ”Assumption is the mother of all screw ups”
> 
> – Mr. Eugene Lewis Fordsworthe  

Sounds so simple and still it's so hard!

> ”The only constant is change”
> 
> – Heraclitus  

Exactly, embrace change and make it work for you "resistance is futile" ;-)



> ”The only constant is change”
> 
> – George Box

This is probably the only justification I'd like to give to all who think that modeling before coding is a waste because "it is still not the solution"...



> The Five Stages of Model Development
> 
> 1) Decide what you want the model to do
> 
> 2) Decide how to build the model
> 
> 3) Build the model
> 
> 4) Debug the model
> 
> 5) Trash stages 1-4 and start again, now that you know what you really wanted.
> 
> – Donald Knuth

It's easy to miss the first two paragraphs, just as it is easy to miss developing good requirements and select the programming language (<a href="http://youtu.be/NvWTnIoQZj4">you are not only using one language, are you</a>?! ;-) ).

A model can, in practice be anything such as a graphical notation, PoC, Lego etc. Personally, I work happily with graphical representations of flows and conditions of the notations <a href="http://en.wikipedia.org/wiki/ArchiMate">Archimate</a>, <a href="http://en.wikipedia.org/wiki/Business_Process_Model_and_Notation">BPMN</a> and <a href="http://en.wikipedia.org/wiki/Unified_Modeling_Language">UML</a>. Which (sometimes What) notation I use is fully determined by the first point i.e. what the model should illustrate and who have an interest in it (do not show UML to the "business"!).



> ”If you can't explain it to a six year old, you don't understand it yourself”
> 
> – Albert Einstein

It's always tough to realize that I reallyn didn't understand it as good as I thought :-(

> ”Everything should be made as simple as possible, but no simpler”
> 
> – Albert Einstein

Sir Jonathan Ive is now perhaps the most famous proponent (<a href="http://www.telegraph.co.uk/technology/apple/9283706/Jonathan-Ive-interview-simplicity-isnt-simple.html">TELEGRAPH.CO.UK</a>, <a href="http://youtu.be/1jdPKi5i030">YouTube</a>) for the spirit of this quote, although I've never read / heard him use this particular quote.



> ”To get a large model to work you must start with a small model  that works, not a large model that doesn't work”
> 
> – Alan Manne

So very true and it is equally applicable to code that in organizations.

My personally most inspiring model for fixing a large model that does not work is Lockheed Martin's <a href="http://en.wikipedia.org/wiki/Skunk_Works">Skunk Works</a>... Start over!



> ”This is the Unix philosophy: Write programs that do one thing and do it well. Write programs to work together. Write programs to handle text streams, because that is a universal interface.”
> 
> – Doug McIlroy  

Doug McIlroy's quote is philosophically always good but if you read it more practically from a modern perspective, it is as equally valid? Certainly, when it comes to applications housed on "one machine", but what about with distributed systems?

A distributed system has no "programs" and there is also small possibilities to 'stdin / stdout / stderr "... But what if we replace the word "programs" with "components" and looks at "streams" as APIs (ie it should be text (JSON / XML / CSV) and not binary format that is communicated), it becomes equally relevant for distributed systems!

Apologies for that, I take the liberty to write about Doug's quote but here goes...

”Write components that do one thing and do it well. Write components to work together. Write components to handle text streams through (http) APIs, because that is a universal interface.”



Another very good quote from Doug's
> ”The notion of "intricate and beautiful complexities" is almost an oxymoron. Unix programmers vie with each other for "simple and beautiful" honors — a point that's implicit in these rules, but is well worth making overt.”
> 
> – Doug McIlroy