This set of code has some of the code needed to process markdown files 
to html using Javascript.

Command mdserver is an http server serving directory (recursively) with
markdown (.md) files. If can render automatically built index of those files
and render them as html pages.

Its main use-case is reading through directory with documentation written in
markdown format, i.e. local copy of Github wiki.

To access automatically generated index, request "/?index" path, as
http://localhost:8080/?index.

To create home page available at / either create index.html file or start
server with -rootindex flag to render automatically generated index.

If started with -github flag, it will render any absolute links to github
wikis like "https://github.com/user/project/wiki/Page" to relative ones like
"Page.md".

To apply custom styling provide css file with -css flag. By default, this
file is read on server start and then embedded into code of every page,
making them self-sufficient. If you instead wish to link stylesheet, provide
absolute root-related path to css file located under the same path as your
markdown files (-dir flag) and enable -csslink flag. This will link
stylesheet into head section of page with href being value of -css flag.

Note that table of contents generating javascript is a modified version of
code found at https://github.com/matthewkastor/html-table-of-contents which
is licensed under GNU GENERAL PUBLIC LICENSE Version 3.
