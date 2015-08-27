---
layout: post
title: Creating Alignment Maps with Graphviz
share: y
---

About a week ago, I read on <a href="http://martinfowler.com/" target="_blank">Martin Fowlers blog</a> a post by <a href="http://www.sriramnarayan.com/" target="_blank">Sriram Narayan</a> about a model he calls <a href="http://martinfowler.com/bliki/AlignmentMap.html" target="_blank">Alignment maps</a>.

A bit simplified the concept is to map and visulize business outcomes to action items in IT so that the business can see how their needs are transformed into actions and to help IT get and keep focus on the business outcomes their work is ment to adress. I encurage you to read the <a href="http://martinfowler.com/bliki/AlignmentMap.html" target="_blank">post</a> because the concept is as simple as it is brilliant! 

In a <a href="https://twitter.com/larsbarkman/status/633918729542336512" target="_blank">tweet</a> after reading the post I stated that Git, Graphviz and a text editor was the only tools needed to produce and maintain alignment maps and in this post I'll show you how to create an alignment map with <a href="http://www.graphviz.org/" target="_blank">Graphviz</a>.

<img src="/images/Tweet_AlignmentMaps.png" alt="Tweet Alignment Maps">

##What is Graphviz (<a href="http://www.graphviz.org/" target="_blank">source</a>)?
Graphviz is open source graph visualization software. Graph visualization is a way of representing structural information as diagrams of abstract graphs and networks. It has important applications in networking, bioinformatics,  software engineering, database and web design, machine learning, and in visual interfaces for other technical domains. 

The Graphviz layout programs take descriptions of graphs in a simple text language, and make diagrams in useful formats, such as images and SVG for web pages; PDF or Postscript for inclusion in other documents; or display in an interactive graph browser.  Graphviz has many useful features for concrete diagrams, such as options for colors, fonts, tabular node layouts, line styles, hyperlinks, and custom shapes.

***Note: For instructions on installing Graphviz, please see this <a href="http://www.graphviz.org/Download..php" target="_blank">page</a>.***
</br>

##Layout components of an Alignment Map
- Four columns, each with a label and color
- "Nodes" for outcome/initiativ/actions, each with a label and color 
- Directional connections between the nodes
</br></br>

##Basic layout of the source file
First, I'll create a new file with a code editor and name it AlignmentMap.dot, changing the name is obviously fine as long as the corresponding change is made to the command line instructions below.

Second, I need to define what kind of graph we are creating, the direction of the graph and a few general layout elements. One other thing that is a "nice to have" rather than necessary, is having a header like in normal programming stating the author, creation date, where to find the changelog and the intent of the "code".

***Note: The source below is not properly formatted due to that <a href="https://bitbucket.org/birkenfeld/pygments-main/issues/1024/add-dot-lexer-graphviz-language" target="_blank">Pygments</a> don't (yet?!) have a lexer for the dot-language.***

***Note: The below source will not show any graph if generated due to it lacking nodes.***

{% highlight ruby %}
digraph AlignmentMap {
	/*
    /*
    Author: Lars Barkman
    Created: 2015-08-25
    Changelog: See version control system

    This is an example of an Alignment Map visualized with the help of Graphviz.
    This solution depends on either generation or maintaining a .dot file and from that generating a image or document.
    Personally, I think that editing the file by hand should be fine if the naming conventions used are intuitive.
    Alignment maps first came to my attention on Martin Fowlers blog (http://martinfowler.com/bliki/AlignmentMap.html).
    */

	// General layout of the graph
	rankdir=LR; // Direction of the graph Left to Right
    graph [style=filled, splines=line]; // Fills the subgraphs and defines the layout of the connections
    rank = same; // Makes sure that nodes are properly aligned even without a connection

}
{% endhighlight %}
</br>

##Creating the columns
The columns are created using subgraphs and each subgraph has it's own label and color. 

***Note: The name of a subgraph has to start with "cluster_" to work.***

***Note: The below source will not show any graph if generated due to it lacking nodes.***

{% highlight ruby %}
digraph AlignmentMap {
	/*
    /*
    Author: Lars Barkman
    Created: 2015-08-25
    Changelog: See version control system

    This is an example of an Alignment Map visualized with the help of Graphviz.
    This solution depends on either generation or maintaining a .dot file and from that generating a image or document.
    Personally, I think that editing the file by hand should be fine if the naming conventions used are intuitive.
    Alignment maps first came to my attention on Martin Fowlers blog (http://martinfowler.com/bliki/AlignmentMap.html).
    */

	// General layout of the graph
	rankdir=LR; // Direction of the graph Left to Right
    graph [style=filled, splines=line]; // Fills the subgraphs and defines the layout of the connections
    rank = same; // Makes sure that nodes are properly aligned even without a connection

    // Column for Business Outcomes
    subgraph cluster_business_outcome {
        label="Business Outcomes"
        graph [color=pink];

    }

    // Column for IT Outcomes
    subgraph cluster_IT_outcome {
        label="IT Outcomes"
        graph [color=mistyrose2];

    }

    // Column for IT Initiatives
    subgraph cluster_IT_initiatives {
    	label="IT Initiatives"
        graph [color=papayawhip];

    }

    // Column for Action Items
    subgraph cluster_action_items {
		label="Action Items"
        graph [color=darkseagreen1];

    }

}
{% endhighlight %}
</br>

##Adding the nodes
The nodes are added to the column (subgraph) they belong to and when adding the nodes I also add the default layout of the nodes in the general layout section of the source. 

***Note: To get a better looking node I've added "\n" in some labels to break the label into two rows.***

***Note: The below source will generate a graph but the direction of the subgraphs will be "wrong" due to missing connections.***

{% highlight ruby %}
digraph AlignmentMap {
	/*
    /*
    Author: Lars Barkman
    Created: 2015-08-25
    Changelog: See version control system

    This is an example of an Alignment Map visualized with the help of Graphviz.
    This solution depends on either generation or maintaining a .dot file and from that generating a image or document.
    Personally, I think that editing the file by hand should be fine if the naming conventions used are intuitive.
    Alignment maps first came to my attention on Martin Fowlers blog (http://martinfowler.com/bliki/AlignmentMap.html).
    */

	// General layout of the graph
	rankdir=LR; // Direction of the graph Left to Right
    graph [style=filled, splines=line]; // Fills the subgraphs and defines the layout of the connections
    rank = same; // Makes sure that nodes are properly aligned even without a connection
    node [style="rounded,filled",color=black,shape=box,fillcolor=white]; // Defines the default layout of the nodes

    // Column for Business Outcomes
    subgraph cluster_business_outcome {
        label="Business Outcomes"
        graph [color=pink];

        business_outcome_Customer_Acquisition [label="Customer\nAcquisition"];
        business_outcome_Customer_Retention [label="Customer\nRetention"];
        business_outcome_Cost_of_Operations [label="Cost of\nOperations"];

    }

    // Column for IT Outcomes
    subgraph cluster_IT_outcome {
        label="IT Outcomes"
        graph [color=mistyrose2];

        IT_outcome_Platform_Unbundling [label="Platform\nUnbundling"];
        IT_outcome_Site_Ux [label="Site Ux"];
        IT_outcome_Site_Performance [label="Site\nPerformance"];
        IT_outcome_Site_Scalability [label="Site\nScalability"];

    }

    // Column for IT Initiatives
    subgraph cluster_IT_initiatives {
    	label="IT Initiatives"
        graph [color=papayawhip];

        IT_initiatives_API [label="API"];
    	IT_initiatives_Pluginize [label="Pluginize"];
    	IT_initiatives_Responsive_Rewrite [label="Responsive\nRewrite"];
    	IT_initiatives_Catalog_Performance [label="Catalog\nPerformance"];
    	IT_initiatives_Sharding [label="Sharding"];

    }

    // Column for Action Items
    subgraph cluster_action_items {
		label="Action Items"
        graph [color=darkseagreen1];

        action_items_0 [label="..."];
		action_items_1 [label="..."];
		action_items_App_X [label="App X"];
		action_items_Search_In_One [label="Search-\nIn-One"];
		action_items_4 [label="..."];

    }

}
{% endhighlight %}
</br>

##Adding the connections
The nodes where added to each subgraph but the connections between the nodes go across the boundries of the subgraphs so they are added after the last subgraph.

{% highlight ruby %}
digraph AlignmentMap {
	/*
    /*
    Author: Lars Barkman
    Created: 2015-08-25
    Changelog: See version control system

    This is an example of an Alignment Map visualized with the help of Graphviz.
    This solution depends on either generation or maintaining a .dot file and from that generating a image or document.
    Personally, I think that editing the file by hand should be fine if the naming conventions used are intuitive.
    Alignment maps first came to my attention on Martin Fowlers blog (http://martinfowler.com/bliki/AlignmentMap.html).
    */

	// General layout of the graph
	rankdir=LR; // Direction of the graph Left to Right
    node [style="rounded,filled",color=black,shape=box,fillcolor=white]; // Defines the default layout of the nodes
    graph [style=filled, splines=line]; // Fills the subgraphs and defines the layout of the connections
    rank = same; // Makes sure that nodes are properly aligned even without a connection

    // Column for Business Outcomes
    subgraph cluster_business_outcome {
        label="Business Outcomes"
        graph [color=pink];

        business_outcome_Customer_Acquisition [label="Customer\nAcquisition"];
        business_outcome_Customer_Retention [label="Customer\nRetention"];
        business_outcome_Cost_of_Operations [label="Cost of\nOperations"];
    }

    // Column for IT Outcomes
    subgraph cluster_IT_outcome {
        label="IT Outcomes"
        graph [color=mistyrose2];

        IT_outcome_Platform_Unbundling [label="Platform\nUnbundling"];
        IT_outcome_Site_Ux [label="Site Ux"];
        IT_outcome_Site_Performance [label="Site\nPerformance"];
        IT_outcome_Site_Scalability [label="Site\nScalability"];
    }

    // Column for IT Initiatives
    subgraph cluster_IT_initiatives {
    	label="IT Initiatives"
        graph [color=papayawhip];

    	IT_initiatives_API [label="API"];
    	IT_initiatives_Pluginize [label="Pluginize"];
    	IT_initiatives_Responsive_Rewrite [label="Responsive\nRewrite"];
    	IT_initiatives_Catalog_Performance [label="Catalog\nPerformance"];
    	IT_initiatives_Sharding [label="Sharding"];
    }

    // Column for Action Items
    subgraph cluster_action_items {
		label="Action Items"
        graph [color=darkseagreen1];

		action_items_0 [label="..."];
		action_items_1 [label="..."];
		action_items_App_X [label="App X"];
		action_items_Search_In_One [label="Search-\nIn-One"];
		action_items_4 [label="..."];
    }

    // Connections between nodes in the different columns
    // business_outcome_* -> IT_outcome_Platform_*
    business_outcome_Customer_Acquisition	-> IT_outcome_Platform_Unbundling;
    business_outcome_Customer_Acquisition	-> IT_outcome_Site_Ux;
    business_outcome_Customer_Retention		-> IT_outcome_Site_Ux;
    business_outcome_Customer_Retention		-> IT_outcome_Site_Performance;
    business_outcome_Cost_of_Operations		-> IT_outcome_Site_Performance;
    business_outcome_Cost_of_Operations		-> IT_outcome_Site_Scalability;
    // IT_outcome_* -> IT_initiatives_*
    IT_outcome_Platform_Unbundling			-> IT_initiatives_API;
    IT_outcome_Platform_Unbundling			-> IT_initiatives_Pluginize;
	IT_outcome_Site_Ux						-> IT_initiatives_Responsive_Rewrite;
	IT_outcome_Site_Performance				-> IT_initiatives_Catalog_Performance;
	IT_outcome_Site_Scalability				-> IT_initiatives_Sharding;
	// IT_initiatives_* -> action_items_*
	IT_initiatives_API						-> action_items_0;
	IT_initiatives_Pluginize				-> action_items_1;
	IT_initiatives_Responsive_Rewrite		-> action_items_App_X;
	IT_initiatives_Catalog_Performance		-> action_items_Search_In_One;
	IT_initiatives_Sharding					-> action_items_4;

}
{% endhighlight %}
</br>

##Qualitative benefits validation
I had to deviate a bit from the original model on this one and instead of coloring the area around the node I colored the node itself. The result is different and I'm not sure if it's better or worse. There might be something that could be done so it would look like the original model, but I have not had the time to dig into it.

{% highlight ruby %}
digraph AlignmentMap {
    /*
    /*
    Author: Lars Barkman
    Created: 2015-08-25
    Changelog: See version control system

    This is an example of an Alignment Map visualized with the help of Graphviz.
    This solution depends on either generation or maintaining a .dot file and from that generating a image or document.
    Personally, I think that editing the file by hand should be fine if the naming conventions used are intuitive.
    Alignment maps first came to my attention on Martin Fowlers blog (http://martinfowler.com/bliki/AlignmentMap.html).
    */

    // General layout for the graph
    rankdir=LR; // Direction of the graph Left to Right
    node [style="rounded,filled",color=black,shape=box,fillcolor=white]; // Defines the default layout of the nodes
    graph [style=filled, splines=line]; // Fills the subgraphs and defines the layout of the connections
    rank = same; // Makes sure that nodes are properly aligned even without a connection

    // Column for Business Outcomes
    subgraph cluster_business_outcome {
        label="Business Outcomes"
        graph [color=pink];

        business_outcome_Customer_Acquisition [label="Customer\nAcquisition", fillcolor=red];
        business_outcome_Customer_Retention [label="Customer\nRetention", fillcolor=chartreuse2];
        business_outcome_Cost_of_Operations [label="Cost of\nOperations", fillcolor=chocolate1];
    }

    // Column for IT Outcomes
    subgraph cluster_IT_outcome {
        label="IT Outcomes"
        graph [color=mistyrose2];

        IT_outcome_Platform_Unbundling [label="Platform\nUnbundling", fillcolor=red];
        IT_outcome_Site_Ux [label="Site Ux", fillcolor=chartreuse2];
        IT_outcome_Site_Performance [label="Site\nPerformance", fillcolor=chocolate1];
        IT_outcome_Site_Scalability [label="Site\nScalability", fillcolor=chocolate1];
    }

    // Column for IT Initiatives
    subgraph cluster_IT_initiatives {
        label="IT Initiatives"
        graph [color=papayawhip];

        IT_initiatives_API [label="API", fillcolor=chartreuse2];
        IT_initiatives_Pluginize [label="Pluginize", fillcolor=red];
        IT_initiatives_Responsive_Rewrite [label="Responsive\nRewrite", fillcolor=chartreuse2];
        IT_initiatives_Catalog_Performance [label="Catalog\nPerformance", fillcolor=red];
        IT_initiatives_Sharding [label="Sharding", fillcolor=chocolate1];
    }

    // Column for Action Items
    subgraph cluster_action_items {
        label="Action Items"
        graph [color=darkseagreen1];

        action_items_0 [label="..."];
        action_items_1 [label="..."];
        action_items_App_X [label="App X", fillcolor=chartreuse2];
        action_items_Search_In_One [label="Search-\nIn-One", fillcolor=red];
        action_items_4 [label="..."];
    }

    // Connections between nodes in the different columns
    // business_outcome_* -> IT_outcome_Platform_*
    business_outcome_Customer_Acquisition   -> IT_outcome_Platform_Unbundling;
    business_outcome_Customer_Acquisition   -> IT_outcome_Site_Ux;
    business_outcome_Customer_Retention  	-> IT_outcome_Site_Ux;
    business_outcome_Customer_Retention  	-> IT_outcome_Site_Performance;
    business_outcome_Cost_of_Operations  	-> IT_outcome_Site_Performance;
    business_outcome_Cost_of_Operations  	-> IT_outcome_Site_Scalability;
    // IT_outcome_* -> IT_initiatives_*
    IT_outcome_Platform_Unbundling          -> IT_initiatives_API;
    IT_outcome_Platform_Unbundling          -> IT_initiatives_Pluginize;
    IT_outcome_Site_Ux                      -> IT_initiatives_Responsive_Rewrite;
    IT_outcome_Site_Performance             -> IT_initiatives_Catalog_Performance;
    IT_outcome_Site_Scalability             -> IT_initiatives_Sharding;
    // IT_initiatives_* -> action_items_*
    IT_initiatives_API                      -> action_items_0;
    IT_initiatives_Pluginize                -> action_items_1;
    IT_initiatives_Responsive_Rewrite       -> action_items_App_X;
    IT_initiatives_Catalog_Performance      -> action_items_Search_In_One;
    IT_initiatives_Sharding                 -> action_items_4;

}
{% endhighlight %}
</br>

##Generating output from the source
After completing the needed "source code" we are now ready to generate the output.

Graphviz supports many output formats but I prefer SVG mainly because the generated file is searchable on the page, can be indexed and you can add functionality like e.g. adding explanatory text when "mouse-over" or add a clickable URL to both nodes and connections.

If at command line you are standing in the folder where the source file is located and the name of the file is AlignmentMap.dot the following command will generate a SVG with the name AlignmentMap.SVG in the same folder.

{% highlight ruby %}
dot -T svg AlignmentMap.dot -o AlignmentMap.svg
{% endhighlight %}

In the final result below I choose to generate and show a png-image just for convenience and as you can see the only tweek I had to do was changing the type of file output and the file ending.

{% highlight ruby %}
dot -T png AlignmentMap.dot -o AlignmentMap.png
{% endhighlight %}
</br>

##The final result
<img src="/images/AlignmentMap.png" alt="The final result">
</br>

This was actually all it took to generate a basic Alignment Map. We did everything manually but there is nothing preventing this file from being generated (to various degree depending on the data accessible) by e.g. <a href="https://pypi.python.org/pypi/graphviz" target="_blank">a Python script</a> based on data from other systems.

Now, add your own nodes & connections and go reap the benefits of better alignment between the business and IT!

But remember that communication and collaboration is always more important than perfect models and <a href="/2015/05/20/the-three-most-important-laws-for-it-architects/" target="_blank">Boyds law of iteration</a> have taught us to get the model out into the real world quickly (to get feedback and improve) rather than trying to make it perfect the first time around.

In a later post I'll discuss using Git (via GitHub) to enable multiple people to work on the same map at the same time and having Git manage eventual conflicts.
</br>

If you think that there is something I missed, could be improved or just want to get in touch, please contact me on Twitter <a href="https://twitter.com/larsbarkman" target="_blank">@larsbarkman</a>