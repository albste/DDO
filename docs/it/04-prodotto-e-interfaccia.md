# Prodotto e Interfaccia del DDO

### Bozza di sito pubblico e app: cosa contengono, cosa mostrano, cosa si può consultare

di **albste** · 17 ott 2026 · Versione 0.1 · Licenza: CC BY-SA 4.0

Documento di accompagnamento al Whitepaper e alla Specifica Tecnica del DDO. Descrive il prodotto visto dal cittadino: le sezioni, il ciclo di vita di una proposta, la mappa dell'economia dello Stato, la scheda che l'elettore vede prima di votare, le fazioni e i commenti. È una proposta di progetto, non una specifica grafica definitiva: i parametri indicati come «aperti» sono lasciati al voto fondativo di ogni pilota. Vale la stessa avvertenza della Specifica Tecnica: nulla qui va usato per votazioni vincolanti prima di revisione e audit indipendenti.

## 1. Perché serve questo documento

Il Whitepaper dice come si decide e la Specifica Tecnica dice come si protegge il voto. Mancava la risposta a una domanda più semplice: dove si trova tutto questo? In DDO ogni passaggio, dalla proposta all'esito, nasce e si consulta nello stesso posto. Se una decisione non è visibile lì, per il sistema non esiste.

Tre principi guidano il resto del documento, e discendono dai principi del Whitepaper (in particolare «Verificabilità con privacy» e «Aperto per progetto»):

1. **Una sola fonte.** Sito e app mostrano gli stessi dati, presi dagli stessi registri pubblici. Nessuna informazione ufficiale esiste solo dentro un prodotto.
2. **Ogni decisione ha un effetto leggibile.** Una proposta che sposta denaro deve mostrare, in modo navigabile, cosa cambia nei conti dello Stato prima e dopo.
3. **Chi vota vede il quadro intero.** Posizioni in campo, numeri, rischi, modifiche e dibattito sono presentati con lo stesso formato per ogni proposta, senza che nessuno possa scegliere cosa mettere in primo piano.

## 2. Due prodotti, le stesse funzioni

DDO ha due prodotti separati che fanno le stesse cose.

- **Sito pubblico.** Si apre da qualsiasi browser, senza account. Chiunque, anche chi non è cittadino abilitato, può leggere tutto: proposte, fazioni, commenti, esiti, mappa economica, registri.
- **App del cittadino.** È il portafoglio della Specifica Tecnica (sezione 4) con l'interfaccia completa. Custodisce le chiavi in hardware sicuro ed esegue le azioni che richiedono un'identità.

Le azioni (proporre, sostenere, aderire a una fazione, commentare, votare) richiedono una prova di abilitazione. Sul sito la prova arriva dal portafoglio del cittadino, tramite un collegamento con codice QR o link diretto verso l'app, così le chiavi restano sul dispositivo. Le cabine eseguono lo stesso client.

| Funzione | Sito pubblico | App del cittadino |
| --- | --- | --- |
| Leggere proposte, fazioni, commenti, esiti | Sì, senza accesso | Sì |
| Navigare la mappa economica dello Stato | Sì, senza accesso | Sì |
| Verificare registri, ricevute e spogli | Sì | Sì |
| Proporre, sostenere, aderire a una fazione | Con portafoglio collegato | Sì |
| Commentare (anche in forma anonima) | Con portafoglio collegato | Sì |
| Votare | Con portafoglio collegato | Sì |
| Custodia delle chiavi | Mai nel sito | Hardware sicuro del dispositivo |
| Notifiche e promemoria di scadenza | Facoltative | Sì |
| Uso senza connessione per iscrizione e voto assistito | No | Tramite cabine |

I due prodotti condividono un nucleo comune (formati dei dati, interfaccia di lettura pubblica, componenti dell'interfaccia) e sono entrambi a codice aperto. L'interfaccia di lettura è pubblica e documentata, così chiunque può costruire un terzo client o un cruscotto indipendente. Se sito e app mostrassero cose diverse, la verifica sarebbe lasciata a chi li gestisce, ed è proprio ciò che DDO vuole evitare.

## 3. Mappa delle sezioni

Stessa struttura in entrambi i prodotti.

| Sezione | Contenuto |
| --- | --- |
| **Proposte** | Tutte le proposte per stato (bozza, in raccolta sostegno, in deliberazione, in voto, chiusa, in blocco). Ricerca e filtri per ambito, territorio, tipo di legge e impatto economico |
| **Votazioni** | Le votazioni aperte e quelle in arrivo che riguardano il cittadino, con scadenze |
| **Esiti** | Risultati, prove di verifica, versione della legge approvata e fine del periodo di blocco |
| **Economia dello Stato** | La mappa navigabile di entrate, debiti, patrimonio e destinazioni, con la sua storia (sezione 5) |
| **Registri** | Schede pubblicate, punti di controllo, versioni delle regole di punteggio, tracce di audit, azioni di mediatori e operatori |
| **Il mio spazio** | Credenziali, ambiti e fasce di peso, adesioni, commenti, ricevute dei propri voti, accessi ai propri dati da parte di autorità (sezione 6 del Whitepaper) |
| **Regole** | Soglie, finestre di voto, periodi di blocco, tetto di peso e Carta dei Diritti Fondamentali, in versione corrente e storica |
| **Mediatori e operatori** | Chi è in carica, mandato, scadenza e registro delle azioni |

## 4. Il ciclo di vita di una proposta

Ogni proposta passa per le stesse fasi, e ogni fase lascia una traccia consultabile. Le fasi riprendono il ciclo del Whitepaper (sezione 3) e rendono esplicite la deliberazione e il monitoraggio dopo l'esito.

| Fase | Cosa succede | Cosa si può consultare |
| --- | --- | --- |
| **1. Bozza** | Un cittadino scrive la proposta, indica ambito e tipo di legge e, se serve, la modifica alla mappa economica | Testo, versioni, autore (o mediatore proponente) |
| **2. Raccolta del sostegno** | La proposta raccoglie sostegni fino alla soglia del suo tipo di legge | Numero di sostegni, soglia, tempo rimasto |
| **3. Verifica di impatto** | Controlli automatici sulla mappa economica, su conflitti con leggi in blocco e con la Carta. Chiunque può segnalare un impatto non dichiarato | Esito dei controlli, segnalazioni e risposte |
| **4. Deliberazione** | Periodo obbligatorio in cui nascono le fazioni, si aderisce, si commenta, si emenda | Fazioni, adesioni, commenti, rischi, emendamenti |
| **5. Voto** | Finestra di voto con la scheda descritta nella sezione 7 | La scheda, la propria ricevuta, il tempo rimasto |
| **6. Spoglio ed esito** | Risultato e prove pubblicati alla chiusura | Risultato, prove di spoglio, registro |
| **7. Blocco ed esecuzione** | La legge è in blocco; se ha effetti economici, i movimenti reali si confrontano con quelli approvati | Scadenza del blocco, mappa economica «approvato contro effettivo» |

La raccolta del sostegno e la deliberazione sono due cose distinte. La prima decide se una proposta merita di essere discussa, la seconda se è stata discussa abbastanza da essere votata. La durata minima della deliberazione è un parametro del voto fondativo, come richiede il Whitepaper (sezione 10, «Populismo e manipolazione»).

## 5. Economia dello Stato: la mappa navigabile

### 5.1 Cosa mostra

La sezione **Economia dello Stato** è una mappa grande, scorribile e ingrandibile, che rappresenta tutto il patrimonio pubblico e i suoi movimenti. Ha quattro tipi di elemento.

- **Entrate.** Imposte, tasse, contributi, rendite, trasferimenti ricevuti.
- **Patrimonio.** Fondi, conti, immobili, partecipazioni, riserve.
- **Debiti.** Creditore, importo, tasso, scadenza.
- **Destinazioni.** Dove vanno i soldi: ambiti (sanità, istruzione, infrastrutture, ...), enti, territori, progetti.

Gli elementi sono collegati da **flussi**, cioè importo, periodicità e base giuridica. Ogni flusso rimanda alla legge o alla proposta che lo ha stabilito. Per questo, dalla mappa si risale sempre alla decisione e, dalla decisione, a chi l'ha votata e con quale esito.

### 5.2 Come si naviga

- **Zoom per livelli.** Si parte dalla vista d'insieme dello Stato (poche grandi voci), si scende negli ambiti, poi negli enti, poi nelle singole voci e nei progetti. A ogni livello i totali tornano con quelli del livello superiore.
- **Spostamento libero.** Trascinamento e zoom con tocco, mouse o tastiera, con una minimappa per non perdersi.
- **Tempo.** Un cursore temporale mostra la mappa a una data qualsiasi e permette di confrontare due date.
- **Filtri e ricerca.** Per ambito, territorio, ente, creditore, importo, proposta o legge.
- **Percorsi.** Selezionando un flusso si evidenzia il percorso a monte (da dove arrivano i soldi) e a valle (dove vanno).
- **Tre viste dei valori.** *Approvato* (deciso dai cittadini), *effettivo* (osservato dai dati pubblicati dagli enti) e *proposto* (nelle proposte in corso). Gli scostamenti tra approvato ed effettivo sono evidenziati.
- **Vista tabella.** Ogni schermata ha l'equivalente in tabella, per accessibilità, lettori di schermo e confronto. I dati si scaricano in formato aperto.

### 5.3 Come è fatta e chi la aggiorna

La mappa è un insieme di dati versionato. **Nessuno la modifica direttamente**, nemmeno gli operatori. Esistono solo due modi in cui cambia.

1. **Decisione dei cittadini.** Una proposta approvata applica la propria modifica alla mappa (sezione 6). La nuova versione fa riferimento alla proposta e al registro del voto.
2. **Dati osservati.** Gli enti pubblici pubblicano i movimenti reali con firma digitale. Questi aggiornano la vista *effettivo* ma non modificano mai *approvato*. Se i due divergono, la divergenza è pubblica e resta visibile.

Le versioni e i punti di controllo della mappa stanno nel registro di trasparenza (Specifica Tecnica, sezione 3), come le altre registrazioni. Sono dati pubblici e senza dati personali, quindi non pongono problemi di cancellazione.

**Controlli di coerenza.** Ogni versione deve rispettare regole verificabili da chiunque: le uscite non superano le entrate più la variazione dei saldi; un saldo non diventa negativo senza essere dichiarato come nuovo debito; i totali di ogni livello corrispondono alla somma dei livelli sotto; nessun flusso viola una legge in periodo di blocco.

**Nei piloti.** Un pilota di comunità non ha un bilancio statale. La mappa copre i fondi della comunità stessa (quote, contributi, beni comuni), con la stessa struttura. Si passa ai dati di un comune o di uno Stato solo se l'ente li pubblica.

## 6. Proposte che muovono denaro

**Regola.** Una proposta che richiede una destinazione di denaro o uno spostamento di fondi deve includere anche la proposta di modifica alla mappa economica. Senza di essa non può uscire dalla fase di bozza.

### 6.1 La modifica alla mappa

Chi scrive la proposta usa lo stesso editor della mappa e indica le modifiche: nuovo flusso, flusso ridotto o eliminato, fondo ridotto, nuovo debito, nuova entrata, aumento di un'imposta. Il sistema calcola e mostra:

- la mappa **prima** e **dopo**, con le sole parti modificate evidenziate;
- l'effetto sui totali: saldo, debito, spesa per ambito, impatto per territorio;
- la **copertura**: da dove vengono i soldi. Ogni spesa deve indicare una fonte (riduzione di un'altra voce, nuova entrata, uso di riserve o nuovo debito) e la fonte è mostrata alla stessa altezza della spesa, mai nascosta;
- i vincoli violati, se ce ne sono. Una proposta che li viola non passa al sostegno.

### 6.2 Impatti non dichiarati

Una proposta può avere effetti economici che l'autore non ha dichiarato, per errore o per scelta. Per limitare questo caso:

- chi redige la proposta indica se muove denaro; se dichiara di no, la modifica alla mappa è vuota;
- in fase di verifica di impatto (fase 3) qualsiasi cittadino abilitato può segnalare un impatto non dichiarato, allegando una stima;
- la segnalazione e la risposta dell'autore sono pubbliche. Se una segnalazione è accolta, la proposta torna in bozza per integrare la modifica alla mappa; il criterio di accoglimento è una regola votata in anticipo, non una decisione discrezionale di un operatore.

### 6.3 Dopo l'approvazione

Se la proposta passa, la sua modifica alla mappa diventa una nuova versione di **approvato**. Quando l'ente esecutore pubblica i movimenti reali, la vista **effettivo** si confronta con essa. Uno scostamento oltre una soglia stabilita crea una segnalazione pubblica, collegata alla proposta. Una proposta che non rispetta i propri limiti economici si vede.

## 7. La scheda di voto: cosa vede chi vota

Quando una proposta supera la soglia di sostegno e la deliberazione, chi è abilitato a votarla trova la stessa **scheda informativa**, con lo stesso formato per ogni proposta. Non esiste un modo di presentarla in modo più favorevole.

```text
┌──────────────────────────────────────────────────────────────┐
│ PROPOSTA  #482 · Territoriale · Ambito: Trasporti            │
│ In voto fino al 24 nov · Blocco previsto: 2 anni             │
├──────────────────────────────────────────────────────────────┤
│ 1. SINTESI             Cosa cambia, in poche righe  [Testo]  │
│ 2. FAZIONI             Fazione A   312 aderenti              │
│                        Fazione B   187 aderenti              │
│                        Fazione C    64 aderenti              │
│                        Nessuna adesione dichiarata  1.040    │
│ 3. ECONOMIA            Prima/Dopo sulla mappa  [Apri mappa]  │
│                        Spesa 4,2 M · Copertura: riduzione    │
│                        voce X (2,0 M) + nuovo debito (2,2 M) │
│ 4. COSA SI MODIFICA    Leggi/regole/flussi toccati           │
│ 5. RISCHI              Dichiarati · Segnalati · Controlli    │
│ 6. COMMENTI            Per fazione · Nominativi o anonimi    │
├──────────────────────────────────────────────────────────────┤
│ [ VOTA ]   Si può rivotare fino alla chiusura (conta l'ultimo)│
└──────────────────────────────────────────────────────────────┘
```

### 7.1 Fazioni e numero di aderenti

Una **fazione** è una posizione su una proposta, con un nome e una breve dichiarazione. Esistono fazioni a favore, contrarie, a favore con modifiche e alternative.

- La fazione dell'autore nasce con la proposta. Qualsiasi cittadino abilitato può proporne un'altra durante la deliberazione; una fazione compare nella scheda solo con un numero minimo di aderenti (parametro aperto), per evitare la proliferazione di fazioni vuote.
- Ogni cittadino abilitato può aderire a **una sola fazione** per proposta e cambiarla fino alla chiusura della deliberazione.
- L'**adesione non è il voto**. È una dichiarazione di posizione. Non lo vincola, non lo rivela e non anticipa lo spoglio. La scheda lo dice esplicitamente («aderenti dichiarati, non voti»).
- Il numero di aderenti è pubblico, ma **non chi sono**. L'adesione usa la stessa prova di abilitazione e lo stesso nullifier per proposta del voto (Specifica Tecnica, sezione 5): un'adesione per persona, non collegabile all'identità né alle adesioni su altre proposte.
- Le fazioni compaiono in ordine casuale per ogni visitatore, non in ordine di dimensione.
- Il numero mostrato è un conteggio di persone. Le fasce di peso del voto ponderato non compaiono nelle adesioni, per non ridurre la privacy del voto.
- Ogni fazione può allegare un **emendamento**, cioè una variante del testo o della modifica economica. L'autore può accoglierlo; altrimenti diventa una proposta concorrente con la sua scheda (domanda aperta nella sezione 11).

### 7.2 Proposta di spostamento economico

La parte «Economia» della scheda è la modifica alla mappa della sezione 6, in forma di confronto prima/dopo. Chi vota può aprirla sulla mappa e navigarla a ogni livello. Se la fazione ha un emendamento economico, la mappa mostra anche la variante.

### 7.3 Rischi

I rischi sono raccolti da tre fonti, distinte per origine:

- **dichiarati dall'autore**, obbligatori, con probabilità e impatto stimati e le mitigazioni;
- **segnalati dai cittadini**, quelli aggiunti da fazioni o singoli durante la deliberazione, con la loro stima;
- **controlli automatici**: violazioni di vincoli, copertura debole, effetti sul debito, concentrazione territoriale della spesa.

Una scheda con la sezione Rischi vuota lo dice (nessun rischio dichiarato né segnalato); non nasconde la sezione.

### 7.4 Cosa si modifica

L'elenco preciso di ciò che l'approvazione cambia: testo di legge nuovo o modificato (con confronto), regole toccate, flussi della mappa economica, leggi correlate e, se ci sono, i periodi di blocco coinvolti. È la stessa informazione dell'elenco delle modifiche in una revisione di codice: chi vota sa cosa cambia davvero.

### 7.5 Commenti per fazione

I commenti sono mostrati **suddivisi per fazione**, così si leggono gli argomenti di ciascuna posizione. Esiste anche la vista cronologica complessiva. Sono previste risposte, segnalazioni e la possibilità di ordinare per data o per rilevanza dichiarata dai lettori.

## 8. Commenti, anonimato e moderazione

**Chi può commentare.** I cittadini abilitati a votare la proposta. Chi non è abilitato legge ma non scrive, così il dibattito riflette chi è coinvolto e si riduce il rischio di invasioni dall'esterno (domanda aperta nella sezione 11).

**Due modalità, a scelta di chi scrive.**

- **Con nome.** Il commento è firmato con un nome pubblico scelto dal cittadino.
- **Anonimo.** Il commento non è collegato a nessuna identità. Il portafoglio dimostra, con prova a conoscenza zero, che l'autore è abilitato e produce un'etichetta per proposta. Dentro la stessa proposta compare come «Anonimo 17», coerente tra i suoi commenti; su un'altra proposta è un'etichetta diversa e nessuno può collegare le due.

In entrambe le modalità il commento porta l'etichetta della fazione di chi lo scrive, se ha aderito. Un commento anonimo non rivela né il nome né altro oltre alla fazione e alla proposta.

**Limiti e abusi.** L'anonimato non deve trasformarsi in uno strumento di abuso né di manipolazione.

- Un'etichetta anonima è unica per persona e per proposta, quindi si può limitare il ritmo dei commenti e bloccare un'etichetta solo su quella proposta, senza risalire alla persona.
- La moderazione agisce su segnalazione. Un commento rimosso lascia sempre una traccia con il motivo (illegale, fuori tema, offesa personale), non sparisce in silenzio, e la rimozione può essere contestata. Chi decide è un gruppo estratto a sorte tra cittadini abilitati, non un operatore; l'applicazione segue l'Articolo 4 della Carta (giusto processo).
- Nessun operatore, e nessuna autorità, può risalire all'autore di un commento anonimo: il sistema non conserva quel collegamento, quindi non c'è nulla da consegnare.

**Dove sono i commenti.** I commenti possono contenere dati personali scritti dal loro autore, quindi il testo sta fuori dal registro, in archivi convenzionali cifrati. Nel registro vanno solo impegni crittografici (hash), così modifiche e cancellazioni sono dimostrabili senza che il registro contenga i testi (Specifica Tecnica, sezione 10).

**Piccoli gruppi.** In un territorio o in una fazione molto piccoli, il solo conteggio può far riconoscere le persone. Sotto un numero minimo (parametro aperto) il sistema mostra un intervallo anziché il numero esatto e non mostra la fazione accanto a un commento anonimo.

## 9. Cosa sta nel registro e cosa fuori

| Dato | Dove sta | Perché |
| --- | --- | --- |
| Testo delle proposte e delle versioni (hash e riferimento) | Registro | Provare cosa fu messo ai voti |
| Modifiche alla mappa economica e sue versioni | Registro | Dati pubblici, senza dati personali |
| Definizione delle fazioni, conteggi di adesione e nullifier | Registro | Conteggio verificabile, nessuna identità |
| Schede, esiti e prove di spoglio | Registro | Verificabilità universale |
| Impegni crittografici dei commenti e delle rimozioni | Registro | Provare modifiche e cancellazioni |
| Testo dei commenti | Archivio fuori registro, cifrato | Possono contenere dati personali |
| Dati osservati dagli enti (movimenti effettivi) | Registro, con firma dell'ente | Confronto pubblico tra approvato ed effettivo |
| Indici di ricerca, miniature, notifiche | Fuori registro | Servizio di comodo, ricostruibile dai registri |

## 10. Rischi

| Rischio | Perché conta | Mitigazione proposta |
| --- | --- | --- |
| Mappa piena di errori o dati falsi | Le decisioni si basano su numeri sbagliati | Dati firmati dagli enti, confronto approvato/effettivo, segnalazioni pubbliche, audit |
| Mappa troppo complessa | Troppi dettagli scoraggiano chi vota | Zoom per livelli, sintesi per ogni livello, vista tabella, totali sempre coerenti |
| Impatti economici nascosti nella proposta | Spese non dichiarate | Segnalazione di impatto, ritorno in bozza, confronto con i movimenti reali |
| I conteggi di adesione condizionano il voto | Effetto gregge: ci si accoda alla fazione più numerosa | Ordine casuale delle fazioni, dichiarazione esplicita «non voti», conteggi mostrati come numeri e non come percentuali |
| Brigading e coordinamento dall'esterno | Commenti organizzati per spostare il dibattito | Solo cittadini abilitati scrivono, limite di ritmo per etichetta, rimozioni tracciate |
| Molestie dietro l'anonimato | Gli anonimi non rispondono di nulla | Blocco per etichetta e proposta, moderazione a sorteggio con traccia pubblica, contestazione |
| Identificazione per esclusione | In gruppi piccoli si risale alle persone | Soglie minime, intervalli al posto dei numeri esatti |
| Disinformazione nei commenti | Dati falsi presentati come fatti | Commenti con fonti collegabili, segnalazione, rischi e controlli automatici mostrati a parte |
| Divario digitale | Chi non usa app o sito resta senza queste informazioni | Cabine pubbliche con la stessa scheda, stampa della scheda, voto assistito |
| Eccesso di informazione | La scheda diventa troppo lunga per essere letta | Struttura fissa in sei blocchi, sintesi in cima, approfondimenti a richiesta |

## 11. Questioni aperte

- Come si vota quando una fazione porta un emendamento incompatibile con la proposta: voto a più opzioni, voto a turni, o proposte concorrenti separate?
- Chi non è abilitato a votare una proposta deve poter commentare? Un'apertura limitata (ad esempio ai residenti o agli esperti dell'ambito) migliora il dibattito o rischia di aprire una porta alla manipolazione?
- Quanti aderenti servono perché una fazione compaia nella scheda, e quali soglie minime proteggono i gruppi piccoli?
- Come si garantisce che la vista *effettivo* resti affidabile quando gli enti pubblicano i dati con ritardo o in modo incompleto?
- Il sito deve permettere il voto con una chiave software (meno sicura dell'hardware del dispositivo), oppure solo il collegamento al portafoglio dell'app?
- Fino a che livello di dettaglio la mappa copre i singoli contratti e fornitori, senza esporre dati commerciali o personali?
- Quali sono i criteri precisi con cui una segnalazione di impatto non dichiarato viene accolta, e chi li applica?

## 12. Sviluppo allineato alla roadmap

1. **Specifica e prototipo.** Sito pubblico in sola lettura con il ciclo di vita delle proposte e il visualizzatore della mappa su dati di esempio. Editor della modifica economica e controlli di coerenza. Fazioni e commenti con nome, senza anonimato crittografico (con le lacune di privacy documentate, come nella Specifica Tecnica).
2. **Pilota di comunità.** App con portafoglio, adesione alle fazioni con nullifier per proposta, commenti anonimi, scheda di voto completa, mappa sui fondi della comunità.
3. **Pilota comunale.** Mappa su dati reali del comune pubblicati e firmati dall'ente, confronto approvato/effettivo, moderazione a sorteggio, cabine con la stessa scheda, accessibilità completa.
4. **Estensione.** Livelli superiori della mappa (più enti e territori), cruscotti di terze parti sull'interfaccia di lettura, revisione dei parametri alla luce dei piloti.

## Licenza

Rilasciata con licenza [Creative Commons Attribuzione-Condividi allo stesso modo 4.0 Internazionale (CC BY-SA 4.0)](https://creativecommons.org/licenses/by-sa/4.0/deed.it). Cita l'autore originale, **albste**, indica le modifiche e condividi le opere derivate con la stessa licenza.
