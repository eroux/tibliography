# Tibliography

The goal of this repository is to provide a `.bib` file containing resources about Tibetan Natural Language Processing. It also contains a [html version](http://eroux.github.io/tibliography/) (in the [gh-pages](https://github.com/eroux/tibliography/tree/gh-pages) branch) showing all the references, so it is possible for other pages to cite a source with a link to the page.

## Using in LaTeX

The current format is very standard and should work in most contexts. LaTeX needs some extra care though, because a language switch is needed when inputting Tibetan or Chinese characters. You thus need to have them inserted them in the `.bib` file you will use. One quite simple way to do so is with the following command:

```
cat tibliography.bib | perl -CS -p -e 's/(\p{Tibetan}+)/\\tibbib\{\1\}/g' | perl -CS -p -e 's/(\p{Han}+)/\\chinbib\{\1\}/g' > tibliographyltx.bib
```

that will create a `tibliographyltx.bib` containing some `\tibbib` and `\chinbib` commands that you'll have to define in your document. The [articles of tibetan-collation](https://github.com/eroux/tibetan-collation/tree/master/articles) can be a simple source of inspiration.

## HTML version

### Compiling the html file

To compile the html file, open the bib file with [JabRef](http://jabref.sourceforge.net/) and export with the format `HTML list`.

### Using the html version

To cite a reference in markdown, use the following example:

    [\[*Tournadre, 2013*\]](http://eroux.github.io/tibliography/#TournadreTibetic)

result: [*\[Tournadre, 2013\]*](http://eroux.github.io/tibliography/#TournadreTibetic)
