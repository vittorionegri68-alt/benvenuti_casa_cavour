# benvenuti.casa-cavour.com — aggiornamento rilevamento lingua

Questo pacchetto contiene SOLO gli aggiornamenti rispetto al repo già live:
`index.html` (versione italiana, aggiornata) ed `en.html` (nuova, versione inglese).
`favicon.svg` è invariato, incluso solo per completezza.

**Non è incluso `logo.png`**: è già presente nel tuo repo live, questi file lo
referenziano con lo stesso nome esatto (minuscolo) che hai già corretto tu.

## Cosa fa

- **index.html** (italiano, pagina principale): al caricamento controlla la
  lingua del telefono (`navigator.language`). Se non inizia per "it",
  reindirizza automaticamente a `/en.html`. In fondo alla pagina c'è comunque
  un link manuale "Read this page in English" per chi vuole passare a mano.
- **en.html** (inglese): stessa pagina, stesso funzionamento (meteo, mappa,
  WhatsApp, recensione Google, 21 profili Instagram), copy tradotta. In fondo
  un link "Leggi questa pagina in italiano" per tornare indietro.
- La scelta (automatica o manuale) viene ricordata con `localStorage`, così
  chi ha già scelto una lingua non viene rimbalzato ogni volta che riapre la
  pagina.
- Nessun loop possibile: solo `index.html` fa redirect automatico, `en.html`
  non reindirizza mai da sola, cambia lingua solo se l'utente clicca il link.

## Come aggiornare il repo

Sostituisci `index.html` con quello incluso qui, aggiungi `en.html` come file
nuovo nella root (stesso livello di `index.html`, `favicon.svg`, `logo.png`).
Nessun'altra modifica necessaria, nessun cambio di configurazione Vercel.

## Da verificare dopo il deploy

- Da un telefono con lingua italiana: apri il link del tag NFC, deve restare
  su `index.html` (nessun redirect)
- Cambia temporaneamente la lingua di sistema del telefono in inglese, riapri
  il link: deve reindirizzare automaticamente su `/en.html`
- Da `en.html`, controlla che meteo e data si carichino in inglese
- Controlla che i due link "Read this page in English" / "Leggi in italiano"
  funzionino in entrambe le direzioni
