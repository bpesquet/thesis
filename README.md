# My thesis manuscript

> 🚧 Work in progress until Autumn 2026

## Development notes

Made with ❤️, 🥵 and the following tools:

- [latexindent.pl](https://github.com/cmhughes/latexindent.pl) for formatting the LaTeX code;
- [ChkTeX](https://www.nongnu.org/chktex/) for linting LaTeX files;
- [latexmk](https://mgeier.github.io/latexmk.html) for orchestrating the complex building process. Under the hood, it runs:
  - [pdflatex](https://www.tug.org/applications/pdftex/) for creating a PDF output from LaTeX files;
  - [biber](https://ctan.org/pkg/biber?lang=en) for generating the bibliography file needed during building.
- The [LaTeX Workshop](https://marketplace.visualstudio.com/items?itemName=James-Yu.latex-workshop) extension for using the previous tools in Visual Studio Code.

### Useful commands

```bash
# Build the PDF file in the gen/ subdirectory
latexmk -interaction=nonstopmode -pdf -outdir=gen/ main.tex

# Clean all generated files
rm -rf gen/
```

### Solving the "empty bibliography" error

```bash
# Get the cache location for biber in case it get stuck.
# See https://tex.stackexchange.com/a/579356
biber --cache

# Delete biber cache on your system

# Generate the .bbl file from the .bcf file
biber gen/main

# Build the PDF file (see above command): problem should be solved!
```

## License

[Creative Commons](LICENSE).

Copyright © 2025-present [Baptiste Pesquet](https://bpesquet.fr).
