## Tab, Tab, Attack

Úloha ma naučila dopĺňanie názvov súborov a priečinkov pomocou klávesu Tab — nevyhnutný trik pri práci s dlhými názvami v termináli.

---

### Zadanie

Na stiahnutie bol priložený súbor `Addadshashanammu.zip`. Po rozbalení sa úloha dá vyriešiť na 11 stlačení klávesov — väčšinou pomocou Tab.

---

### Postup

**1. Stiahnutie a rozbalenie archívu**

```bash
wget https://challenge-files.picoctf.net/.../Addadshashanammu.zip
unzip Add<Tab>
```

Namiesto písania celého názvu stačí napísať začiatok a stlačiť Tab — terminál doplní zvyšok sám.

**2. Prechod cez hlbokú štruktúru priečinkov**

```bash
cd Add<Tab><Tab><Tab><Tab><Tab><Tab><Tab>
```

V každom podpriečinku bol len jeden ďalší priečinok, takže Tab vždy doplnil celý názov aj lomku automaticky. Výsledná cesta:

```
Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
```

**3. Spustenie programu**

```bash
ls
./fang<Tab>
```

`ls` ukázal obsah priečinka — spustiteľný súbor a jeho zdrojový kód `.c`. V Linuxe sa programy v aktuálnom priečinku spúšťajú s predponou `./` — bez nej terminál príkaz nenájde (z bezpečnostných dôvodov nehľadá v aktuálnom priečinku automaticky). Tab doplnil zvyšok názvu.

---

### Reálny výstup z terminálu

```
tomas@Legion-mint:~$ unzip Addadshashanammu.zip
Archive:  Addadshashanammu.zip
creating: Addadshashanammu/
creating: Addadshashanammu/Almurbalarammi/
...
creating: Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/
extracting: .../fang-of-haynekhtnamet.c
inflating: .../fang-of-haynekhtnamet

tomas@Legion-mint:~$ cd Addadshashanammu/Almurbalarammi/Ashalmimilkala/Assurnabitashpi/Maelkashishi/Onnissiralis/Ularradallaku/

tomas@Legion-mint:~/Addadshashanammu/...$ ls
fang-of-haynekhtnamet  fang-of-haynekhtnamet.c

tomas@Legion-mint:~/Addadshashanammu/...$ ./fang-of-haynekhtnamet
*ZAP!* picoCTF{skrytý_flag}
```

---

### Čo som sa naučil

| Príkaz / Pojem | Čo znamená |
|----------------|------------|
| `Tab` | doplní názov súboru alebo priečinka — ak je zhoda jednoznačná, doplní celý názov |
| `Tab Tab` | ak je viac možností, vypíše ich všetky |
| `./program` | spustí program v aktuálnom priečinku — `./` je povinné, Linux nehľadá v aktuálnom priečinku automaticky |
| `unzip súbor.zip` | rozbalí ZIP archív |
