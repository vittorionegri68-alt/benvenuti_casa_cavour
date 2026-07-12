# benvenuti.casa-cavour.com

Pagina statica per il tag NFC di Casa Cavour: CTA recensione Google in cima
e sempre visibile, più meteo, mappa, contatti e consigli sul territorio.
Nessun framework, nessuna build step, stesso schema di romagna-links.

## Prima del primo deploy

1. **Manca `Logo.png`**. Il file `index.html` lo referenzia (`<img src="Logo.png">`)
   ma non è incluso in questo zip: non avendolo a disposizione non l'ho potuto
   generare io. Copia lo stesso `Logo.png` già usato nel repo `romagna-links`
   nella ROOT di questo repo, stesso nome esatto (case-sensitive).

2. **Verifica l'handle Instagram corretto in autonomia**: nella sezione "Amici
   di Casa Cavour" ho scritto `@museo_interreligioso`, correggendo quello che
   sembrava un refuso rispetto a "museo_inerreligioso" scritto in origine.
   Non è stato confermato esplicitamente come gli altri tre handle corretti
   in sessione. Controlla su Instagram che l'account esista con questo nome
   prima di andare live.

3. Se cambi anche il numero WhatsApp o l'indirizzo, ricorda che sono hardcoded
   nell'HTML (cerca `wa.me` e le coordinate della mappa).

## Deploy su Vercel

1. Crea un nuovo repo GitHub, carica il contenuto di questo zip nella root
   (dopo aver aggiunto `Logo.png`, vedi sopra)
2. Importa il repo su Vercel, nessun framework da selezionare (static),
   nessun build command
3. Aggiungi il dominio custom `benvenuti.casa-cavour.com` nelle impostazioni
   del progetto Vercel
4. Sul DNS del dominio `casa-cavour.com`, aggiungi il record CNAME che
   Vercel indica per il sottodominio `benvenuti` (stessa procedura già
   fatta per `links.casa-cavour.com`)

## Dopo il deploy

- Apri `https://benvenuti.casa-cavour.com` da telefono e verifica:
  - Il bottone recensione Google in alto e la barra fissa in basso funzionino
    entrambi (portano a `g.page/r/CX29I9RlMT27EBM/review`)
  - Il meteo si carichi (dipende da una chiamata a `open-meteo.com`, nessuna
    chiave richiesta)
  - Tutti i 21 link Instagram aprano il profilo giusto (controllo veloce a
    campione, non serve aprirli tutti)
- Solo a questo punto programma il tag NFC con l'URL finale.

## File inclusi

- `index.html` — la pagina, completa di CSS e JS inline
- `favicon.svg` — stesso favicon già creato per gli altri siti Casa Cavour
  (monogramma C, oro su crema)
