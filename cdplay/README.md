# CDPLAY

přehrávač audio CD disků  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

## Syntaxe

```
  CDPLAY  [I] [L | L hh:mm:ss] [P n] [S] [C] [D]
           I .......... zobrazení informací o disku v mechanice
           L .......... výpis obsahu disku (seznam nahrávek)
           L hh:mm:ss . výpis obsahu disku s přičtením času
           P n ........ PLAY, přehrávání od nahrávky n (implic. n=1)
           S .......... STOP, zastavení přehrávání
           C .......... CONTINUE, pokračování v přehrávání
           D .......... zobrazení stavu přehrávání, ovládání přehrávání disku
           T .......... test stavu přehrávání pomocí návratového kódu:
                               0 = probíhá přehrávání
                               1 = neprobíhá přehrávání
                             255 = chyba
```

## Charakteristika

Program  CDPLAY  je  nadstavbou  umožňující řízení přehrávání audio CD disků. K
jeho funkci je nutná instalace ovladače CD-ROM disků (jako např. program MSCDEX
umožňující  používání  CD-ROM  jako  logického  disku  DOS).  Tento  ovladač je
zpravidla dodáván spolu s mechanikou CD-ROM. Při instalaci více logických disků
DOS pracuje program CDPLAY vždy s prvním nalezeným diskem CD-ROM.

## Úvodní poznámka

CD  disk  je  organizován  po  sektorech 2048 bajtů, označovaných též jako tzv.
rámce  (=FRAME). Ukazatel přehrávací pozice na CD disku je zpravidla vyjadřován
údajem  "minuta:sekunda:rámec".  Jedna  sekunda  přitom  obsahuje 75 rámců. Pro
vyšší   názornost   je   v   programu   CDPLAY   použito   vyjádření  ve  tvaru
"minuta:sekunda,setina_sekundy" podle vztahu "setina_sekundy=rámec*100/75".

## Zobrazení informací o disku

Zadáním parametru "I" se zobrazí informace o disku CD:

* verze ovladače CD-ROM (tj. verze programu MSCDEX)
* označení logického disku s CD-ROM
* počet nahrávek na disku CD (u CD-ROM včetně datové stopy)
* celková hrací doba disku (formát "minuta:sekunda,setina_sekundy")
* velikost jednoho sektoru disku (převážně 2048 bajtů)
* celková velikost disku v sektorech (a v MB)

## Výpis obsahu disku

Zadáním  parametru  "L"  se  zobrazí  seznam  nahrávek  na disku CD. Jednotlivé
nahrávky  jsou zobrazeny na samostatných řádcích. Každý řádek začíná absolutním
časem  začátku  nahrávky na disku vyjádřený ve formátu "hodina:minuta:sekunda".
Následuje  číslo  nahrávky a na konci řádku délka nahrávky vyjádřená ve formátu
"minuta:sekunda:setina_sekundy". Za údajem délky nahrávky může následovat ještě
upřesnění typu nahrávky:

* DATA .... stopa obsahuje data CD-ROM (lze zobrazit v DOS jako logický disk)
* QUADRO .. nahrávka je kvadrofonní (4 kanály, jinak stereofonní - 2 kanály)
* PREEM ... u nahrávky použita korekce - preemfáze
* COPY .... nahrávka není chráněna proti digitálnímu kopírování

Na  konci  seznamu  nahrávek  je  řádek  začínající časem konce disku a končící
celkovou délkou nahrávek na disku.  

Formát  výpisu seznamu nahrávek je připraven k použití jako seznam nahrávek při
kopírování CD disku na kazetu (audio nebo video HiFi). Uvedením času ve formátu
"hodina:minuta:sekunda"  za  parametrem "L" lze zadat počáteční čas CD disku na
magnetofonu, tento čas je připočítán k počátečnímu času jednotlivých nahrávek.  

Výpis seznamu lze pomocí přesměrování ">" uložit do souboru - např.:

```
CDPLAY L 2:23:45 > enigma.lst
```

nebo pro připojení k existujícímu seznamu:

```
CDPLAY L 2:23:45 >> enigma.lst
```

Pomocí  běžného  textového  editoru  postačí potom dopsat na pozice teček jména
jednotlivých skladeb, seznam vytisknout a vložit do kazety.  

Výhody  tohoto způsobu výpisu vyniknou především ve spojení s videomagnetofonem
s časovým počitadlem. Při této příležitosti lze doporučit jako nejvhodnější typ
k  nahrávání CD videomagnetofon PANASONIC NV-HD90 nebo NV-HD100, který umožňuje
na  kazety  E-240  zaznamenat  8  hodin  nahrávek  v  kvalitě  CD  (nezapojovat
videovstup (!),  mohla  by se zhoršit kmitočtová stabilita; některé jiné značky
magnetofonů bez videosignálu nepracují spolehlivě).

## Přehrávání disku

Povelem  "P n" lze zahájit přehrávání disku od nahrávky číslo n (n=číslo 1...),
bez zadání n se přehrává implicitně od nahrávky 1.  

Povelem  "S"  lze  přehrávání  disku  zastavit.  Povelem  "C"  lze pokračovat v
přehrávání disku dále (od místa zastavení povelem "S").  

Nelze přehrávat stopu CD-ROM disku obsahující data.  

## Zobrazení stavu přehrávání

Po  zadání  parametru  "D"  se průběžně zobrazuje aktuální stav přehrávání (tj.
ukazatel pozice přehrávání):


* nahrávka ...... číslo právě přehrávané nahrávky
* čas ........... aktuální čas v přehrávané nahrávce
* zbývá ......... zbývající čas do konce přehrávané nahrávky
* délka ......... délka právě přehrávané nahrávky
* čas abs. ...... aktuální čas na disku
* zbývá abs. .... zbývající čas do konce disku
* délka abs. .... celková délka celého disku

Všechny údaje času jsou uvedeny ve formátu "minuta:sekunda,setina_sekundy".  

Během  zobrazení  aktuálního  stavu  přehrávání  lze  řídit  přehrávání  pomocí
následujících kláves:

* šipka nahoru ...... přehrávání od předešlé nahrávky
* šipka dolů ........ přehrávání od následující nahrávky
* šipka vlevo ....... posun o 15 sekund zpět
* šipka vpravo ...... posun o 15 sekund vpřed
* mezera ............ zastavení/pokračování v přehrávání (zobrazí se "STOP")
* ESC ............... přerušení režimu zobrazení stavu přehrávání

Při  zastavení  přehrávání  se  může u některých mechanik CD projevovat kmitání
údaje setin sekundy - není to projevem závady. Během zastavení lze též posouvat
ukazatele přehrávání a nastavit tak místo určené k přehrávání.  

Parametr "D" lze kombinovat i s jinými parametry. Např. příkazem

```
CDPLAY P2 L D
```

se zobrazí seznam nahrávek na disku, začne se přehrávat od 2. nahrávky a spustí
se režim zobrazení přehrávání.
