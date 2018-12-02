# CSKEY

Ovladač české a slovenské klávesnice  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

## Syntaxe

```
CSKEY  [{1|2|3|4|5|6|7}]  [{K|L|I|W|O}]  [{C|S}]  [{D|T}]  [Zn]  [!]  [Pabcd]


      1 ...... standardní klávesnice IBM
      2 ...... programátorská  klávesnice
      3 ...... písařská  klávesnice
      4 ...... grafické pole - jednoduchá čára
      5 ...... grafické pole - dvojitá čára
      6 ...... grafické pole - vodorovná dvojitá, svislá jednoduchá 
      7 ...... grafické pole - vodorovná jednoduchá, svislá dvojitá
      K ...... generovány znaky v kódu bratří Kamenických (KEYBCS2)
      L ...... generovány  znaky v kódu Latin 2 (implicitní)
      I ...... generovány znaky v kódu KOI 8 (textový editor TEXT602)
      W ...... generovány znaky v kódu WINDOWS (ISO 8859)
      O ...... generovány znaky v kódu ISO 8859/2 - ISO LATIN 2
      C ...... české uspořádání klávesnice
      S ...... slovenské uspořádání klávesnice
      D ...... generována desetinná čárka v numerickém poli klávesnice
      T ...... generována desetinná tečka v numerickém poli klávesnice
      Zn ..... záměna  kláves  Y  a  Z  (0=nikdy, 1=kromě písařské klávesnice,
               2=pouze písařská klávesnice, 3=vždy)
      ! ...... odinstalování programu z paměti
      ? ...... zobrazení nápovědy k parametrům
      Pabcd .. definice prefixových kláves (1 až 4 znaky: první dva znaky jsou
               použity pro všechny klávesnice kromě písařské, druhé dva  znaky
               jsou použity pro písařskou klávesnici)

Implicitní nastavení parametrů:    CSKEY 1 L Z2 C T P``=+
```

## Jak přeložit

```
tasm CSKEY
tlink CSKEY /t
```
