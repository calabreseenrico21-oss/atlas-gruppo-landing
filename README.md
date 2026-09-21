# Atlas SRL — Landing page di gruppo

Sito statico a file singolo (`index.html`, autonomo, nessuna dipendenza, nessun build).
Pensata per essere linkata da un post LinkedIn: presenta Atlas SRL e i suoi tre business
(Parking Beach, Atlas Rent a Car, Atlas Auto Hub).

## Pubblicare su GitHub Pages (gratis)

1. Crea una nuova repository su GitHub, ad es. `atlas-gruppo-landing` (pubblica o privata).
2. Carica il contenuto di questa cartella nella root della repo:
   `index.html`, `favicon.svg`, `CNAME`, `.nojekyll`.
3. Repo → **Settings → Pages** → *Source*: `Deploy from a branch` → branch `main`,
   folder `/ (root)` → Save.

Da riga di comando, dentro questa cartella:

```bash
git init
git add .
git commit -m "Landing page gruppo Atlas SRL"
git branch -M main
git remote add origin https://github.com/<utente>/atlas-gruppo-landing.git
git push -u origin main
```

## Dominio personalizzato — atlassrl2026.com

Il file `CNAME` è già pronto con `atlassrl2026.com`. Serve solo configurare il DNS
nel pannello dove hai comprato il dominio (Google Domains / Google Workspace):

1. Vai su **Settings → Pages → Custom domain** nella repo e conferma `atlassrl2026.com`
   (GitHub la scrive già leggendo il file `CNAME`, ma va confermata da interfaccia
   la prima volta).
2. Nel pannello DNS del dominio, aggiungi questi record:
   - **Record A** (dominio nudo `atlassrl2026.com`) verso i 4 IP di GitHub Pages:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **Record CNAME** per `www` → `<utente>.github.io`
     (solo se vuoi che funzioni anche `www.atlassrl2026.com`).
3. Attiva **Enforce HTTPS** in Settings → Pages non appena il certificato è pronto
   (di solito entro qualche minuto/ora dalla propagazione DNS).

Dopo la propagazione (di solito pochi minuti, a volte fino a 24h), il sito è live su
`https://atlassrl2026.com` — costo zero, nessun hosting a pagamento.

## Prima di condividere il link

- Verifica in anteprima locale aprendo `index.html` nel browser.
- I link ai tre siti (`parkingbeach.it`, `atlasrentacar.it`, `atlasautohub.it`) sono
  già puntati ai domini reali.
- I dati societari nel footer/sezione contatti sono presi da `chi-siamo.ejs` del sito
  Atlas Rent a Car: verificane l'aggiornamento se qualcosa è cambiato nel frattempo.
