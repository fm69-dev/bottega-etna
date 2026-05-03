# 🍊 La Bottega dell'Etna — Sito Web

Sito web di **Ortofrutta La Bottega dell'Etna**, Padova.  
Tecnologie: HTML5 · CSS3 · JavaScript vanilla · Netlify · Cloudinary

---

## 📁 Struttura del progetto

```
bottega-etna/
├── index.html          ← pagina principale
├── privacy.html        ← privacy policy GDPR
├── cookie.html         ← cookie policy
├── netlify.toml        ← configurazione Netlify + header sicurezza
├── .gitignore          ← file da escludere da Git
├── README.md           ← questo file
└── images/
    └── logo.png        ← logo (unica immagine nel repo)
```

> ⚡ **Tutte le altre immagini sono su Cloudinary** — non vanno nel repo.

---

## 🖼️ Come aggiungere nuove foto (Cloudinary)

### 1. Carica la foto su Cloudinary
- Vai su [cloudinary.com](https://cloudinary.com) → **Media Library**
- Trascina la foto oppure usa l'app mobile
- Cloudinary la ottimizza automaticamente

### 2. Copia l'URL della foto
- Clicca sulla foto → copia il link che termina in `.jpg` o `.webp`
- Esempio: `https://res.cloudinary.com/TUONOME/image/upload/v123/preparati06.jpg`

### 3. Aggiorna il sito
Apri `index.html` e cerca la sezione `// Random product images`:

```javascript
const cats = {
  preparati: [
    'https://res.cloudinary.com/TUONOME/image/upload/preparati01.jpg',
    'https://res.cloudinary.com/TUONOME/image/upload/preparati02.jpg',
    // ← aggiungi qui il nuovo URL
  ],
  ...
};
```

### 4. Commit e push → il sito si aggiorna da solo
```bash
git add index.html
git commit -m "Aggiunta foto preparati"
git push
```
Netlify rileva il push e pubblica in ~30 secondi. ✅

---

## 🚀 Deploy su Netlify (prima volta)

1. Vai su [netlify.com](https://netlify.com) → **Sign up** con GitHub
2. Click **"Add new site"** → **"Import an existing project"**
3. Scegli GitHub → seleziona **bottega-etna**
4. Impostazioni build:
   - **Branch:** `main`
   - **Build command:** *(lascia vuoto)*
   - **Publish directory:** `.`
5. Click **Deploy site**

### Aggiungere il tuo dominio personalizzato
- In Netlify: **Domain settings** → **Add custom domain**
- Digita `labottegadelletna.it`
- Segui le istruzioni per aggiornare i DNS presso il tuo registrar
- HTTPS viene attivato automaticamente (certificato SSL gratuito Let's Encrypt)

---

## ⏰ Orari (per aggiornamenti futuri)

| Periodo | Mattina | Pomeriggio | Note |
|---|---|---|---|
| **Invernale** (metà set – metà giu) | 7:30–13:00 | 15:30–19:30 | Chiuso pom: Lun · Mer |
| **Estivo** (metà giu – metà set) | 7:30–13:00 | 16:00–19:30 | Chiuso pom: Lun · Mer · Sab |
| **Domenica** | — | — | Sempre chiuso |

Per aggiornare gli orari nel sito: cerca `orari-time` in `index.html`.

---

## ✅ Checklist manutenzione

- [ ] Inserire **P.IVA** in `index.html` (footer) e `privacy.html`
- [ ] Inserire **email di contatto** in `privacy.html`
- [ ] Verificare orari stagionali ogni anno (metà giugno / metà settembre)
- [ ] Aggiornare recensioni Google periodicamente
- [ ] Ottimizzare nuove foto prima di caricarle (max 800×600px, JPG qualità 80%)

---

## 🔒 Sicurezza

Gli header HTTP di sicurezza sono configurati in `netlify.toml`:
- `Content-Security-Policy` — previene XSS e injection
- `Strict-Transport-Security` — forza HTTPS
- `X-Frame-Options` — previene clickjacking
- `X-Content-Type-Options` — previene MIME sniffing
- `Permissions-Policy` — disabilita API del browser non necessarie

---

## 📞 Contatti negozio

**Ortofrutta La Bottega dell'Etna**  
Via S. Camillo de Lellis 25, 35128 Padova  
Tel/WhatsApp: +39 351 962 2206  
Google Maps: [Apri](https://maps.google.com/?cid=16789773490855043561)
