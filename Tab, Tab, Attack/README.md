## Úloha: Tab, Tab, Attack (Útok klávesom Tab)

Táto úloha ma naučila trik pre prácu v Linux termináli – dopĺňanie názvov súborov a priečinkov pomocou klávesu Tab.

Čo bolo zadanie?

Dostal som na stiahnutie súbor Addadshashanammu.zip. Zadanie hovorilo, že po rozbalení sa dá táto úloha vyriešiť na 11 stlačení klávesov (väčšinou stláčaním klávesu Tab).

Nápoveda hovorila:

Dopĺňanie pomocou Tab v termináli ti pridá roky života, najmä pri dlhých a zložitých štruktúrach priečinkov.

Ako som postupoval

1. Stiahnutie súboru (wget)

Skopíroval som odkaz na súbor z picoCTF a pomocou príkazu ```wget``` som ho stiahol priamo do svojho PC:

2. Rozbalenie archívu (unzip a Tab)

Namiesto pracného písania celého názvu archívu som napísal iba začiatok a stlačil Tab. Terminál názov okamžite doplnil sám:

```unzip Addadshashanammu.zip```


3. Prechod cez dĺhu štruktúru priečinkov

Vytvoril sa priečinok s dlhým názvom. Napísal som:

```cd Add```


a stlačil Tab. Keďže v každom podpriečinku bol len jeden ďalší priečinok, stačilo mi opakovane stláčať Tab. Linux sám dopĺňal lomky a ďalšie priečinky až na koniec cesty:

```Addadshashanammu/Almurbalarammi/ ... /Ularradallaku```


Nakoniec som len stlačil Enter.

4. Spustenie programu (./)

V cieľovom priečinku som si príkazom ```ls``` zobrazil obsah. Nachádzal sa tam spustiteľný súbor (program).

V Linuxe spúšťame programy v aktuálnom priečinku pomocou predpony ./ pred názvom súboru. Napísal som to teda na začiatok názvu a opäť stlačil Tab, ktorý ho doplnil:

```./fang-of-haynekhtnamet```


Po stlačení Enteru program spustilo a vypísal mi hľadaný flag.

Môj reálny výpis z terminálu

(Skutočný flag som schoval)

```
tomas@Legion-mint:~$ wget https://challenge-files.picoctf.net/c_wily_courier/ce53ef9432bf367be41e465224d721c1187c39debcd758efcd28e99a6b7ff7a4/Addadshashanammu.zip
--2026-05-23 18:28:01--  https://challenge-files.picoctf.net/c_wily_courier/ce53ef9432bf367be41e465224d721c1187c39debcd758efcd28e99a6b7ff7a4/Addadshashanammu.zip
Prevádza sa challenge-files.picoctf.net (challenge-files.picoctf.net) na IP adresu... 13.227.192.19, 13.227.192.102, 13.227.192.35, ...
Pripájanie k challenge-files.picoctf.net (challenge-files.picoctf.net)|13.227.192.19|:443... pripojené.
HTTP požiadavka odoslaná, čakám na odpoveď... 200 OK
Dĺžka: 5166 (5,0K) [application/octet-stream]
Ukladá sa do: ‘Addadshashanammu.zip’

Addadshashanammu.zip       100%[========================================>]   5,04K  --.-KB/s    za 0s      

2026-05-23 18:28:02 (1,27 GB/s) - ‘Addadshashanammu.zip’ uložené [5166/5166]

tomas@Legion-mint:~$ unzip Addadshashanammu.zip 
Archive:  Addadshashanammu.zip
creating: Addadshashanammu/
creating: Addadshashanammu/Almurbalarammi/  
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
extracting: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet.c 
inflating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/fang-of-haynekhtnamet 
tomas@Legion-mint:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
tomas@Legion-mint:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c
tomas@Legion-mint:~/Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku$ ./fang-of-haynekhtnamet 
*ZAP!* picoCTF{***_skrytý_flag_***}
```
Získaný flag: picoCTF{***_skrytý_flag_***}

## Čo som sa vďaka tejto úlohe naučil?

Dopĺňanie pomocou Tab: Ak napíšem prvé písmená príkazu, priečinka alebo súboru a stlačím Tab, terminál ho sám dopíše.

Spúšťanie súborov pomocou ```./```: V Linuxe nestačí len napísať názov programu, ak sa nachádza v aktuálnom priečinku. Z bezpečnostných dôvodov musíme pred názov pridať ```./``` (napr. ./program).
