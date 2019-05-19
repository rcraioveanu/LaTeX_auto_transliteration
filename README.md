# Automatic transliteration in XeLaTeX

This repository provides a set of mappings of ASCII characters to non-Roman writing systems, allowing the user to type in the Roman alphabet and have the compiled output rendered in another writing system. This may be useful to reduce errors in writing systems the user is not very familiar with, or simply as a workaround for poor editor or OS rendering of the writing system.

Note that this transliteration requires use of the `fontspec` package, and therefore requires use of XeLaTeX or LuaLaTeX.

The transliteration is provided by the `.map` file, which needs to be in the same folder as the `.tex` file (or otherwise findable in the TeX directory structure). The transliteration is specified with `Mapping=` in the optional arguments of the `\newfontfamily` command:

```latex
\newfontfamily{\nameofcommand}[Mapping=/path/to/map/file]{Fontname} 
```

For instance, for Hebrew, you'd specify a new font family command, pick your favourite Hebrew font, and point XeLaTex at the `hebrew.map` file (in the same directory, in this example):

```latex
\newfontfamily{\hebrew}[Scale=1,Mapping=hebrew]{Ezra SIL} 
```

## Currently implemented, with documentation

Mongolian (Bichig and Cyrillic)

## In progress, in varying states of completion

Arabic

Aramaic

Balinese

Brahmi

Burmese

Egyptian hieroglyphics

Elamite cuneiform

Hebrew

Japanese

Kharosthi

Linear B

N'Ko

Old Persian

Sgaw Karen

Sundanese

Syriac

Tibetan

Ugaritic

## Requests

If there is a writing system you would particularly like to see implemented, let me know! 
