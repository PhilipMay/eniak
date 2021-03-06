# Sphinx
- Sphinx: <https://www.sphinx-doc.org/>
- Sphinx GitHub: <https://github.com/sphinx-doc/sphinx/>
- Sphinx Config:
  <https://www.sphinx-doc.org/en/master/usage/configuration.html>
- Read the Docs Sphinx Theme:
  <https://github.com/readthedocs/sphinx_rtd_theme>
- Recommonmark: <https://recommonmark.readthedocs.io/>

## Syntax
- reStructuredText Primer:
  <https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>
- TOC:
  <https://www.sphinx-doc.org/en/master/usage/restructuredtext/directives.html#table-of-contents>
- [Cross-referencing Python objects](https://www.sphinx-doc.org/en/master/usage/restructuredtext/domains.html#python-roles)
- Markdown: <https://commonmark.org/help/>

## Convert reStructuredText to Markdown
``` bash
pandoc -s -t commonmark -o <target>.md <source>.rst
```
