# Automatic transliteration in XeLaTeX

This repository provides a set of mappings of ASCII characters to non-Roman writing systems, allowing the user to type in the Roman alphabet and have the compiled output rendered in another writing system. This may be useful to reduce errors in writing systems the user is not very familiar with, or simply as a workaround for poor editor or OS rendering of the writing system.

Note that this transliteration requires use of the `fontspec` package, and therefore requires use of XeLaTeX or LuaLaTeX. It is also dependent on appropriate fonts being installed for the writing systems in question; these are not provided in this repository, although the guides for each writing system indicate which font they are typeset in and suggest alternatives as appropriate.

The transliterations are defined in plaintext in `.map` files. In order to be used in transliteration, they must be compiled into `.tec` files; these can be kept in an arbitrary directory or in one relative to the `.tex` file. This repository provides `.tec` files for each writing system that correspond to the transliteration described in their respective `.pdf` guides; the original `.map` files are provided in case users wish to make alternations to the mappings in a way that is more intuitive or convenient for them.

Transliterations are specified in the preamble of the `.tex` file, when the relevant font family is introduced. The `\newfontfamilycommand` takes an optional argument `Mapping=`, which should point to the `.tec` file being used for the transliteration. In some cases, a `Script=` argument may also be necessary for correct rendering of the typeface. 

```latex
\newfontfamily{\nameofcommand}[Mapping=/path/to/tec/file]{Fontname} 
```

For instance, for Mongolian, you'd specify a new font family command, pick your favourite Mongolian font, and point XeLaTex at the `mongolian-bichig.tec` file (in the same directory, in this example):

```latex
\newfontfamily{\mongolian}[Scale=1,Script=Mongolian,Mapping=mongolian-bichig]{Noto Sans Mongolian} 
```

Then, using the `\mongolian` command will both change the font to Noto Sans Mongolian and automatically transliterate any text typed: `sorgug` will be output as ᠰᠣᠷᠭᠤᠭ.


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
