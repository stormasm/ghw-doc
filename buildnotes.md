
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

At the very end of the process you must do this by hand.

Go to the directory on your disk for **mui-tutorial**
and add this line of HTML into the file *index.html*.

```
<link rel="shortcut icon" href="/mui-tutorial/favicon.ico">
```

Eventually we will automate this process using
[Print Options](https://github.com/leebyron/spec-md/blob/master/spec/Usage.md#print-options)

[For more details](https://github.com/leebyron/spec-md/blob/master/spec/Usage.md)

Contributing to **[Spec-Markdown](https://github.com/leebyron/spec-md/blob/master/CONTRIBUTING.md)**
