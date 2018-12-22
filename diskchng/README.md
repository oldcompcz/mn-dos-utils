# DISKCHNG

test výměny diskety v disketové jednotce  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

Program DISKCHNG umožňuje v povelovém souboru provádět test, zda je v disketové
mechanice  vložena  disketa  a  zda  byla disketa od poslední disketové operace
vyměněna.  Při spuštění programu se za jménem programu uvede označení disketové
mechaniky (písmeno A nebo B). Po otestování mechaniky program navrátí návratový
kód podle stavu disketové mechaniky:

* 0=disketa je vložena a nebyla měněna
* 1=disketa je vložena, ale byla od poslední operace (posledního testu) vyměněna
* 2=disketa není vložena do mechaniky nebo dvířka mechaniky nejsou uzavřena
* 3=chybné zadání disketové mechaniky

Program  využívá  signálu  výměny  diskety,  který  je  generován  v  disketové
mechanice.  Tento  signál  se  nastaví  při  každém vyjmutí diskety z disketové
mechaniky  a  nuluje se až při přístupu na disketovou mechaniku. Z toho vyplývá
chování mechaniky při testu: pokud je disketa vložena, kontrolka je během testu
pomocí  programu  DISKCHNG  zhasnuta. Pokud je disketa vyjmuta, začne kontrolka
mechaniky  poblikávat (provádí se pokus o přístup na disketu) a generuje se kód
2  (mechanika  nepřipravena).  Po  zasunutí  diskety  se při příštím testu jeví
mechanika  jako  připravena,  signál  výměny  se vynuluje a vygeneruje se kód 1
(disketa  byla  vyměněna,  ale  již  je  zasunuta).  Dále se již až do příštího
vyjmutí diskety generuje opět kód 1.  

Dále uvedený povelový soubor je příkladem použití programu - umožňuje vytváření
seznamu  souborů na disketách bez nutnosti manipulace s klávesnicí (podobně lze
program  využít  např. k formátování většího množství disket pouhým vyměňováním
disket).  

```
@echo off
cls
echo  ————————— Priklad pouziti programu DISKCHNG —————————— 
echo      Tento povelovy soubor vam vytvori seznam vsech     
echo   souboru na disketach bez dotyku na klavesnici. Staci  
echo   jenom vymenovat podle pokynu diskety v mechanice A:.  
echo    Cinnost se ukonci stiskem Ctrl-Break. Seznam bude    
echo    vytvoren v aktivnim adresari v souboru DISKETY.TXT.  
echo  —————————————————————————————————————————————————————— 
echo.
wait
echo.
echo.> DISKETY.TXT
echo             SEZNAM  SOUBORU            >> DISKETY.TXT
echo.>> DISKETY.TXT
echo.>> DISKETY.TXT
diskchng a
if errorlevel == 2 goto vloz

:otevri
rem -------- Čekání, až se vyjme stará disketa -------
echo Vyjmete disketu z mechaniky ....
:cek2
diskchng a
if not errorlevel == 2 goto cek2

:vloz
rem -------- Čekání, až se vloží nová disketa --------
echo Vlozte novou disketu a zavrete dvirka ....
:cek1
diskchng a
if errorlevel == 1 goto cek1

:akce
rem ------- Provedeni operace s disketou
dir a: >> DISKETY.TXT
echo.>> DISKETY.TXT
echo.
goto otevri
```

DISKCHNG  vyžaduje  k  provozu  operační  systém  kompatibilní  s  MS DOS verze
minimálně 2.00 a řadič disketových mechanik kompatibilní s I8272.

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
