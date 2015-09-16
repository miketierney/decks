# Michael Tierney's Presentation Decks

This repository contains the source for various presentations that
I've given or plan to give at some point. They are built using the
[quick-deck](https://github.com/divshot/quick-deck) precompiler
for [Reveal.js](http://lab.hakim.se/reveal-js/).

## Getting Started

Yu'll need to install [broccoli](https://github.com/joliss/broccoli)
as well as the bower and NPM modules used by Quick Deck:

    npm install -g broccoli-cli && npm install && bower install

Next you'll want to get the Broccoli server up and running so you can
preview your work:

    broccoli serve

Now you're ready to make your decks, and they'll be compiled automatically!

## Making a Deck

To create a deck, all you need to do is make a new markdown file in the
`decks` directory. Here's an example deck syntax:

```markdown
# Title Slide
## Author Name

===

# Sections Use "="
## To Divide

---

# Subsections Use "-"
## To Divide
```

## Publishing Your Decks

If you want to publish your deck to a static web host you will need to build a
distribution. For convenience, you can do so into the `dist` directory
like so:

    npm run build

If you'd like to use a different directory, just use `broccoli build`:

    broccoli build [DEST_DIR]

Unfortunately at the moment Broccoli doesn't have a "watch" command, so
you'll have to manually trigger each build for publication.

## Roadmap

Right now this is all very, very basic. Soon you'll hopefully be able to:

1. Configure themes (or make your own)
2. Add classes or other HTML configuration to individual slides
3. Add plugins and other Reveal functionality
4. ???

## License

All of my decks are licensed under a **Creative Commons
Attribution-ShareAlike 4.0 License**. More details by clicking the
button below:

<a rel="license" href="http://creativecommons.org/licenses/by-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-sa/4.0/88x31.png" /></a>
