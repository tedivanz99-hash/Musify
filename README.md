# MUSIFY — versione completa PWA (build personale)

## Incluso
- Interfaccia responsive desktop/iPhone, tema scuro minimal.
- Ricerca video musicali YouTube tramite YouTube Data API v3.
- Riproduzione con YouTube IFrame Player ufficiale.
- Preferiti, playlist multiple (crea/rinomina/elimina), cronologia.
- Coda di riproduzione, brano precedente/successivo, shuffle e play/pause.
- Persistenza locale e funzione di esportazione libreria JSON.
- Manifest PWA, service worker e icone.

## Avvio e pubblicazione
Questa cartella è una PWA statica. Per funzionare come app installabile va pubblicata su un hosting HTTPS (GitHub Pages, Netlify, Cloudflare Pages o hosting equivalente).
1. Crea un progetto in https://console.cloud.google.com/
2. Abilita **YouTube Data API v3** e crea una API key.
3. Restringi la chiave all'API YouTube Data API v3 e, se possibile, ai domini autorizzati.
4. Pubblica tutti i file mantenendo la struttura delle cartelle.
5. Apri l'indirizzo pubblicato su iPhone con Safari.
6. Apri Impostazioni nell'app e inserisci la API key.
7. Safari → Condividi → Aggiungi alla schermata Home.

Per test locale usa un server HTTP (es. `python -m http.server 8000`) e non `file://`.

## Limiti e trasparenza
- La chiave API inserita in questa build personale è memorizzata nel local storage del browser. Non è adatta a un servizio pubblico multiutente: per quello occorre un backend/proxy e gestione sicura delle credenziali.
- La ricerca può consumare quota API Google/YouTube.
- La riproduzione avviene nel player YouTube ufficiale, che può mostrare pubblicità e non consente di rimuovere i controlli/branding.
- Le regole YouTube API non consentono a un'app di offrire o promuovere la riproduzione in background. Quindi questa PWA non garantisce audio con schermo spento o app in background.
- Per ascolto in background serve un provider musicale che lo autorizzi espressamente e offra API/SDK adatti; non è una funzione che si possa aggiungere aggirando il player YouTube.
- Dati salvati localmente su un singolo browser/dispositivo; nessun account o sincronizzazione cloud.
- Prima di una distribuzione pubblica occorre verificare le YouTube API Services Terms, policy, privacy e requisiti di branding.

## Nota
È una build completa lato front-end per uso personale, non un'app già pubblicata su App Store né un servizio già ospitato. La pubblicazione HTTPS e la configurazione della chiave API restano passaggi esterni.
