## Úloha: Insp3ct0r

Táto úloha ma naučila, ako preskúmať webovú stránku pomocou inšpektora v prehliadači, aby som našiel skryté časti flagu v HTML, CSS a JavaScript súboroch.

Čo bolo zadanie?

V zadaní bol odkaz na webovú stránku. Úloha hovorila, že flag je rozdelený na tri časti a každá z nich sa nachádza v inom type súboru (HTML, CSS, JavaScript), ktoré sa načítavajú pri otvorení stránky.

Ako som postupoval

1. Inšpekcia HTML (karta Elements)

Po otvorení stránky a stlačení F12 som si prezrel zdrojový kód HTML. V tele stránky ```<body>```, konkrétne v bloku s triedou tabcontent (záložka "How"), som v komentári našiel prvú časť flagu.

2. Inšpekcia CSS (karta Sources)

Prešiel som na kartu Sources, kde som otvoril súbor mycss.css. V komentároch na konci súboru som našiel druhú časť flagu.

3. Inšpekcia JavaScriptu (karta Sources)

V rovnakej karte Sources som otvoril súbor myjs.js. Tam som našiel poslednú, tretiu časť flagu.

Po spojení všetkých troch častí som získal kompletnú vlajku.

- HTML: picoCTF{1/3
- CSS: 2/3
- JS: 3/3}


Získaný flag: picoCTF{skrytý_flag}

## Čo som sa vďaka tejto úlohe naučil?

Inšpektor prehliadača (F12): Nástroj pri analýze webových aplikácií.

Karta Elements: Slúži na prezeranie HTML štruktúry a nájdenie skrytých komentárov alebo elementov.

Karta Sources: Tu vidím všetky súbory, ktoré si prehliadač stiahol (CSS, JS, obrázky), čo mi umožňuje prehľadávať celý web.

Analýza kódu: Už viem, že ak niečo nie je viditeľné priamo na stránke, nemusí to znamenať, že to tam nie je – vždy treba kontrolovať zdrojové súbory.
