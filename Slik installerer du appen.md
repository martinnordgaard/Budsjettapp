# Budsjett – slik gjør du den til en ekte app

Appen består nå av flere filer som hører sammen og **må ligge i samme mappe**:

- `index.html` – selve appen
- `manifest.webmanifest` – gjør den installerbar
- `sw.js` – gjør at den fungerer offline
- `icon-192.png`, `icon-512.png`, `icon-maskable-512.png`, `icon-180.png` – app-ikoner

`budsjett.html` er den gamle enkeltfila. Den fungerer fortsatt om du bare vil åpne den fra disk, men for å få en **installerbar app med varig lagring** bruker du `index.html` lagt ut på nett (se under).

---

## Hvorfor må den «på nett»?

En app som skal kunne installeres, kjøre offline og få *varig* lagring kan ikke åpnes rett fra disk (`file://`). Den må ligge på en HTTPS-adresse. Det er gratis og tar noen minutter. Du trenger ikke kunne kode.

---

## Enklest: Netlify Drop (ingen konto nødvendig for å teste)

1. Gå til **https://app.netlify.com/drop** i nettleseren.
2. Dra hele **Budsjettapp-mappa** inn i vinduet.
3. Du får umiddelbart en adresse, f.eks. `https://muntre-budsjett-123.netlify.app`.
4. Åpne adressen på telefonen og PC-en. Ferdig.

For en permanent adresse: opprett en gratis Netlify-konto før du drar inn mappa (samme steg, men adressen forsvinner ikke).

---

## Alternativ: GitHub Pages (permanent, gratis)

1. Opprett gratis konto på **github.com**.
2. Lag et nytt repository, f.eks. `budsjett`.
3. Last opp alle filene i mappa (dra dem inn i «Add file → Upload files»).
4. Gå til **Settings → Pages**, velg branch `main` og mappe `/root`, trykk **Save**.
5. Etter et par minutter ligger appen på `https://<brukernavn>.github.io/budsjett/`.

---

## Installere appen etter at den ligger på nett

**iPhone/iPad (Safari):** åpne adressen → trykk Del-knappen → **«Legg til på Hjem-skjerm»**.

**Android (Chrome):** åpne adressen → meny (⋮) → **«Installer app»** / «Legg til på startskjerm».

**PC (Chrome/Edge):** åpne adressen → klikk installer-ikonet ⊕ helt til høyre i adresselinjen → **«Installer»**.

Nå får du et app-ikon, den åpnes i eget vindu uten nettleserlinje, og fungerer offline.

---

## Om lagringen

- Data lagres **automatisk** på hver enhet – du trenger ikke eksportere for å beholde dem.
- Når appen er installert, ber den om **varig lagring**, som gjør at nettleseren ikke rydder bort dataene ved diskpress.
- Lagringen er per enhet og per adresse. Bruker du appen på både telefon og PC, er det to separate datasett – bruk **Eksporter/Importer** under «Mer» for å flytte data mellom dem.
- **Viktig:** Hvis du legger ut en *ny* adresse senere, starter den tom (data er knyttet til adressen). Hold deg til én fast adresse.

---

## Vil du ha ekte sky-synk mellom enheter?

Det krever en server/tjeneste og er et større prosjekt (og bryter med «gratis og privat»). Si fra hvis du vil utforske det – da er neste steg noe som Supabase eller Firebase, eller en enkel egen backend.
