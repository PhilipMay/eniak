reveal.js
===========

Installation
------------

- Install Node.js (LTS Version): ``nvm install --lts```
- Fix security problems: ``npm audit fix``
- Change to reveal.js directory
- Install via npm: ``npm install``
- run on port 8000: ``npm start``
- tun on other port: ``npm start -- --port=8001``

Using external Markdown file
----------------------------

Place this as a ``section`` block.

.. code-block:: html

   <section data-markdown="example.md" 
            data-separator="^\n\n\n" 
            data-separator-vertical="^\n\n">
   </section>
