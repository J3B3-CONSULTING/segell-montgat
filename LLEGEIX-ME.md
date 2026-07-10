# Segell de Qualitat del Comerç de Montgat — app instal·lable (PWA)

Aquesta carpeta és l'aplicació web completa, **instal·lable** i que **funciona sense connexió**.
Conté:

- `index.html` — l'aplicació (inspecció + segell + informes)
- `manifest.webmanifest` — fa que sigui instal·lable com una app
- `sw.js` — service worker (memòria cau offline)
- `icon-*.png`, `apple-touch-icon.png`, `favicon.png` — icones

## Per què cal “publicar-la” (i no obrir-la des dels Fitxers)

El desat de dades i la instal·lació com a app **només funcionen de forma fiable sobre una adreça web segura (https://)**, no obrint l'`.html` des de la memòria del telèfon (`file://`). Cada adreça té el seu propi magatzem de dades.

---

## Opció A — Publicar a internet (recomanat per a treball de camp)

### GitHub Pages (gratuït)
1. Crea un repositori a github.com (ex. `segell-montgat`).
2. Puja **tots els fitxers d'aquesta carpeta** (no la carpeta, sinó el seu contingut).
3. Settings → Pages → Branch: `main` / `/root` → Save.
4. Al cap d'un minut tindràs una URL `https://usuari.github.io/segell-montgat/`.

### Netlify Drop (encara més ràpid, gratuït)
1. Ves a https://app.netlify.com/drop
2. Arrossega-hi aquesta carpeta `app`.
3. Et dona una URL `https://...netlify.app` immediata amb https.

Un cop tens la URL:
- Obre-la al mòbil amb Chrome (Android) o Safari (iPhone).
- **Android:** apareixerà el botó “📲 Instal·lar app”, o menú ⋮ → “Afegir a la pantalla d'inici”.
- **iPhone:** botó Compartir → “Afegir a la pantalla d'inici”.
- A partir d'aquí funciona com una app, **offline**, i les dades es desen de forma estable en aquell dispositiu.

---

## Opció B — Provar-la al PC (localhost)

Obre un terminal en aquesta carpeta i executa:

```
python -m http.server 8080
```

Després obre al navegador del **mateix PC**: `http://localhost:8080/`
(`localhost` és context segur, així que la instal·lació i el service worker funcionen.)

> Nota: accedir-hi des del mòbil amb la IP del PC (`http://192.168.x.x`) **no** activa
> la instal·lació offline, perquè no és https. Per al mòbil, fes servir l'Opció A.

---

## Important sobre les dades

- Les inspeccions es desen **dins del navegador d'aquell dispositiu** (no al núvol, no es comparteixen entre aparells).
- Feu **còpies de seguretat periòdiques**: botó **“Còpia de seguretat completa (JSON)”** dins “Base de dades (repositori)”, i **“Exportar (CSV)”** per al full de càlcul. Deseu-les a la carpeta de l'ajuntament — aquest és l'arxiu definitiu.
- No useu mode incògnit (s'esborra en tancar) ni “esborrar dades de navegació” (esborra les inspeccions).

## Actualitzar l'app més endavant

Si canvieu `index.html`, editeu també `sw.js` i incrementeu la línia
`const CACHE = 'segell-montgat-v1';` (a `v2`, `v3`…) perquè els dispositius es refresquin.
