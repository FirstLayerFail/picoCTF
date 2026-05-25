## Obedient Cat

Úloha ma naučila sťahovať súbory priamo z internetu cez terminál a zobraziť ich obsah — bez prehliadača, bez klikania.

---

### Zadanie

Priložený bol odkaz na stiahnutie súboru s názvom `flag`. Úloha hovorila, že flag je v súbore priamo "na očiach" (plain sight).

---

### Postup

**1. Stiahnutie súboru**

```bash
wget https://challenge-files.picoctf.net/.../flag
```

`wget` stiahne súbor z URL priamo do aktuálneho priečinka. Hodí sa hlavne tam, kde nemáš grafické rozhranie — napríklad na vzdialených serveroch. Ak by si chcel súbor uložiť pod iným názvom, použiješ `-O`:

```bash
wget -O mojflag.txt https://...
```

**2. Zobrazenie obsahu**

```bash
cat flag
```

`cat` vypíše obsah súboru do terminálu. Funguje spoľahlivo na plain text — ak by bol súbor binárny (obrázok, zip, spustiteľný súbor), výstup by bol nezmysel. Preto je dobrým zvykom začínať príkazom `file`, ktorý ti povie čo súbor vlastne je:

```bash
file flag
# flag: ASCII text
```

---

### Reálny výstup z terminálu

```
tomas@Legion-mint:~$ wget https://challenge-files.picoctf.net/.../flag
--2026-05-23 15:52:40--  https://challenge-files.picoctf.net/.../flag
...
flag                100%[===================>]      34  --.-KB/s    za 0s
2026-05-23 15:52:41 (41,5 MB/s) - 'flag' uložené [34/34]

tomas@Legion-mint:~$ cat flag
picoCTF{skrytý_flag}
```

---

### Čo som sa naučil

| Príkaz / Pojem | Čo znamená |
|----------------|------------|
| `wget URL` | stiahne súbor z internetu priamo do aktuálneho priečinka |
| `cat súbor` | vypíše obsah textového súboru do terminálu |
| `file súbor` | ukáže typ súboru — dobrý prvý krok pri každej CTF úlohe |
| `man príkaz` | zobrazí manuál k príkazu — vyskočíš z neho cez `q` |
| `wget -O názov URL` | stiahne súbor pod vlastným názvom |
