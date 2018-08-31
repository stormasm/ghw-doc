
# Appendix

## Learning React

If you are coming to React for the first time and are in the learning process of understanding it:

**Be Patient !**...

Once you get React it makes total sense and is clear and easy to understand; but the road to get there can take some people a while to grok. If you are fluent in more than one language; and you learned the second language as an adult you know how hard it is to get a concept.  Once you got it, you forget how hard it was to get there.  Computer programming is the same idea.  It takes years to truly be good at writing software; but once you are there it is just second nature.  React is not to this level of complexity... But it does take some people a period of time.

The React model is truly the next evolutionary step in user interface design.  When you think about computer design and how one transistor can be scaled up to have
**[billions of transistors in one integrated circuit](https://en.wikipedia.org/wiki/Transistor_count)** and then
you think about Facebook and the thousands of components that exist inside
its total application you can begin to understand the power of React.

And that is also where Material-UI starts to shine.  The power of Material-UI and in general **CSS in JS** is not apparent at first look.  But as you start to develop large scale applications and then you realize that **WOW** I can just take this component that I used somewhere else; and drop it right down in my completely other unrelated application is when the light goes on.  Especially because all of the CSS comes along with it.  You no longer need to mess around with pulling CSS out of a much larger CSS file and then merge it into your new application's CSS file.

## Generating out Github Worlds JSON data files

For more details on how to generate out JSON data from the
**[Github GraphQL API](https://developer.github.com/v4/)**
check out the README for
**[Graphql Redis Github](https://github.com/stormasm/graphql-redis-github/blob/master/README.md)**.

## Markdown Processing in Material-UI

**[mui-md](https://github.com/stormasm/mui-md)**
is still in beta code but depicts using Markdown
in your applications.

This demo shows how to integrate
[Markdown](https://www.markdownguide.org/getting-started) files into your Material-UI application.  Besides using
**[Typography](https://material-ui.com/style/typography/)**, Markdown is an excellent and simpler way to display your text without having to worry about the formatting issues associated with Typography.

**[MarkdownDocs](https://github.com/mui-org/material-ui/blob/master/docs/src/modules/components/MarkdownDocs.js)** is used through out all of the Material-UI demos.  There is not an example of how to use it standalone and so I have come up with a nice simple demo that uses the MarkdownDocs code slightly modified.

**[MarkdownElement](https://github.com/mui-org/material-ui/tree/master/packages/material-ui-docs/src/MarkdownElement)** is the core software behind MarkdownDocs.  MarkdownElement is a part of the Material-UI distribution and lives inside the docs package.  Therefore this demo shows how to create a wrapper around MarkdownElement which is essentially the core mission of MarkdownDocs.

Besides the above two pieces of code another part of the demo shows how to use
**[React Markdown](https://github.com/rexxars/react-markdown)**.

All of the Markdown files that are displayed in this demo are loaded remotely from some server that gets defined in the demo code. It gives one the ability to have a static Markdown File Server for any Markdown files you want to display in your application.

## Links of Interest

 * [Material-UI v1 is out blog post](https://medium.com/material-ui/material-ui-v1-is-out-e73ce13463eb)

 * [A Journey Towards Better Style](https://oliviertassinari.github.io/a-journey-toward-better-style/#/0?_k=hwphr3)
and the **[github repo](https://github.com/oliviertassinari/a-journey-toward-better-style)**

* [All You Need To Know About CSS-in-JS](https://hackernoon.com/all-you-need-to-know-about-css-in-js-984a72d48ebc)

# About this document

This document is created using the awesome github repository
**[spec-md](https://github.com/leebyron/spec-md)**

This document is located inside
**[this github repository](https://github.com/stormasm/mui-tutorial-src)**.

## Editing this document and pull requests

Please read this section carefully and understand it prior
to issuing a pull request on the tutorial.

This document has several pieces which all come together to form
the tutorial.  If you want to understand how the tutorial gets built simply **[read the bash script.](https://github.com/stormasm/mui-tutorial-src/blob/master/scripts/buildme)**

So there are three main pieces to the tutorial and they are:

* [ghw-part1](https://github.com/stormasm/mui-tutorial-src/blob/master/ghw-part1.md)
* [ghw-part2](https://github.com/stormasm/mui-tutorial-src/blob/master/ghw-part2.md) **which gets built by the script**
* [ghw-part3](https://github.com/stormasm/mui-tutorial-src/blob/master/ghw-part3.md)

### ghw-part2 in more detail...

The file, **ghw-part2** gets built by the script and is a concatenation
of all of the *README.md* files in all of the tutorial demos in a particular order that flows and reads like a book or tutorial.  So it is important if you are editing any of these files that you keep that in mind.  **Do Not** edit the files in the repository
[mui-tutorial](https://github.com/stormasm/mui-tutorial), but rather edit the individual README.md files in the respective demos or

* ghw-part1
* ghw-part3

For more details on what you need to do to build this tutorial
[read this document](https://github.com/stormasm/mui-tutorial-src/blob/master/buildnotes.md)
as well.

## Examples of spec-md docs...

The initial motivator for spec-md was
**[graphql](http://facebook.github.io/graphql/draft/)**

The actual
**[spec on spec-md](http://leebyron.com/spec-md/)**

## Living Document

If you are interested in participating in this project feel
free to
**[reach out to me](https://github.com/stormasm)**. I would welcome other developers
who are passionate
both about Material-UI and writing excellent
documentation. Making Material-UI more accessible to others
who are just getting started; and to those who
are experienced developers but want to have a well documented small
scale application that shows best practices for software development
in the Material-UI world.

If you have a cool idea about a new view married with the
[Github Github Graphql API](https://developer.github.com/v4/)
or just want to fix grammatical or spelling mistakes
in this tutorial you can find me on Gitter.

But for the most part, I hope you enjoy programming with Material-UI
as much as I do.
