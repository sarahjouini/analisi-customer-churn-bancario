# Analisi Customer Churn - Settore Bancario

## Descrizione
Quarto progetto del mio percorso in data analytics. Ho scelto un dataset sull'abbandono dei clienti (customer churn) di una banca, perché si collega direttamente al mio percorso di laurea in Economia e Banca e mi permette di applicare l'analisi dati a un problema di business reale e molto diffuso nel settore finanziario.

L'obiettivo del progetto è capire quali caratteristiche distinguono i clienti che abbandonano la banca da quelli che restano, per poi ragionare su possibili azioni di retention (fidelizzazione).

## Dataset
Il dataset contiene informazioni su 10.000 clienti di una banca, con 12 colonne tra cui età, saldo conto, numero di prodotti bancari posseduti, paese di residenza, e la variabile target `churn` (1 = ha abbandonato la banca, 0 = è ancora cliente).

Fonte: [Bank Customer Churn Dataset - Kaggle](https://www.kaggle.com/datasets/gauravtopre/bank-customer-churn-dataset)

## Domande di business affrontate

1. **Qual è la percentuale di clienti che hanno abbandonato la banca?**
   Su 10.000 clienti totali, circa il **20%** ha abbandonato la banca (2.037 clienti), mentre il restante 80% è ancora cliente attivo.

2. **I clienti che abbandonano hanno un'età media diversa da quelli che restano?**
   I clienti che abbandonano sono in media più anziani (**~45 anni**) rispetto a chi resta (**~37 anni**).

3. **Il saldo del conto è diverso tra chi abbandona e chi resta?**
   I clienti che abbandonano hanno un saldo medio più alto (**~91.000**) rispetto a chi resta (**~72.700**). Questo risultato, all'apparenza controintuitivo, ha senso dal punto di vista bancario: i clienti con saldi più alti hanno più potere negoziale e più alternative sul mercato, quindi sono anche i più contesi dalla concorrenza.

4. **Il numero di prodotti bancari posseduti influenza l'abbandono?**
   La differenza è minima (1.5 prodotti medi per chi abbandona vs 1.4 per chi resta) — questo fattore da solo non sembra determinante per l'abbandono.

5. **Quale paese ha la percentuale di abbandono più alta?**
   La **Germania** ha una percentuale di abbandono del **32%**, quasi il doppio rispetto a Francia e Spagna (entrambe intorno al **16-17%**).

## Implicazioni di business e possibili azioni

Mettendo insieme questi risultati, emerge un profilo di cliente più a rischio di abbandono: **clienti più anziani, con saldi conto elevati, principalmente in Germania**.

Alcune possibili azioni che una banca potrebbe considerare sulla base di questi insight:

- **Programmi di retention dedicati ai clienti con saldi alti**: essendo i più "contesi" dalla concorrenza, meritano un'attenzione commerciale prioritaria (es. consulenza personalizzata, condizioni dedicate).
- **Approfondire la situazione del mercato tedesco**: la percentuale di abbandono doppia rispetto agli altri paesi suggerisce un problema specifico (concorrenza locale più aggressiva, insoddisfazione del servizio, normative diverse) che meriterebbe un'indagine qualitativa oltre a quella quantitativa fatta qui.
- **Attenzione alla fascia di clientela più anziana**: potrebbero avere esigenze finanziarie diverse (es. pensione, successione patrimoniale) che la banca non sta soddisfacendo adeguatamente con l'offerta attuale.
- **Il numero di prodotti non è una leva efficace da solo**: aumentare il cross-selling di prodotti non sembra sufficiente a trattenere i clienti; servono altre strategie più mirate ai fattori che contano davvero (età, saldo, area geografica).

**Dashboard Power BI**
Ho creato una dashboard con i tre insight principali del progetto, pensata per essere capita anche da chi non ha background tecnico. I tre grafici mostrano: la percentuale di abbandono clienti per paese (più alta in Germania), l'età media dei clienti che abbandonano rispetto a chi resta (i clienti che abbandonano sono più anziani), e il saldo medio per gruppo (chi abbandona ha saldi più alti, probabilmente perché ha più alternative sul mercato).

## Tecniche Python/pandas utilizzate
- `pd.read_csv()` per caricare il dataset
- `value_counts()` e `value_counts(normalize=True)` per calcolare frequenze e percentuali
- `groupby()` con `mean()` per confrontare gruppi (clienti churn vs non-churn)
- Interpretazione di una variabile binaria (0/1) tramite la media, per ottenere percentuali per categoria (es. percentuale di abbandono per paese)

## Strumenti
- Python (pandas)
- Visual Studio Code + Jupyter

## Prossimi passi
- Analisi di altre variabili (es. attività del cliente, possesso di carta di credito)
- Visualizzazioni con grafici per rendere gli insight più immediati
- Possibile approfondimento con tecniche di analisi predittiva
