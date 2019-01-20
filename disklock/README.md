# DISKLOCK

uzamykání disků  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

Program DISKLOCK umožňuje uzamykání diskových jednotek a jejich blokování proti
zápisu.  Je určen především k ochraně proti virům a pro víceuživatelský provoz.
Doporučuje se použít též při spouštění neznámého programu.  

Program  lze  ovládat  jak  z příkazového řádku, tak z klávesnice. Při spuštění
programu  (prvním  nebo  opakovaném)  lze  zadat za jménem programu následující
parametry:  

```
1  .... provoz s disketovými jednotkami není omezen      (Shift-Alt-F1)
2  .... diskety chráněny proti modifikaci BOOT sektoru   (Shift-Alt-F2)
3  .... diskety chráněny proti zápisu                    (Shift-Alt-F3)
4  .... přístup na diskety je úplně zablokován           (Shift-Alt-F4)

5  .... provoz s pevným diskem není omezen               (Shift-Alt-F5)
6  .... pevný disk chráněn proti modifikaci BOOT sektoru (Shift-Alt-F6)
7  .... pevný disk chráněn proti zápisu                  (Shift-Alt-F7)
8  .... přístup na pevný disk je úplně zablokován        (Shift-Alt-F8)

K0 .... ovládání z klávesnice není možné
K1 .... ovládání z klávesnice je možné

S0 .... zvuková signalizace zapnuta
S1 .... zvuková signalizace vypnuta

X  .... odinstalování programu z paměti
```

Zadáním  znaku  "?"  jako  parametr  se  zobrazí  nápověda. Při správném zadání
parametrů se zobrazí aktuální stav přepínačů.  

Volby  1 a 5 (Shift-Alt-F1 a Shift-Alt-F5) vyřazují funkci kontroly přístupu na
disky.  

Volby 2 a 6 (Shift-Alt-F2 a Shift-Alt-F6) zajišťují, aby nemohl být modifikován
BOOT  sektor  disku  (u  pevného disku MASTER BOOT). V běžném provozu jej mohou
modifikovat pouze viry a proto je vhodné mít tyto volby nastaveny trvale.  

Volby 3 a 7 (Shift-Alt-F3 a Shift-Alt-F7) nastavují ochranu proti zápisu disku.
Tento  režim  je  vhodné  používat  především při spouštění neznámých programů,
obzvláště je-li u nich podezření na přítomnost virů.  

Volby  4  a  8 (Shift-Alt-F4 a Shift-Alt-F8) vyřazují úplně disketové mechaniky
nebo pevné disky z činnosti.  

Parametrem  X  lze  program  DISKLOCK  odinstalovat z paměti. Zobrazí-li se při
odistalovávání programu chybová zpráva, je nutno nejdříve odinstalovat programy
instalované po programu DISKLOCK.  

DISKLOCK  vyžaduje  k  provozu  počítač  IBM  PC/XT/AT nebo plně kompatibilní a
operační systém DOS verze minimálně 2.00.  

```
                   ————————————————————————————————————————— 
                                     GOLEM                   
                    P.O.Box 66, 756 61 Rožnov pod Radhoštěm  
                             tel/fax: (0651) 54044           
                   ————————————————————————————————————————— 
                    Tento program je součástí programového   
                         balíku DOS Manažer verze 1.50       
                   ————————————————————————————————————————— 
```
