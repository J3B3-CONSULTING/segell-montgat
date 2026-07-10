# Segell de Qualitat del Comerç de Montgat

Aplicació web (PWA) d'inspecció per a l'atorgament del **Segell de qualitat del comerç de Montgat**.
Funciona **sense connexió**, és **instal·lable** al mòbil i desa les dades al propi dispositiu.

## Què fa

- Llista de verificació de **49 ítems** en 6 blocs (A–F), classificats en **Obligatori / Estàndard / Premium**.
- Càlcul automàtic del veredicte segons l'article 6 dels criteris reguladors:
  **100 %** dels obligatoris + **≥ 70 %** estàndard → **ESTÀNDARD**; si a més **≥ 70 %** premium → **PREMIUM**.
- Genera **certificat/informe en Word**, **certificat en PDF** (via impressió del navegador) i **segell acreditatiu** amb els adhesius oficials.
- Base de dades local (al navegador): desar, exportar CSV i còpia de seguretat JSON.

## Ús en línia

Un cop publicada a GitHub Pages, l'adreça serà:

```
https://<usuari>.github.io/<repositori>/
```

Obre-la al mòbil i instal·la-la (Android: «Afegir a la pantalla d'inici» o botó «📲 Instal·lar app»; iPhone: Compartir › «Afegir a la pantalla d'inici»).

## Documentació i desplegament

Vegeu [`LLEGEIX-ME.md`](LLEGEIX-ME.md) per a les instruccions completes de publicació (GitHub Pages / Netlify) i de gestió de dades.

## Contingut

| Fitxer | Descripció |
|---|---|
| `index.html` | L'aplicació (inspecció + segell + informes) |
| `manifest.webmanifest` | Fa que sigui instal·lable com a app |
| `sw.js` | Service worker (memòria cau offline) |
| `icon-*.png`, `apple-touch-icon.png`, `favicon.png` | Icones |

---

Projecte J3B3 per a l'Ajuntament de Montgat.
