

### Table of Contents
**[Intro](#intro)**<br>
**[AI types](#ai-types)**<br>
**[Functions](#functions)**<br>
**[Tells](#tells)**<br>
**[Behaviour](#behaviour)**<br>
**[Building the Extension Bundles](#building-the-extension-bundles)**<br>
**[Next Steps, Credits, Feedback, License](#next-steps)**<br>

## Intro


## AI types



## Functions

See the [Troubleshooting wiki page](https://github.com/adam-p/markdown-here/wiki/Troubleshooting).


## Tells

See the [Compatibility wiki page](https://github.com/adam-p/markdown-here/wiki/Compatibility).


## Behaviour

* *Markdown Here* uses [Github Flavored Markdown](http://github.github.com/github-flavored-markdown/), with the limitation that GFM special links are not supported ([issue #11](https://github.com/adam-p/markdown-here/issues/11)); nor will they be, as MDH is not Github-specific.

* Available languages for syntax highlighting (and the way they should be written in the fenced code block) can be seen on the [highlight.js demo page](http://softwaremaniacs.org/media/soft/highlight/test.html).

* Images embedded inline in your Markdown will be retained when you "Markdown Toggle". Gmail allows you to put images inline in your email -- this can be much easier than referencing an external image.

* Email signatures are automatically excluded from conversion. Specifically, anything after the semi-standard `'-- '` (note the trailing space) is left alone.
  * Note that Hotmail and Yahoo do *not* automatically add the `'-- '` to signatures, so you have to add it yourself.

* The "Markdown Toggle" menu item shows up for more element types than it can correctly render. This is intended to help people realize that they're not using a rich editor. Otherwise they just don't see the menu item and don't know why.

* Styling:
  * The use of browser-specific styles (-moz-, -webkit-) should be avoided. If used, they may not render correctly for people reading the email in a different browser from the one where the email was sent.
  * The use of state-dependent styles (like `a:hover`) don't work because they don't match at the time the styles are made explicit. (In email, styles must be explicitly applied to all elements -- stylesheets get stripped.)

* For more tweaky features, visit the [Tips and Tricks](https://github.com/adam-p/markdown-here/wiki/Tips-and-Tricks) section.

## Building the Extension Bundles

"Building" is really just zipping. Create all archives relative to the `src` directory.

Before zipping, delete the `src/common/test` directory. This will prevent the autotests from ending up in the release.

An important preparatory step is to remove any system-generated hidden files that shouldn't be included in the release file (like Windows' `desktop.ini` and OS X's `.DS_Store`, etc.). This shell command will delete those unwanted files:

```
find . -name "desktop.ini" -or -name ".*" -and -not -name "." -and -not -name ".git*" -print0 | xargs -0 rm -rf
```

### Chrome and Opera extension

Create a file with a `.zip` extension containing these files and directories:

```
manifest.json
common/
chrome/
```

### Firefox/Thunderbird extension

Create a file with a `.xpi` extension containing these files and directories:

```
chrome.manifest
install.rdf
common/
firefox/
```

### Safari extension

The browser-specific code is located in the [`markdown-here-safari`](https://github.com/adam-p/markdown-here-safari) project.

Use the Safari Extension Builder.

## Next Steps

See the [issues list](https://github.com/adam-p/markdown-here/issues) and the [Notes Wiki](https://github.com/adam-p/markdown-here/wiki/Development-Notes). All ideas, bugs, plans, complaints, and dreams will end up in one of those two places.

Feel free to create a feature request issue if what you want isn't already there. If you'd prefer a less formal approach to floating an idea, post to the ["markdown-here" Google Group](https://groups.google.com/forum/?fromgroups=#!forum/markdown-here).

It also takes a fair bit of work to stay up-to-date with the latest changes in all the applications and web sites where Markdown Here works.

## Credits

*Markdown Here* was coded on the shoulders of giants.

* Markdown-to-HTML: [chjj / marked](https://github.com/chjj/marked)
* Syntax highlighting: [isagalaev / highlight.js](https://github.com/isagalaev/highlight.js)
* HTML-to-text: [mtrimpe / jsHtmlToText](https://github.com/mtrimpe/jsHtmlToText)

## Feedback

All bugs, feature requests, pull requests, feedback, etc., are welcome. [Create an issue](https://github.com/adam-p/markdown-here/issues). Or [post to the "markdown-here" Google Group](https://groups.google.com/forum/?fromgroups=#!forum/markdown-here).

## License

### Code

MIT License: http://adampritchard.mit-license.org/ or see [the `LICENSE` file](https://github.com/adam-p/markdown-here/blob/master/LICENSE).

### Logo

Copyright 2015, [Austin Anderson](http://protractor.ninja/). Licensed to Markdown Here under the [MDH contributor license agreement](https://github.com/adam-p/markdown-here/blob/master/CLA-individual.md).

### Other images

[Creative Commons Attribution 3.0 Unported (CC BY 3.0) License](http://creativecommons.org/licenses/by/3.0/)

---

![Dos Equis man says](https://raw.github.com/adam-p/markdown-here/master/store-assets/dos-equis-MDH.jpg)
