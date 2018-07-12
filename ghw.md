Material-UI Tutorial
---------------

This tutorial introduces some fundamental concepts that are helpful
to understand if you want to be a productive developer in the
Material-UI world.

# Introduction

I have been working with Material-UI now
since the release of
[v1.0.0-beta.3](https://github.com/mui-org/material-ui/releases/tag/v1.0.0-beta.3) on July 29, 2017 and
over that time period I have worked on lots of different projects
that cover a range of topics and from that knowledge I have come
up with a tutorial that hits the highlights of things people need
to know.

Over time this tutorial will focus on a set of github repositories
that show developers real code used in
moderately complex real world applications.

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

All of the code repositories that this tutorial will reference uses
CRA which means they all come out of the box the same way with the
same cadence of commands.

```sh
npm install
npm start
```

## AppBar

At the top of the hierarchy are ways to organize information or
websites.  All websites need to have an
[AppBar](https://material-ui.com/demos/app-bar/).  A nice example
of an AppBar in action is the
[Material-UI Home Page](https://material-ui.com/).  
There you will
see the Icon button for drawer open and close.  In these repos you
will see the same functionality.

## Menus

## Drawers


# Data Visualization Framework

I am in the process of developing a simple generic data visualization
framework in the context of a Material-UI tutorial with the main goal of
using this framework as a test bed for elucidating different aspects of
Material-UI.  So the tutorial and the framework will develop over time
in parallel.  As more interesting aspects of the framework get developed
the associated documentation teaching the Material-UI concepts of how it works will follow.

## The Overall Architecture of the framework

The concept is simple.  The framework supports views and JSON data.  

The views are any React component that can be accepted inside
[withStyles](https://material-ui.com/customization/css-in-js/#api).
Examples of this can be
[Grid Lists](https://material-ui.com/demos/grid-list/) with
[Cards](https://material-ui.com/demos/cards/) inside them to
[D3 graphs](https://github.com/stormasm/awesome-d3-react) depicting statistics inside the JSON data set.

The JSON data comes from any API call or endpoint that returns JSON data.  The API call can be GraphQL, REST, or static JSON data sources such as JSON files sitting on your local disk or in your Github repo.

## Github Worlds Data Visualization

Github Worlds (Ghw) is a Data Visualization Toolkit to display different types of views of data coming from the [Github API](https://developer.github.com/v4/).
Its a platform from which to develop new views of data that shows the power of
all of the information about open source tools, users, statistics and anything else that can be derived from this data possibly in concert with other data sets.

The data sets for Ghw are abstracted away from the underlying visualization so that the only thing needed to display the data is a JSON data file.  Eventually, we will provide a live view of the data; but for now with simplicity being urgent we decided to only require JSON data sets.  The generation of the JSON data sets is described in another part of this document.  For now, we are providing a test set of JSON data files to better understand the structure of the data along with the program which interprets the data and a sample set of views.

Users are welcome to generate out their own custom views along with the data sets to their liking.

# Next.js to Create-React-App

This section is about refactoring AppDrawer from Next.js to Create-React-App

This section will outline the details of how to transform the
[Material-UI Docs](https://material-ui.com/)
from Next-js to Create-React-App through a simple code
example.  

The example code for this section is inside the Github Repo
[mui-drawer](https://github.com/stormasm/mui-drawer).  All code
references not referring to the
actual Material-UI code base will
refer to the code inside **mui-drawer**.

## The AppDrawer Concept

Currently the Material-UI docs
[AppDrawer](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/AppDrawer.js)
are driven by
[Next-js Routing](https://nextjs.org/docs/#routing)
by using the Material-UI
[Link](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/Link.js) component.
In order to transform the
[Drawer](https://material-ui.com/demos/drawers/)
from Next-js to
[React-Router](https://reacttraining.com/react-router/core/guides/philosophy)
one must remove references to the Next-js Link inside the
[AppDrawerNavItem](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/AppDrawerNavItem.js)
and replace it with the React-Router
[Link](https://reacttraining.com/react-router/web/api/Link).

## The AppDrawer Details

If you take a look at the Material-UI docs and open the drawer
you will notice that all of the content inside the drawer is defined
by an an object called **pages** which is located inside the file
[withRoot](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/withRoot.js).

Inside this file are two other important functions.

* findActivePage
* getChildContext

These 3 pieces of code are ported over to their own file
in the sample code called
[Drawer](https://github.com/stormasm/mui-drawer/tree/master/fl7/src/Drawer.js)

This code is the basis for the refactor.

## The AppDrawer Code

[mui-drawer](https://github.com/stormasm/mui-drawer)
is a demo that allows you to navigate inside
the drawer and show a example delineating a **Chapter**
in a book and a **Section** inside of it...

Along with the **pages** object and the two functions
mentioned above this code is the other piece of logic
located inside the file
[Drawer](https://github.com/stormasm/mui-drawer/blob/master/fl7/src/Drawer.js)
that completes the refactor.


```js
const ShowChapterSection = ({ match }) => (
  <div>
    <h3>Chapter: {match.params.ch}</h3>
    <h4>Section: {match.params.sec}</h4>
  </div>
);
```

# Appendix

## Living Document

If you are interested in participating in this project feel
free to reach out to me.  I would welcome other developers
who are passionate
both about Material-UI and writing excellent
documentation that makes Material-UI more accessible to others
who are just getting started in Material-UI to those of us who
have some experience but want to have a well documented medium
scale application that shows best practices for software development
in the Material-UI world.

If you have a cool idea about a new view married with a JSON data
source or just want to fix my grammatical or spelling mistakes
you can find me on Gitter.

But for the most part, I hope you enjoy programming with Material-UI
as much as I do.

# About this document

This document is created using the awesome github repo
[spec-md](https://github.com/leebyron/spec-md)

## Links of Interest

For more examples of **spec-md** docs...

This is a clone of the spec-md repo with a personal document of mine
[spec17](https://stormasm.github.io/spec17/)

The initial motivator for spec-md
[graphql](http://facebook.github.io/graphql/draft/)

The actual spec on spec-md
[spec-md](http://leebyron.com/spec-md/)
