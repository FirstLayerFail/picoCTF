## Super SSH

Úloha ma naučila pripojiť sa na vzdialený server cez SSH a pracovať s neštandardným portom.

---

### Zadanie

- Server: `titan.picoctf.net`
- Port: `61427`
- Meno: `ctf-player`
- Heslo: `f3b61b38`

Cieľom bolo prihlásiť sa na server a získať flag.

---

### Postup

**1. Pripojenie na server**

```bash
ssh ctf-player@titan.picoctf.net -p 61427
```

Štandardný SSH port je `22` — ak server beží na inom porte, musím ho zadať cez `-p`. Bez toho sa pripojenie nepodarí.

**2. Overenie servera (fingerprint)**

Pri prvom pripojení na server sa terminál opýta či mu dôverujem:

```
The authenticity of host '[titan.picoctf.net]:61427' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
Are you sure you want to continue connecting (yes/no/[fingerprint])?
```

Každý SSH server má unikátny kryptografický kľúč. `ED25519` je typ šifrovacieho algoritmu, `SHA256:...` je jeho skrátený odtlačok (fingerprint) — slúži na overenie že sa pripájam na správny server. Zadal som `yes`.

**3. Zadanie hesla**

Pri písaní hesla sa na obrazovke nič nezobrazuje — žiadne hviezdičky, žiadne bodky. Je to bezpečnostná funkcia Linuxu, nie chyba. Stačí vložiť heslo a stlačiť `Enter`.

> **Poznámka:** V termináli nefunguje `Ctrl+V` — na vkladanie slúži `Ctrl+Shift+V`. Podobne `Ctrl+C` prerušuje proces, nie kopíruje — na kopírovanie slúži `Ctrl+Shift+C`.

**4. Získanie flagu**

Server ma po prihlásení automaticky privítal, vypísal flag a odpojil ma.

---

### Reálny výstup z terminálu

```
tomas@Legion-mint:~$ ssh ctf-player@titan.picoctf.net -p 61427
The authenticity of host '[titan.picoctf.net]:61427 ([3.139.174.234]:61427)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:61427' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{skrytý_flag}
Connection to titan.picoctf.net closed.
```

---

### Čo som sa naučil

| Príkaz / Pojem | Čo znamená |
|----------------|------------|
| `ssh user@server` | pripojí sa na vzdialený server |
| `-p 61427` | určuje port — povinné ak server nebeží na predvolenom porte 22 |
| Fingerprint | skrátený odtlačok kľúča servera — slúži na overenie identity servera |
| ED25519 | typ šifrovacieho algoritmu použitého na generovanie kľúča |
| Skryté heslo | Linux nezobrazuje zadávanie hesla — bezpečnostná funkcia, nie chyba |
| `Ctrl+Shift+V` | vkladanie v termináli (nie `Ctrl+V`) |
| `Ctrl+Shift+C` | kopírovanie v termináli (nie `Ctrl+C`) |
