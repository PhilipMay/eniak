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

Place this as a ``section`` block. This needs reveal.js to run in a Node.js server. A local file is not sufficient.

.. code-block:: html

   <section data-markdown="example.md"
            data-separator="^\n\n\n"
            data-separator-vertical="^\n\n"
            data-separator-notes="^Note:"
            data-charset="iso-8859-15">
       <!--
           Note that Windows uses `\r\n` instead of `\n` as its linefeed character.
           For a regex that supports all operating systems, use `\r?\n` instead of `\n`.
       -->
   </section>

Keyboard Shortcuts
-------------------

- <kbd>N</kbd>, <kbd>SPACE</kbd>:	Next slide
- <kbd>P</kbd>: Previous slide
- <kbd>←</kbd>, <kbd>H</kbd>: Navigate left
- <kbd>→</kbd>, <kbd>L</kbd>: Navigate right
- <kbd>↑</kbd>, <kbd>K</kbd>: Navigate up
- <kbd>↓</kbd>, <kbd>J</kbd>: Navigate down
- <kbd>Home</kbd>: First slide
- <kbd>End</kbd>: Last slide
- <kbd>B</kbd>, <kbd>.</kbd>: Pause (Blackout)
- <kbd>F</kbd>: Fullscreen
- <kbd>ESC</kbd>, <kbd>O</kbd>: Slide overview / Escape from full-screen
- <kbd>S</kbd>: Speaker notes view
- <kbd>?</kbd>: Show keyboard shortcuts
- <kbd>alt</kbd> + click: Zoom in. Repeat to zoom back out.
