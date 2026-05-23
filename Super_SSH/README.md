## Úloha: Super SSH

Server: titan.picoctf.net

Port: 61427

Meno: ctf-player

Heslo: f3b61b38

Cieľom bolo prihlásiť sa na tento server a nájsť skrytý flag.

Postup:

1. Príkaz na pripojenie

Skúsil som použiť klasický SSH príkaz. Hneď na začiatku som ale narazil na problém s prihlásením, následne som zistil, že sa nepripájam na bežný port (ktorý býva automaticky 22), ale na špeciálny port 61427. Preto bolo v zadaní číslo portu.

Musel som použiť -p (port) a celý príkaz v termináli vyzeral takto:

```ssh ctf-player@titan.picoctf.net -p 61427```

2. Overenie servera

Terminál si vypýtal potvrdenie (fingerprint) a opýtal sa ma, či chcem pokračovať. *yes + Enter*

3. Zadanie heslo

Skopíroval som si f3b61b38 a vložil ho do terminálu. Lenže na obrazovke sa neobjavila ani jedna hviezdička, ostalo tam prázdne miesto. Najprv som si myslel, ze pri hesle nefunguje klasické kopírovanie no potom som zistil, že linux z bezpečnostných dôvodov nezobrazuje zadávanie hesla

4. Získanie flagu

Hneď po potvrdení hesla ma server automaticky privítal a priamo do terminálu mi vypísal flag, server ma po vypísaní flagu rovno odpojil.

Môj reálny výpis z terminálu

(Skutočný flag som skryl)
```
tomas@Legion-mint:~$ ssh ctf-player@titan.picoctf.net -p 61427

The authenticity of host '[titan.picoctf.net]:61427 ([3.139.174.234]:61427)' can't be established.

ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.

This key is not known by any other names.Are yousureyou want to continue connecting (yes/no/[fingerprint])? yes

Warning: Permanently added '[titan.picoctf.net]:61427' (ED25519) to the list of known hosts.

ctf-player@titan.picoctf.net's password: 

Welcome ctf-player, here's your flag: picoCTF{***_skrytý_flag_***}

Connection to titan.picoctf.net closed.*
```

Získaný flag: picoCTF{***_skrytý_flag_***}

## Čo som sa vďaka tejto úlohe naučil?

Čo je to SSH: Je to bezpečný spôsob, ako sa pripojiť na iný počítač vo svete cez príkazový riadok.

Hláška: The authenticity of host '[titan.picoctf.net]:61427 ([3.139.174.234]:61427)' can't be established.

ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.

This key is not known by any other names.

Are you sure you want to continue connecting (yes/no/[fingerprint])?

Každý SSH server má svoj vlastný, jedinečný kryptografický kľúč.

ED25519 je typ šifrovacieho algoritmu, ktorý ten kľúč vygeneroval

SHA256:4S9EbTSSRZm32I... je odtlačok prsta (fingerprint) tohto kľúča. Keďže samotný kľúč je obrovský kus textu, SSH ukáže len krátky "odtlačok", aby sa dal vizuálne skontrolovať.

Nezabúdať na príkaz -p: Ak server beží na inom porte ako predvolenom (22), musím ho v príkaze jasne zadať, inak ma nepripojí.

Zadávanie hesla v terminály: Už viem, že ak terminál pri písaní hesla nič neukazuje, je to bezpečnostná funkcia Linuxu, nie chyba. Stačí písať/vložiť a stlačiť Enter.

Skratky v Linux termináli: Na vkladanie v konzole nefunguje klasické Ctrl+V, ale Ctrl+Shift+V a tak isto Ctrl+C slúži na prerušenie procesu, treba použiť Ctrl+Shift+C
