# WAIT

Čekání povelového souboru na stisk klávesy  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

## Popis

Pomocí  programu  WAIT  lze  pozastavit vykonávání povelového souboru do stisku
klávesy  (čekání na potvrzení uživatele). Spuštěním programu WAIT bez parametrů
se  zobrazí  výzva  "Stiskni  libovolnou  klávesu  ..." a program čeká na stisk
libovolné  klávesy.  Po  stisku  libovolné  klávesy se zobrazená výzva vymaže z
obrazovky  a  povelový  soubor  pokračuje  ve  své činnosti (tedy jistá náhrada
příkazu PAUSE).  

Jako  parametr  programu  WAIT  lze  zadat  text,  který  se zobrazí jako výzva
uživateli  (namísto  výše  uvedené  výzvy).  Text se zobrazí od druhého znaku v
příkazovém  řádku  za jménem programu WAIT (oddělovací znak mezery za jménem se
ignoruje) po poslední zadaný znak v příkazovém řádku. Je-li prvním znakem textu
znak  dvojité  uvozovky  "  (tj. znak na druhé pozici za jménem programu WAIT),
zobrazí se text až od následující pozice a vypustí se též podobně znak uvozovky
na  konci  řádku  (je-li uveden jako poslední znak v řádku). Uzavřením textu do
uvozovek  lze zadávat v textu též speciální znaky operačního systému, jako jsou
znaky <, >, | a pod.  

Program  WAIT  navrací návratový kód systému vždy 0, pouze po stisku kláves ESC
nebo  Ctrl-Break  navrátí  návratový  kód  1.  To  je  možné využít k přerušení
činnosti povelového souboru.

## Demonstrační příklad použití

```
@echo off
:zac
wait "Čekám na stisk libovolné klávesy (<Esc>=přerušení): "
if errorlevel == 1 goto preruseno
echo OK
goto zac
:preruseno
echo Operace PŘERUŠENA !
```

WAIT  vyžaduje k provozu počítač IBM PC/XT/AT nebo plně kompatibilní a operační
systém DOS verze minimálně 2.00.

## Jak přeložit

```
tasm WAIT
tlink WAIT /t
```
