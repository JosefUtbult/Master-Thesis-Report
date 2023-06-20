# LTU Report Template

An LTU report template based on the [LTU SRT Thesis Template](https://www.overleaf.com/latex/templates/ltu-srt-thesis-template/jnqrnxdqxrvx)

Adding the option to work with a document in dark theme. A custom TODO implementation is also a part of the template, allowing you to write TODOs for your report.

The following are examples of the [light](https://github.com/JosefUtbult/LTU-Report-Template/blob/main/example_lighttheme.pdf?raw=true) and [dark](https://github.com/JosefUtbult/LTU-Report-Template/blob/main/example_darktheme.pdf?raw=true) themes.

## Setup
Begin with installing _TexLive full_.
```shell
sudo apt-get install texlive-full
```

After that, make sure you can run `pdflatex`
```shell
pdflatex -v
```

Also, make sure you can run `bibtex`
```shell
bibtex -v
```

## Editing
Your document will begin in the file `report.tex`. In there you have definitions for title, author and right/left heading. Change all these out for your own.

This document uses a file structure for every section and subsection. I recommend using this style, as it is much easier to navigate through longer documents. Use the `input` macro in the same way the two example sections are implemented, to include your different files into the report.

This theme uses the IEEEtran bibliography style to apply the references from the file `refs.bib`. You can find a guide on how to apply this at [Overleaf](https://www.overleaf.com/learn/latex/Bibliography_management_with_bibtex)

You have two definitions in the beginning of the file. With `DARKMODE` enabled, the color scheme of the document changes to dark mode. 

With `HIGHRES` enabled, a higher resolution LTU logo is used. This takes a second longer to compile and should therefore be used when submitting the report, and not when writing it.

You can enable/disable these modes by commenting and uncommenting the lines.

```tex
\def\DARKMODE{}

\def\HIGHRES{}
```

You can also use the tag `\todo` to get a list of TODOs for your document. The tag `\listoftodos` can then be used to get the list as an index.

## Building
The script `build` can be used for building. It will run `pdflatex` in a directory called `out`, giving you a cleaner `src` directory. It will also run `bibtex` for referencing.

Make sure the script is executable

```shell
chmod +x build
```

And try running it

```shell
./build
```

The resulting PDF should be located in `out/report.pdf`.
