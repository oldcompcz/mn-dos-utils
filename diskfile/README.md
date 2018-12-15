# DISKFILE

Souborové kopírování disket  
(c) [Miroslav Němeček](https://github.com/oldcompcz/readme/wiki/Nemecek)  

Program  DISKFILE  urychluje  kopírování disket. Je možné zkopírovat celý obsah
diskety  do  jednoho souboru nebo opačně soubor s obsahem diskety zkopírovat na
disketu.  Tímto  způsobem  se zrychlí vícenásobné kopírování diskety se stejným
obsahem,  neboť lze disketu přečíst pouze jednou a potom již vytvářet libovolný
počet  kopií.  Zpomalení  vzniklé  ukládáním  souboru  s obsahem diskety je při
použití  pevného  disku zanedbatelné, proto je tato metoda výhodná již při dvou
kopiích  jedné  diskety  a  ani při jedné kopii není nutné používat jiný způsob
kopírování.  

Další  výhody  přináší  tento  způsob  při  kopírování disket s větším formátem
(např. 1.2 MB), jejichž obsah se nevejde celý do paměti a je potřeba při běžném
kopírování  vyměňovat diskety vícekrát. Při použití DISKFILE je potřeba vyměnit
diskety pouze jednou, čímž se sníží obtížnost manipulace s disketami.  

Důležitým  využitím  programu  DISKFILE  může  být archivace diskety v původním
tvaru.  Jako  příklad  může  posloužit systémová disketa. Programem DISKFILE se
uloží  obsah  systémové  diskety  do  souboru.  S  tímto  souborem je potom již
snadnější  manipulace  při  archivaci  než  s celou disketou. Soubor lze snadno
archivovat  komprimačním programem do malého souboru. Po dekompresi souboru lze
vytvořit  zpětně  opět  disketu shodnou s původní disketou, tedy i se zavaděčem
operačního  systému.  Tím  se  též liší od systémového kopírování disket, které
ponechává sériové číslo cílové diskety.  

Program se může uplatnit též při startu počítače. Někdy se používá RAM-disk pro
zrychlení   spouštění  často  používaných  programů.  Proto  se  při  instalaci
operačního  systému  někdy  kopírují  do  RAM-disku  často  používané  programy
operačního  systému, především pak povelový interpreter COMMAND.COM. Obvykle se
do  RAM-disku  instaluje  i  nadstavba operačního systému typu Norton Commander
nebo DOS Manažer. Pro zrychlení instalace programů do RAM-disku je možné uložit
obsah  celého  RAM-disku  do  souboru a při startu operačního systému zapsat do
RAM-disku  celý  obsah  najednou,  což  je  rychlejší  operace  než  kopírování
jednotlivých souborů samostatně.  

Při  spuštění  programu  je  nutno uvést dva parametry. První parametr označuje
zdroj  operace,  druhý  parametr označuje cíl operace. Jako parametry lze uvést
označení   disku  (např.  A:)  nebo  soubor  (např.  C:\system1.dsk).  Povolené
kombinace  jsou disk/soubor (uchování obsahu disku do souboru) nebo soubor/disk
(vytvoření  kopie  diskety).  Při vytváření kopie diskety se vyžaduje, aby byla
disketa  předem naformátována na formát stejný jako byla původní disketa. Během
operace  kopírování se vyžaduje bezchybnost zdrojové i cílové diskety. Pokud se
během kopírování vyskytne chyba čtení nebo zápisu, ohlásí se chyba a operace se
přeruší.  

Existuje-li cílový soubor při ukládání obsahu disku do souboru, ohlásí se chyba
a  operace  se  neprovede  (soubor  je  nutno  zrušit).  Uvede-li se jako další
parametr při spuštění programu /W, cílový soubor se přepíše bez ohlášení chyby.

Před  kopírováním  souboru  na  disk  se  zobrazí  varování  a operaci je nutno
potvrdit  stiskem  klávesy Enter. Po zadání parametru /W se obsah disku přepíše
bez varování.  

DISKFILE  vyžaduje  k  provozu  počítač  IBM  PC/XT/AT nebo plně kompatibilní a
operační systém MS DOS verze minimálně 2.00.  

```
                   ————————————————————————————————————————— 
                                     GOLEM                   
                    P.O.Box 66, 756 61 Rožnov pod Radhoštěm  
                             tel/fax: (0651) 54044           
                   ————————————————————————————————————————— 
                    Tento program je součástí programového   
                         balíku DOS Manažer verze 1.55       
                   ————————————————————————————————————————— 
```
