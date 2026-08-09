# Il caso del pacco misterioso

Un link che le arriva su WhatsApp dalla sua migliore amica. Lei apre, e per
ricevere il pacco deve
scoprire due cose: **chi** gliel'ha mandato e **cosa** c'è dentro.

## Il percorso

1. **Apertura** — messaggio del mittente sconosciuto.
2. **Primo sigillo** — sudoku 9×9 (32 indizi, soluzione unica). Risolto, arriva
   il primo indizio: il mittente ha sei lettere nel nome.
3. **Secondo sigillo** — deve scrivere il nome. La risposta è `SIMONE`.
4. **Quiz** — quattro domande sì/no più la quinta. Ogni risposta riceve una
   battuta diversa, ma il caso prosegue comunque: non si può sbagliare.
5. **Quinta domanda** — «Ritieni di aver capito il regalo?»
   - **Sì** → scrive la sua ipotesi, poi una patina da grattare.
   - **No** → «Ma come, ho chiesto alla migliore!» e la patina da grattare.
6. **Il pacco** — «Hai trovato il pacco misterioso! E dentro c'è…»
7. **Dieci secondi dopo**, da solo: il doppio fondo con il voucher QC Terme.

## Cosa devi riempire tu

Tutto sta in **`src/dati.js`**:

- `PACCO.regalo` — adesso c'è scritto `IL TUO REGALO`: mettici il regalo vero.
- `SICURA.gratta` e `INSICURA.gratta` — cosa compare sotto le due patine.
- `QUIZ[4].d` — la quinta domanda, se vuoi riscriverla.
- `MESSAGGI` — i messaggi WhatsApp che manda la sua migliore amica, in ordine.

Il sudoku sta in fondo allo stesso file: `SOL` è la soluzione, `PUZ` la griglia
con gli zeri. Se cambi uno cambia anche l'altro.

## Farlo girare e pubblicarlo

```bash
npm install
npm run dev
```

Poi push su GitHub e import su Vercel. Nessuna variabile d'ambiente, nessun
database: tutto vive nel browser di lei, che è esattamente quello che serve.

## Farlo arrivare

Il link glielo manda la sua migliore amica su WhatsApp, come se le fosse stata
consegnata una busta da uno sconosciuto poco prima di raggiungerla. I messaggi
da mandare stanno in `MESSAGGI` dentro `src/dati.js`: sono spezzati apposta,
vanno mandati uno alla volta come si scrive davvero.

Due accortezze: il link su un messaggio suo, così WhatsApp lo rende cliccabile
e mostra l'anteprima del fascicolo; e l'amica deve sapere soltanto quello che
c'è scritto nei messaggi. Se sa il resto, alla prima domanda si tradisce.
