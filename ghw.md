Ghw
---------------

This documents a material-ui tutorial I am working on called ghw.

# Introduction

I have been working with Material-UI now for about one year and
over that time period I have worked on lots of different projects
that cover a range of topics and from that knowledge I have come
up with a tutorial that hits the highlights of things people need
to know.

Over time this tutorial will focus on a set of github repositories
that show developers real code used in
moderately complex real world applications.

## Living Document

If you want to add to this tutorial and or have an interesting
real world application
that highlights concepts not addressed in this tutorial
that uses Material-UI at the core of the architecture
and want to document
that application in the flow of this document
we can have a conversation about how to integrate

## Create React App

First and foremost I have decided to start out with all of the
tutorial repos using
[Create-React-App](https://github.com/facebook/create-react-app).

The reason for this decision is because if you look at the
[Material-UI doc](https://material-ui.com/) you will note that
it uses
[Nextjs](https://nextjs.org/) at the core for driving its documentation.

Initially, I thought ok cool, I want to build a Material-UI drawer system
that uses CRA (Create-React-App) instead of Nextjs. At the time, I was relatively new to using Material-UI and thought "oh this would be easy".  Turns out it was more tricky than I initially thought and it ended up taking me
weeks to really come up with a solution I was happy with.

So saving people time on just this one simple concept seemed like something
that would be valuable to have documented.  From there, I started working on
a more sophisticated application that used
[Menus](https://material-ui.com/demos/menus/) instead of [Drawers](https://material-ui.com/demos/drawers/) and by that time we are off to the races
so to speak.  Fast forward about a year, and I am finally getting around
to writing all of these concepts up along with polishing up some nice
repos that elucidate the concepts.

All of the code repositories that this tutorial will reference

## AppBar

At the top of the hierarchy are ways to organize information or
websites.  All websites need to have an
[AppBar](https://material-ui.com/demos/app-bar/)

## Menus

## Drawers

The main reason for focusing on React now is because of
[Facebook's Relay](https://facebook.github.io/relay/).  
For many years all of my development has been REST based.  But I am completely sold on Graphql and the power of having a defined query langage being used to get data on the backend.  Think SQL but instead of just relational databases you now have access to all sorts of backend systems that store data including blockchains, redis, Nosql, relational etc...

I have been working with backend
[Graphql systems](http://graphql.org/)
that use Graphql as their query language namely
[Dgraph](https://dgraph.io/)
and
[Github's new Graphql API](https://developer.github.com/v4/).

## Reactabular

When my design requirements need React Tables I always turn to
[Reactabular](https://reactabular.js.org)
as way to display tabular data.  For example, recently I have been working on a system that has the concept of a shopping cart.  So the user is presented with an Amazon like store front and they get to select products they want to purchase and "add to their cart".  Then they get to checkout.  There is also the concept of an inventory system which manages which products the user is able to purchase as well as a system that keeps track of all of the receipts posted.  All of these systems can use HTML tables to model their data structures that the end user sees.  These tabular systems extend across to other projects including buying and selling financial instruments.  You need to choose a stock to buy and this can easily be displayed using tables. Subsequently, there is a section which shows the end user the transaction log of their purchases.  Again, a tabular system to display the data is being used.

## Passport

Most systems that I develop need the ability to authenticate a user so they can log in.  A simple abstraction called
[Passport](http://passportjs.org/)
enables one to simply and easily integrate login functionality into your
[Express](https://expressjs.com/)
app which I use for most of my systems.

# Backend Systems

Having worked with large system deployments mainly on AWS, I am fascinated by the infancy of our industry in the understanding of what it takes to build systems that are robust, secure, and fault tolerant.

My career has been wide and varied but over the past couple of years I have been focusing on Golang programming in the area of products that uses the
[Raft algorithm](https://raft.github.io/)
as their underlying infrastructure for distributed computing and fault tolerance. Both
[Kubernetes](https://kubernetes.io/)
and
[Consul](https://www.consul.io/)
use Raft to allow for individual node failures but still maintaining state of the cluster system.  
Kubernetes underlying distributed storage system uses
[Etcd](https://coreos.com/etcd/).

[Consensus](https://en.wikipedia.org/wiki/Consensus_(computer_science)
in Etcd is based on a recent Stanford PhD thesis called Raft which enables replicated state machines to come to agreement on values you deem as important. Likewise,
[P2P](https://github.com/libp2p)
systems in blockchain based systems use Proof of Stake like voting systems and also Proof of Work to agree on values that need to be persisted long term in both the Bitcoin and Ethereum blockchains.

In the past, I worked on the
[Rkt spec](https://github.com/rkt/rkt)
which has integrations with Hashicorp's Nomad and Kubernetes.  I am also familiar in my past work with the internal workings of Docker via
[Systemd](https://github.com/systemd/systemd).

# Blockchain Systems

Besides containerized systems, I have also been working in the blockchain space working with P2P systems like Ethereum and Bitcoin working on new ways to search, store and retrieve data structures embedded in blockchains most recently with a new system called Noms.

In the Golang Bitcoin world my main focus was decred and btcsuite and more recently  in the world of ethereum focusing on backend P2P system and on front end Solidity contracts and tools associated with compiling, deploying and debugging namely web3.js and Truffle.

## Ethereum

One of the very cool things about writing and debugging the Solidity contracts is that one can simulate the Ethereum client with Testrpc which gives one the ability to use the Web3 provider interface namely handleRequest to simulate all of the Web3 calls that need to be instantiated and simulated. Testrpc in concert with Truffle is an invaluable resource for quickly testing all of the code paths that need to be checked when prototyping new Ethereum contracts using Solidity.

## Noms

My interest in blockchains goes deeper as I am delving into newer blockchain like Merkle DAG systems such as Noms.  From an information storage and retrieval architecture one can think of Noms as a new style of database that tracks individual inserts / commits but enables one to have complete control over their local data similar to the way git works.  Tying back into Ethereum one can think of running your own Ethereum private network that gives you the ability to use the power of Etheruem but in your own company where accounting for things no matter what it may be is very important.  The currency aspect of Ethereum is at the top of the stack so there are many other types of applications that are relevant to blockchain type systems that lend themselves well to systems like Noms.

# Graphql

For the past number of years I have been designing and building large scale API systems that use REST api endpoints.  Tools like Swagger are helpful for managing and automatically documenting the actual REST schemas that can then be generated for the different language implementations.

Recently, Facebook introduced the concept of
[Graphql](http://graphql.org/)
which is now starting to gain some traction.  It "changes the game" so to speak in how we think about and build out APIs to back end services.  Now instead of designing many different endpoints for different types of data, we are able to incorporate our complete data model into one schema that we can then query against very similar to an SQL query.  We now have a defined Query Language that uses JSON requests to get at the data which is then returned in JSON as well.

## The Dgraph Project

One of the front end research projects I am working on now, which is still in development has to do with saving off visualizations of subgraphs that are returned from a larger dgraph query.  Imagine a fairly large graph of data that gets returned when you query for one node and all of its children in a large dataset.  What you want to be able to do is save off sections of the graph for visualization and analysis reasons.  For now, the dgraph team only returns the whole graph, and then to visualize the subgraph you have to send in another query.  But I am working on the ability to click on one of the nodes in the subgraph and then just see that data and save it off as its own Json data structure.


# Machine Learning

I am very familiar with the field of Machine Learning having done my graduate studies in Computer Science in the fields of Artificial Intelligence and Neural Networks.  Python is my language of choice when working on AI projects due to the fact that the core mathematical libraries namely
[Numpy](http://www.numpy.org/)
is written in Python.
In the past I did a research project using
[Tensorflow](https://www.tensorflow.org/)
and
[Gensim](https://github.com/RaRe-Technologies/gensim).
Also, while working at Spinnakr we initiated a Machine Learning project
for use in intelligent data analytics.  However, this project was never launched into production.

# Front End Design History

I started
out designing front ends written in Java that ran both on the desktop and
in the browser using
[applets](https://en.wikipedia.org/wiki/Java_applet).

I have been developing front ends using Javascript since 2005.  
I was an early user of
[Jquery](https://jquery.com/) which was released a year later in 2006.
When
Node.js came out in 2009 that is when things picked up for me.  And
the first Javascript framework I used in earnest was
[Backbone.js](http://backbonejs.org/)

In the past I worked with
[Marionette](https://marionettejs.com/), the Backbone Framework,
and the simple application I developed can be found in my
[Github repo](https://github.com/stormabq/jobs).

[Here is a demo of the application](http://stormabq.github.io/jobs/)

I also worked for a software company in Buenos Aires, Argentina where I worked on front end development for a Spanish Language learning site.  While living in Los Angeles I worked at Caltech as a researcher in the Biology department where we developed
[CRdata](https://github.com/seerdata/crdata),
a Ruby on Rails front end to back end AWS jobs that ran Stem Cell Experiments.  The first version of the software which I also wrote was developed in Python using
[Django](https://www.djangoproject.com/).  At the time, we were using
[Protovis](http://mbostock.github.io/protovis/)
for our graphs and visualization, the precursor to
[Mike Bostock's popular Framework D3](https://d3js.org/).  

When D3 was released in February of 2011 I was living in Argentina but continued developing with D3 for various UI projects I was working on at the time.  Since that time I have also done extensive work with D3, but its been about 4 years am I am not currently up to speed again on D3.  Instead, the
[Dgraph team](https://dgraph.io/)
is using
[Vis.js](http://visjs.org/)
to do all of their rendering of the nodes and edges of the data returned from the Graphql query.

## Angular

I did some development work in
[Angular.js](https://angular.io/)
after finishing up several projects in Backbone.js.  Once I started using Angular I no longer worked with the Backbone.js framework.  I felt that Angular took me to the next level, and gave me the tools I needed to further develop the concept of a Single Page Application.  But with it came the complexity.  The beauty of Backbone.js was its simplicity, small code base and the ability to wrap your head around the concept at hand.  You could even study the Backbone.js code base and fairly quickly come up to speed on how it works.  Angular is highly complex, with lots of moving parts, and understanding intimately how Angular works could take weeks of work.  Whereas Backbone.js could be understood in days.

Then two things happened to derail Angular from its rockstar status.

1. Version 2 was written in Typescript
2. React started to get traction

## React

When
[React](https://facebook.github.io/react/)
was originally released in 2013 I was spending most of my time developing backend API systems, and when I was doing front end development I was happily using Angular.  But in the past year, when a project came up to do work on the front end I decided to try out react.  I can't say that I am blown away by React, but I am happily using it and the ecosystem is clearly solid.  The thing I do like about React is the simplicity of it.  Because it only deals with the View part of the UI, there are clearly not as many moving parts as Angular.  The downside is that, the view code is embedded inside the Javascript's file **render** method, and that to me is not perfect.  But for now, I am happily developing using React, and coming back up to speed on all of the CSS that needs to be used to make the UI look correct.  But I will admit that I am **NOT** a fancy UI designer and the UIs I design are very simple.  So having an excellent designer on board for me to work with is clearly important for sophisticated web applications.
