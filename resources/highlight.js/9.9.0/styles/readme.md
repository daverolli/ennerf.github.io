# Adding MATLAB-style syntax highlighting to Asciidoc

The highlight.js version bundled by default does not include support for MATLAB. Additionally, the standard styles don't work well for highlighting MATLAB syntax. The code below can be used to to remove the default highlighter and to add a stylesheet that results in MATLAB-like syntax highlighting.

Deactivate source highlighter by specifying invalid string

```asciidoc
:source-highlighter: none
```

Pass-through highlight.js styles and scripts

```html
++++
<link rel="stylesheet" href="https://cdn.rawgit.com/ennerf/ennerf.github.io/master/resources/highlight.js/9.9.0/styles/matlab.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.9.0/highlight.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.9.0/languages/matlab.min.js"></script>
<script>hljs.initHighlightingOnLoad()</script>
++++
```

Github serves content as text/plain, but we can use https://rawgit.com/ for referencing the css. See http://stackoverflow.com/questions/7780550/referencing-a-css-file-in-github-repo-as-stylesheet-in-a-html-file for more info.

## Overriding base stylesheet

Alternatively, the -override stylesheet can be combined with any standard style to get MATLAB-like syntax highlighting only for MATLAB code blocks.

```html
++++
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.9.0/styles/github.min.css">
<link rel="stylesheet" href="https://cdn.rawgit.com/ennerf/ennerf.github.io/master/resources/highlight.js/9.9.0/styles/matlab-override.css">
<script src="https://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.9.0/highlight.min.js"></script>
<script src="http://cdnjs.cloudflare.com/ajax/libs/highlight.js/9.9.0/languages/matlab.min.js"></script>
<script>hljs.initHighlightingOnLoad()</script>
++++
```


