# RFID DOMINATOR - Airsoft / Paintball
* Pri záujme o plnú verziu projektu kontaktujte na: martinius96@gmail.com

**Popis:**
* DOMINATOR je zariadenie - stopky, ktoré využívajú RFID vstup
* Využíva riadiaci mikrokontróler (Arduino Uno / Nano).
* Na znakovom LCD displeji sa vyobrazujú časy jednotlivých tímov (RED a GRE tím.)
* Každý z členov tímu je vybavený kartou, alebo kľúčenkou, ktorá komunikuje na 13.56MHz. Kľúčenky môžu byť farebné odlíšené (modré, červené pre ich ľahšie pridelenie hráčom...)
* Ak tím obsadí bod, hociktorý hráč tohto tímu priloží svoju kartu k čítačke. 
* Rozsvieti sa dióda daného tímu (červená / zelená) na tomto stanovišti a začne sa pripočítavať čas danému tímu. 
* Čas sa počíta až do momentu, kedy bod obsadí druhý tím 
* Ak priloží člen druhého tímu svoju kartu, rozsvieti sa dióda toho daného tímu, čas druhého tímu sa pauzuje a počíta sa čas toho tímu, ktorý bod obsadil. 
* Ak kartu / kľúčenku priloží organizátor (rozhodca), oba časy sa zapauzujú až do momentu, kým nepriloží kartu niektorý z tímov (pauza v hre, koniec hry, vyhodnotenie). 
* Poslednou možnou kartou v systéme je použitie tzv. eraser karty, ktorá oba časy zapauzuje a vynuluje (reštart hry, nová hra).
* Maximálny časový rozsah systému je: 99 hodín 99 minút 59 sekúnd, vhodné teda aj pre akcie a športové areály zaoberajúce sa Airsoftom, Paintballom. 
* Čítačka NXP RC522 pracuje na frekvencii 13.56MHz, RFID tagy registruje na cca 3 centimetre (nutný skoro až fyzický dotyk s čítačkou), kompatibilný formát tagov ISO/IEC 14443 A.
* **Pre projekt je kompatibilná čítačka RC522 s originálnym NXP čipom!** Counterfeit (0x12) čip nie je v systéme podporovaný a je knižnicou dátovo ukončená komunikácia s čítačkou.
* Očakávaná verzia RFID čítačky vypísaná na UART monitor: 0x92 (version 2) 
* Program UID_GET.ino v priečinku examples je možné použiť pre načítanie kódov z RFID kariet, ktoré chcete použiť vo finálnej aplikácii DOMINATOR-a.
* Vhodné je adresy spísať do Excel tabuľky a farebne odlíšiť, aby ste mali adresy k dispozícii aj do budúcna
* K projektu existuje DPS návrh GERBER (s vŕtaním a strojovou výrobou DPS), alebo DPS pre výrobu fotocestou
* Obe DPS sú obojstranné a s prekovmi. Rozmer 100x105mm.
* Sú k projektu dodávané GRÁTIS

![Fyzické UID čísla RFID kariet v Excel tabuľke pre použitie v projekte RFID DOMINATOR](https://i.imgur.com/LvXPxVq.png)

**Hardvér použitý pre projekt RFID DOMINATOR:**
* Arduino Uno / Nano (DPS je výhradne navrhnutá pre Arduino Nano)
* RFID RC522
* 2x LED diódy
* 2x predradný rezistor pre LED (možno použiť aj 2x I2C pullup rezistor - použitý v DPS)
* LCD displej 16x2/20x4 s I2C prevodníkom
* Buzzer (hlásič)
* kompatibilné karty a kľúčenky štandardu ISO/IEC 14443-A
# Screenshoty projektu RFID DOMINATOR
![Štart Airsoft Hry - RFID DOMINATOR - Arduino - Airsoft](https://i.imgur.com/OY0geF2.jpg)
![DPS - GERBER - RFID DOMINATOR - Arduino - Airsoft](https://i.imgur.com/YMe2Y4L.png)
![DPS - Výroba fotocestou - RFID DOMINATOR - Arduino - Airsoft](https://i.imgur.com/cbZssQT.png)
![Schéma zapojenia - RFID DOMINATOR - Arduino - Airsoft](https://i.imgur.com/g5ufkBO.png)

# Tlačidlový DOMINATOR - Airsoft / Paintball
* Logikou totožný ako RFID DOMINATOR, využíva však tlačidlový vstup spínacími tlačidlami
* Hráč tímu po obsadení bodu stlačí príslušné tlačidlo, čím obsadí bod (reakcia na stlačenie je okamžitá). 
* Hlásič (buzzer) pípnutím oznámi obsadenie bodu, rozsvieti sa LED dióda daného tímu, začne sa počítať čas.
* Čas sa pre tento tím počíta do momentu, kým bod neobsadí a neaktivuje svoje tlačidlo člen druhého tímu, čo zastaví pôvodný čas a začne sa pripočítavať čas k druhému tímu.
* Rozhodca má svoje tlačidlo, ktorým dokáže čas zastaviť - vykonať pauzu. Pauza hry, obed, koniec hry, spočítanie času a vyhodnotenie herného kola.
* Posledným tlačidlom v systéme je možnosť erasera, ktorý čas zastaví a vynuluje (reštart hry, nová hra). 
* LED diódy je možné nahradiť za relé pre možnosť spínať výkonnejšie svietidlá pre lepšiu viditeľnosť aktuálnej farby DOMINATOR-a
* K projektu nie je dostupný DPS návrh (neplánuje sa)

# Shareware verzia - Tlačidlový DOMINATOR
**K projektu Tlačidlový DOMINATOR existuje Shareware verzia, kde je možné vyskúšať funkčnosť celého systému s vašim hardvérom.**
* Testovací firmvér je v Shareware verzii obmedzený na maximálne 15 sekundové meranie obsadenia bodu každým tímom
* Verzia využíva 30 sekundovú inicializáciou systému pred jeho možným použitím. 
* Testovací firmvér je v strojovom kóde (.hex)
* Nahrať do Arduino Uno dosky je možné firmvér cez nástroj Xloader (dostupný v repozitári).
* Firmvér je iba pre Arduino Uno / Nano dosku (AtMega328P), pre iné dosky nebude fungovať!
* Pre Arduino Nano s Old Bootloaderom je nutné zvoliť nahrávaciu rýchlosť 57600 baud/s. Pre Uno a Nano s novším Bootloaderom 115200 baud/s.
* Testovací firmvér je založený na schéme zapojenia pre Tlačidlový DOMINATOR bez buzzera (LED diódy fungujú a vizualizujú stav, rovnako displej vypisuje čas)
# Použitie nástroja XLoader pre nahratie strojového kódu do Arduina
![Použitie programu XLoader](https://i.imgur.com/jpKuhTc.png)

**Hardvér použitý pre projekt Tlačidlový DOMINATOR:**
* Arduino Uno / Nano
* 2x LED diódy
* 2x predradný rezistor pre LED (možno použiť aj 2x I2C pullup rezistor)
* LCD displej 16x2/20x4 s I2C prevodníkom
* Buzzer (hlásič)
* 4x spínacie tlačidlá (pushbutton)

# Screenshoty projektu Tlačidlový DOMINATOR
![Tlačidlový DOMINATOR - Arduino - Airsoft - bežiaca hra](https://i.imgur.com/yuHmpZa.jpg)
![Schéma zapojenia - Tlačidlový DOMINATOR - Arduino - Airsoft](https://i.imgur.com/D9KcneX.png)
