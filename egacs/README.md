# EGACS

České a slovenské fonty pro displeje EGA, VGA, LCD-VGA a Super VGA  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

## Syntaxe

```
EGACS  [ 0 | K | L | M | I | W | O | ! ]

              0 ... kód znaků IBM (funkce vypnuta)
              K ... národní kód bratří Kamenických (KEYBCS2)
              L ... národní kód Latin 2 (implicitně)
              M ... národní kód Latin 2 - minimalizovaná verze
              I ... národní kód KOI 8 (editor Text602)
              W ... národní kód WINDOWS (ISO 8859)
              O ... národní kód ISO 8859/2 (ISO Latin 2)
              ! ... odinstalování z paměti

Nastavení programu lze měnit i dodatečně po nainstalování.
```

## Jak přeložit

```
tasm EGACS
tlink EGACS /t
```
