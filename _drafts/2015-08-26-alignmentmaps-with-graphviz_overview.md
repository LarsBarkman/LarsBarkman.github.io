---
layout: post
title: Creating Alignment Maps with Graphviz
share: y
---

About a week ago, I read on <a href="http://martinfowler.com/" target="_blank">Martin Fowlers blog</a> a post by <a href="http://www.sriramnarayan.com/" target="_blank">Sriram Narayan</a> about a modell he calls <a href="http://martinfowler.com/bliki/AlignmentMap.html" target="_blank">Alignment maps</a>.

A bit simplified the concept is to map and visulize business outcomes to action items in IT so that the business can see how their needs are transformed into actions and to help IT get/keep focus on the business outcomes there work is ment to adress. I encurage you to read the <a href="http://martinfowler.com/bliki/AlignmentMap.html" target="_blank">post</a> because the concept is as simple as it is brilliant! 

In a <a href="https://twitter.com/larsbarkman/status/633918729542336512" target="_blank">tweet</a> following reading the post I stated that Git, Graphviz and a text editor was the only tools that was needed to produce and maintain alignment maps and I thought that I would show you how to do that.

*Just to make it clear, this solution is not ideal for users not used to markup languages and version control systems but these days those are pretty common tools for most IT professionals. For those not yet familiar with markup languages and version control systems I think it would be time well spent to learn the very basic knowledge that is needed to get this solution to work, if just not for this solution then for general knowledge of technologies that could help almost every knowledge worker in their daily job.*

For a complete solution we require the following:

- Creating the alignment maps
- Keeping track of the changes to the maps
- Make it possible for several people to work with the same map at the same time
- Push new versions of the maps to a presentation server

##Creating the alignment maps
For both documents and graphs I like the modell of authors not having to worry too much about the appearance of their documents/graphs but to concentrate on getting the right content. <a href="http://www.graphviz.org/" target="_blank">Graphviz</a> is visualization software that takes a plain text source file and generate stunning graphs in a multitude of output formats.

##Keeping track of the changes to the maps

##Make it possible for several people to work with the same map at the same time

##Push new versions of the maps to the presentation server
This is a tricky one due to the fact that there are so many different types of presentation servers and different ways of presenting graphs.

Personally I'm very fond of wikis, much more than a document management system like e.g. Microsoft Sharepoint (I know Sharepoint can do more than that, but it's still not as flexible as a "real wiki" and NO Sharepoint is no real wiki even if it has wiki-like functionality) so for this example I'm going to automatically push the new versions of the map to <a href="https://www.dokuwiki.org/dokuwiki#" target="_blank">DokuWiki</a>.

*I know that there is a <a href="https://www.dokuwiki.org/plugin:graphviz" target="_blank">plugin</a> for Graphviz but then you loose most of the functionality that make it possible for several people to work with the same map at the same time that you get with e.g. Git.*

If you think that there is something I missed or just want to get in touch, please contact me on Twitter <a href="https://twitter.com/larsbarkman" target="_blank">@larsbarkman</a>