# Registro Spese

App web progressiva (PWA) per tracciare spese ricorrenti e una tantum, con:

- **Scansione IA** di scontrini e screenshot (API Groq con la tua chiave, o Claude su desktop)
- **Calendario mensile esplorabile** — le ricorrenti compaiono alla data di addebito
- **Scadenzario** con promemoria delle prossime ricorrenze
- **Grafici** per categoria e andamento 6 mesi
- **Categorie personalizzate**
- **Salvataggio locale** sul dispositivo + export/import backup
- **Installabile su iPhone e Android** come vera app, funziona anche offline

## File del repository

| File | Scopo |
|---|---|
| `index.html` | L'app completa (HTML + CSS + JS in un solo file) |
| `manifest.webmanifest` | Manifest PWA (nome, icone, colori) |
| `sw.js` | Service worker per il funzionamento offline |
| `icon-192.png`, `icon-512.png`, `apple-touch-icon.png` | Icone dell'app |

## Pubblicazione su GitHub Pages (una volta sola, ~5 minuti)

1. Vai su [github.com](https://github.com) e accedi (o crea un account gratuito).
2. In alto a destra: **+ → New repository**. Nome: `registro-spese`. Visibilità: **Public** (necessario per Pages gratuito). **Create repository**.
3. Nella pagina del nuovo repo: **uploading an existing file** → trascina tutti i file di questa cartella → **Commit changes**.
4. Vai in **Settings → Pages** (menu a sinistra).
5. In "Build and deployment": Source = **Deploy from a branch**, Branch = **main** e cartella **/ (root)** → **Save**.
6. Dopo 1–2 minuti l'app è online su:
   `https://TUONOME.github.io/registro-spese/`

## Installazione su iPhone

1. Apri l'URL in **Safari**.
2. Tocca **Condividi → Aggiungi a Home**.
3. L'app compare in Home con la sua icona, si apre a schermo intero e conserva dati e chiave API sul telefono.

## Configurazione della scansione IA

1. Apri l'app → tab **⚙︎ Impostazioni**.
2. Incolla la tua chiave API Groq (gratuita su [console.groq.com](https://console.groq.com) → API Keys).
3. Salva. Da quel momento **📷 Scansiona** legge foto e screenshot direttamente dal telefono.

> La chiave resta salvata solo sul tuo dispositivo, non viene caricata su GitHub.

## Aggiornamenti futuri

Per aggiornare l'app: sostituisci `index.html` nel repo (Add file → Upload files → commit). Pages ripubblica da solo in un paio di minuti. Se modifichi anche `sw.js`, incrementa il numero in `const CACHE = "registro-spese-vX"` per forzare l'aggiornamento della cache sui dispositivi.

## Roadmap possibile (fase 2)

- Login con account e sincronizzazione tra dispositivi (Supabase, piano gratuito)
- Scansione multipla (più scontrini in un colpo)
- Export Excel delle spese
