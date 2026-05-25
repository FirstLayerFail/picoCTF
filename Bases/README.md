## Bases

Úloha o kódovaní dát. Naučil som sa rozpoznať Base64 a dekódovať ho priamo cez terminál — bez externých nástrojov.

---

### Zadanie

Dostal som reťazec znakov: `bDNhcm5fdGgzX3IwcDM1`
Nápoveda hovorila, že to má niečo spoločné so "základmi" (bases).
Cieľom bolo reťazec dekódovať a odovzdať vo formáte `picoCTF{výsledok}`.

---

### Postup

**1. Rozpoznanie Base64**

Text zakódovaný v Base64 sa dá rozpoznať podľa týchto znakov:
- obsahuje zmes malých písmen, veľkých písmen a čísel
- neobsahuje špeciálne znaky
- občas končí znakom `=` alebo `==` (padding) — v tomto prípade nebol

Base64 využíva 64 znakov (A-Z, a-z, 0-9, + a /) na reprezentáciu binárnych dát v textovej forme.

**2. Dekódovanie**

```bash
echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
```

`echo` pošle reťazec na výstup, `|` ho presmeruje do `base64 -d`, ktorý ho dekóduje (`-d` = decode). Ak by som chcel naopak niečo zakódovať:

```bash
echo "ahoj" | base64
```

---

### Reálny výstup z terminálu

```
tomas@Legion-mint:~$ echo "bDNhcm5fdGgzX3IwcDM1" | base64 -d
skrytý_flagtomas@Legion-mint:~$
```

*(výsledok sa vypíše priamo za sebou bez nového riadku — normálne správanie)*

---

### Čo som sa naučil

| Príkaz / Pojem | Čo znamená |
|----------------|------------|
| `base64 -d` | dekóduje Base64 reťazec |
| `base64` (bez -d) | zakóduje text do Base64 |
| `echo "text" \| príkaz` | pošle text priamo do iného príkazu bez súboru |
| Kódovanie vs šifrovanie | Base64 nie je šifra — každý to vie dekódovať. Slúži na bezpečný prenos binárnych dát v textových systémoch |
