## Insp3ct0r

Táto úloha bola iná než ostatné — neriešila sa cez terminál, ale cez prehliadač. Naučil som sa používať inšpektor (F12) na preskúmanie HTML, CSS a JavaScript súborov webovej stránky.

---

### Zadanie

Priložený bol odkaz na webovú stránku. Flag bol rozdelený na tri časti, každá skrytá v inom type súboru — HTML, CSS a JavaScript.

---

### Postup

**1. Inšpekcia HTML — karta Elements**

Po otvorení stránky som stlačil `F12` a prešiel na kartu **Elements**. V tele stránky `<body>`, v bloku s triedou `tabcontent` (záložka "How"), som v HTML komentári našiel prvú časť flagu.

![HTML flag v komentári](screenshoty/html.png)

HTML komentáre vyzerajú takto a bežný návštevník ich nevidí, ale v zdrojovom kóde sú:
```html
<!-- tu môže byť skrytý text -->
```

**2. Inšpekcia CSS — karta Sources**

Na karte **Sources** som otvoril súbor `mycss.css`. V komentároch na konci súboru bola druhá časť flagu.

![CSS flag v komentári](screenshoty/css.png)

**3. Inšpekcia JavaScriptu — karta Sources**

V tej istej karte **Sources** som otvoril `myjs.js` a našiel tretiu časť flagu.

![JS flag v komentári](screenshoty/js.png)

Po spojení všetkých troch častí som získal kompletný flag:
- HTML: `picoCTF{1/3`
- CSS: `2/3`
- JS: `3/3}`

---

### Čo som sa naučil

| Nástroj / Pojem | Čo znamená |
|-----------------|------------|
| `F12` / Inšpektor | Vstavaný nástroj prehliadača na analýzu webových stránok |
| Karta Elements | Zobrazuje HTML štruktúru vrátane skrytých komentárov |
| Karta Sources | Zobrazuje všetky súbory ktoré si prehliadač stiahol — CSS, JS, obrázky |
| HTML komentár | `<!-- text -->` — neviditeľný pre návštevníka, ale viditeľný v kóde |
| Kľúčové ponaučenie | Ak niečo nie je viditeľné na stránke, neznamená to že to tam nie je — zdrojový kód prezradí všetko |
