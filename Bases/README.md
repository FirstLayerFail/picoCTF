## Úloha: Bases (Základy / Kódovanie Base64)

Táto úloha bola o kryptografii a kódovaní dát. Naučil som sa, ako rozpoznať kódovanie Base64 a ako ho dekódovať priamo cez Linux terminál.

Čo bolo zadanie?

Dostal som reťazec znakov: bDNhcm5fdGgzX3IwcDM1

Úloha mala nápovedu, že to má niečo spoločné so "základmi" (bases).

Cieľom bolo tento reťazec dekódovať a odovzdať ho vo formáte flagu: picoCTF{výsledok}.

Ako som postupoval

1. Analýza reťazca (Ako spoznať Base64)

Text, ktorý:

Obsahuje zmes malých písmen, veľkých písmen a čísel,

Končí občas znakom = alebo == (tzv. padding - výplň, hoci v tomto prípade tu nebola),

Vyzerá ako náhodný zhluk znakov, ale neobsahuje špeciálne znaky,

s veľkou pravdepodobnosťou ide o Base64. Base64 využíva 64 znakov (A-Z, a-z, 0-9, + a /) na prenos dát.

2. Dekódovanie v termináli

Namiesto ponúkanej možnosti použiť CyberChef som využil Linux terminál a jeho zabudovaný nástroj base64.

Použil som príkaz:

```echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d```


```echo``` poslal zašifrovaný text ďalej.

```|``` (pipe) presmeroval výstup do ďalšieho programu.

```base64 -d``` prijal text a dekódoval ho (prepínač -d znamená decode).

Terminál okamžite vypísal výsledný text: skrytý_flag.

Môj reálny výpis z terminálu
```
tomas@Legion-mint:~$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
skrytý_flagtomas@Legion-mint:~$
```


Môj získaný flag: picoCTF{skrytý_flag}

## Čo som sa vďaka tejto úlohe naučil?

Rozdiel medzi šifrovaním a kódovaním: Base64 nie je šifra na utajenie dát (keďže ju vie každý ľahko dekódovať).

Je to kódovanie, ktoré slúži na to, aby sa binárne dáta dali bezpečne prenášať v textových systémoch bez toho, aby sa poškodili.

Príkaz ```base64```: Skvelý Linux pomocník. Ak by som chcel naopak niečo zakódovať, napíšem napr. echo "ahoj" | base64. Na dekódovanie slúži prepínač -d.

```|``` (rúra/pipe): dá sa použiť na spájanie viacerých príkazov.
