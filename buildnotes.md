
This code is a fork of
[spec-md](https://github.com/leebyron/spec-md)

Besides this repository
[mui-tutorial-src](https://github.com/stormasm/mui-tutorial-src)
you will also need to grab
**[mui-tutorial](https://github.com/stormasm/mui-tutorial)**
as the **deployme** script copies files into here.

To build the doc simply run the following commands

* yarn
* ./scripts/buildme
* npm run build [the first time]
*
* Then subsequent builds you can do...
*
* npm run watch [if you want hot reloading only]
* npm run start

You must **check and make sure** that the changes you made
actually work and generate out the proper Spec Markdown
**index.html** file.  You do this by running one of the above
*npm* commands.

If there is a problem then spec-md will tell you what line
number the error occured at.

##### At the very end of the build process
##### You must do this by hand.

Add this line of HTML into the file **index.html**.

```
<link rel="shortcut icon" href="/mui-tutorial/favicon.ico">
```

In this location in the <head> tag at the very top of the file...

```
<!DOCTYPE html>
<!-- Built with spec-md -->
<html><head><meta charset="utf-8"><title>Material-UI Data Visualization Tutorial</title>

<link rel="shortcut icon" href="/mui-tutorial/favicon.ico">

<style>body {
  color: #333333;
  font: 13pt/18pt Cambria, "Palatino Linotype", Palatino, "Liberation Serif", serif;
  margin: 6rem auto 3rem;
  max-width: 780px;
}
```

Eventually we will automate this process using
[Print Options](https://github.com/leebyron/spec-md/blob/master/spec/Usage.md#print-options)

[For more details](https://github.com/leebyron/spec-md/blob/master/spec/Usage.md)

Contributing to **[Spec-Markdown](https://github.com/leebyron/spec-md/blob/master/CONTRIBUTING.md)**
