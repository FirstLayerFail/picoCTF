## Úloha: Obedient Cat (Poslušná mačka)

Táto úloha ma naučila, ako stiahnuť súbor priamo z internetu cez terminál a ako si rýchlo zobraziť jeho obsah bez toho, aby som musel "klasicky" otvárať súbor.

Čo bolo zadanie?

V zadaní bol priložený odkaz na stiahnutie súboru s názvom flag. Úloha hovorila, že flag je v tomto súbore priamo "na očiach" (plain sight).

Mal som k dispozícii tieto nápovedy:

Akékoľvek rady týkajúce sa zadávania príkazu do terminálu (napríklad nasledujúceho) budú začínať znakom „$“... všetko za znakom dolára bude napísané (alebo skopírované a vložené) do vášho terminálu.

Na stiahnutie súboru mám použiť príkaz wget s odkazom.

Mám si pozrieť manuál k príkazu cat pomocou príkazu man cat.

Ako som postupoval

1. Stiahnutie súboru (wget)

Najprv som si skopíroval odkaz na súbor z picoCTF a pomocou príkazu wget som ho stiahol priamo do svojho PC:

```wget https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d7cb01727e12e3f9606d89fe45/flag```

2. Prečítanie obsahu súboru (cat)

Nápoveda spomínala príkaz cat. Pozrel som si jeho manuál cez man cat a zistil som, že slúži na: zreťaziť súbory a vypísať na štandardný výstup.
Zadal som teda do terminálu:

```cat flag```


Akonáhle som stlačil Enter, terminál mi okamžite vypísal hľadaný flag.

Môj reálny výpis z terminálu

(Skutočný flag som skryl)
```
tomas@Legion-mint:~$ wget https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d7cb01727e12e3f9606d89fe45/flag

--2026-05-23 15:52:40--  https://challenge-files.picoctf.net/c_wily_courier/4acf636990e4540d6fc36684b1256e625c0617d7cb01727e12e3f9606d89fe45/flag

Prevádza sa challenge-files.picoctf.net (challenge-files.picoctf.net) na IP adresu... 13.227.192.126, 13.227.192.19, 13.227.192.35, ...

Pripájanie k challenge-files.picoctf.net (challenge-files.picoctf.net)|13.227.192.126|:443... pripojené.

HTTP požiadavka odoslaná, čakám na odpoveď... 200 OK

Dĺžka: 34 [application/octet-stream]

Ukladá sa do: ‘flag’

flag                100%[===================>]      34  --.-KB/s    za 0s      

2026-05-23 15:52:41 (41,5 MB/s) - ‘flag’ uložené [34/34]

tomas@Legion-mint:~$ ls
 Documents   flag    Obrázky   Stiahnuté   Verejné  'VirtualBox VMs'
 Dokumenty   Hudba   Plocha    Šablóny     Video
tomas@Legion-mint:~$ man cat
tomas@Legion-mint:~$ cat flag
picoCTF{***_skrytý_flag_***}
```

Získaný flag: picoCTF{***_skrytý_flag_***}

## Čo som sa vďaka tejto úlohe naučil?

Príkaz ```wget```: Slúži na sťahovanie súborov z internetu priamo cez príkazový riadok.

Príkaz ```ls```: zobrazenie súborov v priečinku

Príkaz ```cat```: Najrýchlejší spôsob, ako v termináli zobraziť obsah akéhokoľvek textového súboru.

Príkaz ```man```: Skratka pre manual. Ak pred akýkoľvek príkaz napíšem man (napr. man cat), Linux mi ukáže podrobnú príručku k tomuto príkazu. Z manuálu sa vyskočí stlačením písmena q (quit).
