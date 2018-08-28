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
tutorial demos using
[Create-React-App](https://github.com/facebook/create-react-app).

The Material-UI doc is an excellent example of a real world application,
however, the reason for using CRA is because if you look at the
[Material-UI doc](https://material-ui.com/) you will note that
it uses
[Next.js](https://nextjs.org/) at the core for driving its routing.

Initially, I thought ok, I want to build a Material-UI drawer system
that uses **Create React App** (CRA) instead of Next.js. At the time, I was relatively new to using Material-UI and thought "oh this would be easy".  Turns out it was more tricky than I initially thought and it ended up taking me
days to really come up with a solution I was happy with.

So saving people time on just this one simple concept seemed like something
that would be valuable to have documented.  From there, I started working on
a more sophisticated application that used
[Menus](https://material-ui.com/demos/menus/) instead of [Drawers](https://material-ui.com/demos/drawers/) and that added more knowledge to understand and think about. Fast forward about a year, and I am finally getting around
to writing all of these concepts up along with polishing up some nice
demos that elucidate the concepts.

All of the demos that this tutorial will reference uses
CRA which means they all come out of the box the same way with the
same cadence of commands.

```sh
npm install
npm start
```

# The List

All of the repositories in this tutorial use the
[MIT License](https://en.wikipedia.org/wiki/MIT_License) and are referenced with the

**[Github Topic:  material-ui-tutorial](https://github.com/topics/material-ui-tutorial)**

They include in order of complexity from the most simple to slightly more sophisticated code:

## Drawers

* [mui-drawer](https://stormasm.github.io/mui-drawer/)
* [ghw-drawer](https://muitool.github.io/ghw-drawer/)

## Menus

* [mui-menu](https://stormasm.github.io/mui-menu/)
* [ghw-menu](https://muitool.github.io/ghw-menu/)

# The Tutorial Repositories
