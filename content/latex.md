# Writing reports with LaTeX

Text written by Arthur Loison.

In the framework of APM51051EP, you are asked to write reports for the various practical sessions, and the simplest way to write them is to use scientific text editors such as $\LaTeX$. This makes it possible to write clear documents and, for those who have never used it, it will be an opportunity to acquire and develop a tool that is essential for what comes next (internships, theses, research, reports, ...). Even though its use is not mandatory for APM51051EP, using $\LaTeX$ is strongly suggested. You will obviously not be penalized for a lack of knowledge of $\LaTeX$.


## What is $\LaTeX$?

$\LaTeX$ is a text editor suited to the writing of scientific documents (papers, books, reports) which makes it easier, among other things, to write mathematical formulas and to lay out a document.

The principle is to write/code a document using the $\LaTeX$ conventions: tags and environments such as `section`, `equation`, `align`, `figure`, `table`, ...


## Where to start?

The simplest way to use $\LaTeX$ is to use free software such as Overleaf (online, through a web browser) or to download an editor (TeXStudio or another one).


### Overleaf

Go to *Overleaf.com*, log in or create an account. In the left bar, select "New project", then "Example project" in the drop-down menu.

A page opens with, on the left, the $\LaTeX$ code in a ".tex" file and, on the right, the PDF rendering.

All that is left to do is to compile the code to obtain the corresponding PDF.


### Other editors

Download and install an editor on your computer, start a new document in a folder of your choice by selecting a template of your choice of type `article`, `report` or another one. In the same way, the code and the PDF rendering are shown in two different windows and all that is left to do is to compile the code to obtain the PDF file (which you will find in the folder you are working in).


## First steps with $\LaTeX$

Plenty of very complete books (I can send you one by email if you wish) or free tutorials are available on the internet to discover (for example on the Overleaf website), learn and improve in $\LaTeX$. The essential point is to start from a fairly simple basis such as the one described in the Overleaf example project and to reuse the pieces of code already written: the default layout of $\LaTeX$ is enough for a clear report. The subtleties of $\LaTeX$ layout can turn out to be difficult to master and are reserved for experienced users. Nevertheless, I present in this document the basic tools that will be necessary for your report, together with a document listing the useful shortcuts.

<!-- #region -->
### Packages

First of all, $\LaTeX$ is a language enriched by many packages which provide a lot of interesting features (bibliography, languages, references, insertion of images, additional mathematical symbols, layout, ...) and are inserted at the beginning of the document through tags of the form: 

```latex
\usepackage{PackageName},
```

Whether on Overleaf or in other editors, these packages are then downloaded when the code is compiled.

I therefore advise you to insert the following packages: `graphicx` (to insert images), `amsmath` and `amssymb` (many useful mathematical symbols). If a command you want to use does not work, make sure you have declared the package in the preamble.
<!-- #endregion -->

<!-- #region -->
### Text

Text is organized through the tags 

```latex
\section{Title of the section}
```

as well as 

```latex 
\subsection{Title of the subsection}
```

and 

```latex
\subsubsection{Title of the subsubsection}  
```

for the organization into parts, subparts and subsubparts.

The plain text itself is written directly between these tags.
<!-- #endregion -->

<!-- #region -->
### Mathematical formulas

To write mathematical symbols, there are several methods:

1. A formula within the text, using `$Your formula$`, e.g.: `$\int_0^1 x^2 dx = \frac{1}{3}$` gives $\int_0^1 x^2 dx = \frac{1}{3}$
        
2. On a new line and centered, through: `$$\int_0^1 x^2 dx= \frac{1}{3}$$` which gives 

$$\int_0^1 x^2 dx= \frac{1}{3}$$

3. Same as the previous point but to be preferred, through 
```latex
\begin{equation*} 
\int_0^1 x^2 dx= \frac{1}{3}
\end{equation*}
```
which gives 
\begin{equation*} 
\int_0^1 x^2 dx= \frac{1}{3}
\end{equation*}

4. A sequence of aligned equations with `align`, e.g.: 
```latex
\begin{align*}
\int_0^1 x^2 dx &= \frac{1^3}{3}-\frac{0^3}{3}\\
                &= \frac{1}{3}.
\end{align*}
```

which gives:

\begin{align*}
\int_0^1 x^2 dx &= \frac{1^3}{3}-\frac{0^3}{3}\\
                &= \frac{1}{3}.
\end{align*}

The list of mathematical symbols in $\LaTeX$ is available just about everywhere on the internet.
<!-- #endregion -->

<!-- #region -->
### Images

To insert images, in particular curves exported from Jupyter notebooks or elsewhere, I advise you to open a `figure` environment through:
```latex
\begin{figure} 
\includegraphics[width=width]{filename}
\caption{Titleofthefigure}
\end{figure} 
```
where `filename` is the name of the file to be added and `Titleofthefigure` the content of the caption.

You can leave to $\LaTeX$ the choice of where the image is displayed, or you can force it to display the image between the paragraphs of text where you declared the `figure` environment, through the option `h!`, i.e. `\begin{figure}[h!]`.
<!-- #endregion -->

<!-- #region -->
### Tables

To insert a table, I advise you to use a `table` environment and a `tabular` sub-environment. The columns of the table are declared through letters, as in `$\begin\{figure\}{c|lrc}`, where we have for instance a table with 4 columns, the first one being centered and separated from the others by a vertical line, then three columns aligned to the left `l`, to the right `r` and centered `c`.

A row of the table is declared cell by cell, cells being separated by `&` and the end of the row by `\\`. 

Example of a table:
```latex
\begin{table}[h!]
        \centering
        \begin{tabular}{c|lrc}
                1 & 2 & 3 & 4\\
                \hline
                5 & 6 & 7 & 8
        \end{tabular}
        \caption{An example of a table.}
        \label{tab:exemple}
\end{table}
```

Horizontal lines are declared through `hline`.


<!-- #endregion -->

### References

References make it possible to automatically link the number of an image, of a table or of an equation, even after rearranging the order in which they are declared, or deleting or adding a new element. This allows one to make references without worrying about checking that the numbers of the figures match.

To do this, it is enough to label the environments through the tag `\label{yourLabel}` and to refer to them in the text through `\ref{yourLabel}`. In order to find your way among the labels, I advise you to use short labels or to start them with `fig:...`, `tab:...`, `eq:...` so as to recognize the type of element being referred to.


## $\LaTeX$ Cheat Sheet

You will find a two-page summary of the main $LaTeX$ commands [here](https://wch.github.io/latexsheet/latexsheet.pdf).


### A final word

$\LaTeX$ is a very widely used and very well documented language, for which all the answers can be found on the internet, from the most basic to the most technical questions. Even if it takes time at the beginning, you will quickly find your bearings and the effort required will become smaller and smaller.
