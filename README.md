# APA Annotated Bibliography

This is a simple LaTeX Template for APA annotated bibliography. Simply add your 
references to the `refs.bib` and add them in sequentially using the custom 
bibentry environment.

## Title page

This template provides a simple command that automatically formats
the title page. In the `main.tex` file, set the author, title, subtitle, 
instructor, course title, and department as follows.

```
\def\maintitle{Title}
\def\subtitle{Subtitle}
\def\mainauthor{John Doe}
\def\instructor{Jane Doe}
\def\course{Course Title}
\def\school{Department Name}
```

Then call the `\tlpage{}` command in `main.tex` after`\begin{document}`.

## Adding a reference

References must be added to the `refs.bib' and then referenced in the `main.tex`
file. Take the following example of a journal article.

```
@article{doe:2024,
    title="Some Long Important Title",
    author="Jane Doe",
    year="2024",
    journal="Extremely Fancy Journal"
    volume="1",
    number="1",
}
```
To reference `doe:2024` add it to the `main.tex` file using the `bibentry` 
environment.
```
\begin{bibentry}{doe:2024}
    Annotation goes here
\end{bibentry}
```

To edit the `bibentry` environment, you can find the source in the `preamble.tex`
file.

## Building

This template uses the `biber` engine to format citations. First, you must build
the `main.tex` file using `pdflatex`, then run `biber` on the main file, and
finally run `pdflatex` again. You might have to run `pdflatex` multiple times.

```
$ pdflatex main.tex && biber main && pdflatex main.tex
```
