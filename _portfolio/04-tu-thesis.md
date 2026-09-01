---
title: "tu_thesis — A LaTeX dissertation template for Temple University"
collection: portfolio
permalink: /portfolio/tu-thesis
excerpt: 'A generic, maintained LaTeX class for Temple University PhD dissertations and Masters theses, current with the graduate style guide and adaptable to other institutions.'
---

[Repository](https://github.com/jbrodovsky/tu_thesis)

Every university has a thesis template. Most are unmaintained, internally inconsistent, or so
specific to one author's department that adapting them costs more than starting over. Temple's
own mathematics department template is a good starting point but has drifted out of sync with
the current graduate handbook.

This is a clean, generic LaTeX class covering both the Ph.D. dissertation and Masters thesis
cases, parameterized by degree type, department, college, and university — which means it also
works for any institution following a similar style guide, and forks cleanly for those that
don't.

It handles committee members and their roles through `\advisor` and `\committeemember`, and
generates the title page, abstract, acknowledgements, table of contents, list of figures, list
of tables, and bibliography automatically.

Written while using it. Forking rather than copying is recommended, so upstream style-guide
fixes can be pulled in without touching the document itself.
