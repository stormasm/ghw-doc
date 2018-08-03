Material-UI Data Visualization Tutorial
---------------

This tutorial introduces some fundamental concepts that are helpful
to understand if you want to
learn how to visualize data using Material-UI.

# Introduction

I have been working with Material-UI now
since the release of
[v1.0.0-beta.3](https://github.com/mui-org/material-ui/releases/tag/v1.0.0-beta.3) on July 29, 2017. Over that time period I have worked on different projects
that cover a range of topics. From that experience and knowledge, I have come
up with a tutorial that hits the highlights of ideas people need
to know when visualizing JSON data coming from an
[API endpoint](https://stackoverflow.com/questions/2122604/what-is-an-endpoint).

The demos in the
[Material-UI documentation](https://material-ui.com/)
are an excellent starting
point to better understand how Material-UI works in the context
of one React component.

But if you want a better understanding of a slightly more complicated
real world Material-UI application this will hopefully serve your needs.

## Create React App

First and foremost I have decided to start out with all of the
tutorial repos using
[Create-React-App](https://github.com/facebook/create-react-app).

The Material-UI doc is an excellent example of a real world application,
however, the reason for using CRA is because if you look at the
[Material-UI doc](https://material-ui.com/) you will note that
it uses
[Next.js](https://nextjs.org/) at the core for driving its routing.

Initially, I thought ok, I want to build a Material-UI drawer system
that uses Create-React-App (CRA) instead of Next.js. At the time, I was relatively new to using Material-UI and thought "oh this would be easy".  Turns out it was more tricky than I initially thought and it ended up taking me
days to really come up with a solution I was happy with.

So saving people time on just this one simple concept seemed like something
that would be valuable to have documented.  From there, I started working on
a more sophisticated application that used
[Menus](https://material-ui.com/demos/menus/) instead of [Drawers](https://material-ui.com/demos/drawers/) and that added more knowledge to understand and think about. Fast forward about a year, and I am finally getting around
to writing all of these concepts up along with polishing up some nice
repos that elucidate the concepts.

All of the code repositories that this tutorial will reference uses
CRA which means they all come out of the box the same way with the
same cadence of commands.

```sh
npm install
npm start
```

# The set of Repositories discussed in this Tutorial

All of the repositories in this tutorial use the
[MIT License](https://en.wikipedia.org/wiki/MIT_License) and are referenced with the **Github Topic** [material-ui-tutorial](https://github.com/search?q=topic%3Amaterial-ui-tutorial&type=Repositories).  They include in order of complexity:

## The List

* [mui-md](https://github.com/stormasm/mui-md)
* [mui-drawer](https://github.com/stormasm/mui-drawer)
* [mui-menu](https://github.com/stormasm/mui-menu)
* [ghw-autosuggest](https://github.com/stormasm/ghw-autosuggest)
* [ghw-drawer](https://github.com/stormasm/ghw-drawer)
* [ghw-menu](https://github.com/stormasm/ghw-menu)

### mui-md

### mui-drawer

### mui-menu

### ghw-autosuggest

### ghw-drawer

### ghw-menu

# Next.js to Create-React-App

If you look at the Material-UI docs the main piece of Navigational software is the
[AppDrawer](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/AppDrawer.js)
which is derived from
[Drawer](https://material-ui.com/api/drawer/).

This section is about refactoring AppDrawer from Next.js to Create-React-App

This section will outline the details of how to transform the
[Material-UI Docs](https://material-ui.com/)
from Next.js to Create-React-App through a simple code
example.  

The example code for this section is in the github repository
[mui-drawer](https://github.com/stormasm/mui-drawer).  All code
references not referring to the
actual Material-UI
[docs code base](https://github.com/mui-org/material-ui/tree/master/docs#material-ui-docs)
will refer to the code inside **mui-drawer**.

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
[Drawer](https://github.com/stormasm/mui-drawer/tree/master/fl8/src/Drawer.js)

This code is the basis for the refactor.

## The AppDrawer Code

[mui-drawer](https://github.com/stormasm/mui-drawer)
is a demo that allows you to navigate inside
the drawer and show an example delineating a **Chapter**
in a book and a **Section** inside of the chapter.

Along with the **pages** object and the two functions
mentioned above this code is the other piece of logic
located inside the file
[Drawer](https://github.com/stormasm/mui-drawer/blob/master/fl8/src/Drawer.js)
that completes the refactor.


```js
const ShowChapterSection = ({ match }) => (
  <div>
    <h3>Chapter: {match.params.ch}</h3>
    <h4>Section: {match.params.sec}</h4>
  </div>
);
```

## More Details

[See this Readme](https://github.com/stormasm/mui-drawer/blob/master/README.md)
for more details on how to refactor the Material-UI code.

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

## Github World Views

The tutorial repository for Ghw is called **ghw-menu** and is
[located here on Github](https://github.com/stormasm/ghw-menu).

Github World (Ghw) is a set of views coming from the [Github API](https://developer.github.com/v4/).
Using this data visualization framework one can develop new views of data for repositories, users, statistics and anything else that can be derived from this data possibly in concert with other data sets.

The data sets for Ghw are abstracted away from the underlying visualization so that the only thing needed to display the data is a JSON data file.  Eventually, we will provide a live view of the data coming from the Github API; but for now with simplicity being urgent we decided to only require JSON data sets.  The generation of the JSON data sets is described in another part of this document.  For now, we are providing a test set of JSON data files to better understand the structure of the data along with the program which interprets the data and a sample set of views.

Users are welcome to generate out their own custom views along with the data sets to their liking.

### One repo many views

In the current incarnation of the demo there are four views.

 * view1: vertical scrollable gridlist of cards
 * view2: horizontal single line scrollable gridlist of cards
 * view3: table view with [react-autosuggest](https://github.com/moroshko/react-autosuggest)
 * view4: vertical scrollable gridlist of cards with no avatars

### One view many repos

Each view in the system is accessible via the Views menu.  The repo dropdown
allows one to switch between different Github repositories while staying on the same view.  If you select a different repo the same view will be persistent.

### High level data flow outline

In all Create-React-App (CRA) applications things kickoff inside **index.js**.  From there you wire up the
[Redux](https://redux.js.org/introduction)
state through a Provider interface inside **Root**.  Next up is the **MenuAppBar** which houses the Icons and Menus along with the
[React-Router](https://reacttraining.com/react-router/core/guides/philosophy)
Route definitions.  Finally, when you select a view inside the menu Views.

**ShowTheLocation** will select the proper **DataViewWrapper** given the repo name and view name as
[props](https://reactjs.org/docs/components-and-props.html#props-are-read-only).

### DataViewWrapper

This component has two important variables defined inside it.

```js
const repoMap = {
  repo1: "material-ui.json",
  repo2: "graphql-js.json",
  repo3: "html5-node-diagram.json",
  repo4: "nodejs-sandboxed-fs.json",
  repo5: "ivy.json"
};
```

The **repoMap** allows one to define their own repositories of
data that they are interested in observing, showing to others,
or using for your open source web site.  Say you have an open
source project on Github, and you want to show the world all of the committers
on the project.  Or provided you don't have too many stars, all of the
developers who starred or forked your repo.  This is the type of view
that might be interesting to you but with your own repositories data
instead of these sample data sets.

```js
const template =
  "https://raw.githubusercontent.com/stormasm/ghdata/master/data1/";
```

The **template** is the location of where your JSON data files live.
You can put them anywhere you want, provided you define the template variable.

#### Fetching Data

Now that you have things defined, its time to go out and
[fetch](https://developer.mozilla.org/en-US/docs/Web/API/Fetch_API)
the data.  For now we are fetching static JSON files from a specific
Github repo defined in the template above, but we could have just as easily fetched the data from the
[Github Api](https://developer.github.com/v4/).  
Or if you have other custom data views defined, your own GraphQL or
REST endpoint.

### DataView

DataView is a switch or set of if statements to grab the selected View from the View Menu in the AppBar.

The actual views themselves are styled any way you like them with
Material-UI's [styling solution](https://material-ui.com/customization/css-in-js/#material-ui-39-s-styling-solution).  

The **View** is the core of the application in that this is where you do your creative work.  Its your canvas so to speak, to create your data visualization. The rest of the framework is there for your use, you just have to be inventive
and come up with interesting views of your data.

The View takes in the prop **tileData** which is the data that was fetched from the API in the DataViewWrapper.  Then the tileData is mapped onto each component that you define in your View.

Any custom view that you define will take in tileData as a prop and then its up to you to build out your own styled component View.

### DataView Examples

#### AppBar

At the top of the hierarchy are ways to organize information or
websites.  All websites need to have an
[AppBar](https://material-ui.com/demos/app-bar/).  A nice example
of an AppBar in action is the
[Material-UI Home Page](https://material-ui.com/).
There you will
see the Icon button for drawer open and close.  In the repos
in this tutorial you
will see the same functionality.

#### Gridlists

The Gridlist is used to display a collection of Cards in both
a single horizontal line and with three cards per row.

#### Cards

The cards in this demo contain different data types about
each user that commits to a Github
repository including:
  * the user's name
  * the user's location
  * the user's username
  * a link to the avatar of the user

One can also grab data surrounding stars and forks as well.

#### React-Autosuggest

The Autosuggest is used to sort through many rows of a table and only display
particular users that are from a location that gets selected from the list
of user locations.  There may be more than one user displayed depending
upon how many users there are that reside in a particular location.

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

This document is created using the awesome github repository
[spec-md](https://github.com/leebyron/spec-md)

This document is located inside
[this github repository](https://github.com/stormasm/ghw-doc).

## Links of Interest

For more examples of **spec-md** docs...

The initial motivator for spec-md was
[graphql](http://facebook.github.io/graphql/draft/)

The actual spec on
[spec-md](http://leebyron.com/spec-md/)
