# acl.bst
## An ACL BibTeX style that supports hyperlinks

This is a minor extension of the original `acl.bst`, which adds support for a `url` field in your BibTeX file.
The `url` field is optional, and if it exists for a given entry, then the title of the article will be hyperlinked.
If the URL contains a `%` character, insert a backslash before it.

## Example
For example, in your BibTeX file:

    @inproceedings{sjobergh-araki2008,
     title     = {A Complete and Modestly Funny System for Generating and Performing {J}apanese Stand-Up Comedy},
     author    = {Sj\"{o}bergh, Jonas  and  Araki, Kenji},
     booktitle = {Coling 2008: Companion volume: Posters},
     year      = {2008},
     address   = {Manchester, England},
     pages     = {111--114},
     url       = {http://www.aclweb.org/anthology/C08-2028}
    }

In the references section of the PDF, the title will be hyperlinked to the actual article, as:

Jonas Sjöbergh and Kenji Araki. 2008. [A Complete and Modestly Funny System for Generating and Performing Japanese Stand-Up Comedy](http://www.aclweb.org/anthology/C08-2028). In Coling 2008: Companion volume: Posters, pages 111–114, Manchester, England.

## Hyperref and Navigator
You can use either [Hyperref] or [Navigator] to allow hyperlinks in your LaTeX document.

### [Hyperref]
Hyperref's default colors for linked text are crazy neon colors, so if you want a less-distracting coloring scheme, add the following to your preamble:

    \usepackage[hyperref,table,x11names]{xcolor}
    \definecolor{linkblue}{rgb}{0,0,0.20}
    \usepackage{hyperref}
    \hypersetup{pdfborder=0 0 0, colorlinks=true, citecolor=linkblue, linkcolor=linkblue, urlcolor=linkblue}

### [Navigator]
Navigator's commands have different names, so add the following lines to your preamble for compatibility:

    \usepackage[hyperref,table,x11names]{xcolor}
    \definecolor{linkblue}{rgb}{0,0,0.20}
	\usepackage{navigator}
	\providecommand{\href}[2]{\urllink[border = 0]{#1}{{\color{linkblue}{#2}}}}


[Hyperref]: https://en.wikibooks.org/wiki/LaTeX/Hyperlinks
[Navigator]: http://ctan.org/pkg/navigator
