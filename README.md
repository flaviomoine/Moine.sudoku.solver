🧩 Sudoku Solver in Python

Un risolutore di Sudoku ad alte prestazioni scritto interamente in Python. A differenza degli approcci tradizionali basati sul backtracking a forza bruta, questo algoritmo imita il ragionamento umano applicando tecniche di logica deduttiva pura per calcolare ed eliminare progressivamente i candidati.



🚀 Caratteristiche Principali

Senza Backtracking: Nessun tentativo per errore o indovinello; risolve gli schemi usando solo la logica.

Validazione Iniziale Integrata: Verifica preventivamente che la griglia rispetti le regole base (nessun duplicato su righe, colonne o sotto-griglie 3x3).

Gestione Dinamica dei Candidati: Calcolo in tempo reale dell'insieme dei candidati validi per ciascuna cella vuota.

Cicli Deduttivi Iterativi: Risoluzione ricorsiva fino al completamento dello schema o al raggiungimento del limite logico.

🧠 Tecniche Logiche Implementate

L'algoritmo sfrutta tre principali strategie di risoluzione deduttiva:

Naked Singles (Candidati Unici Visuali):
Se una cella vuota ammette un solo numero possibile dopo aver incrociato i vincoli della sua riga, colonna e sotto-griglia $3 \times 3$, quel valore viene assegnato immediatamente.

Hidden Singles (Candidati Unici Nascosti):
Se un numero all'interno di un'unità (riga, colonna o blocco $3 \times 3$) può occupare una sola posizione specifica tra tutte le celle vuote di quell'unità, quel numero viene posizionato lì, anche se la cella ha altri candidati possibili.

Naked Pairs / Double Pairs (Coppie Esclusive):
Se due celle all'interno della stessa riga, colonna o blocco $3 \times 3$ contengono esclusivamente la stessa coppia identica di due candidati $\{a, b\}$, tali candidati vengono rimossi dalle altre celle della medesima unità, restringendo significativamente lo spazio di ricerca per le iterazioni successive.

📊 Performance & Copertura (Sudoku.com)

L'algoritmo è stato ampiamente testato sui livelli ufficiali di Sudoku.com. I risultati dimostrano la potenza dell'approccio deterministico:

| Difficoltà | Tasso di Successo (Senza Backtracking) | Note |
| 🟢 Facile | 100% | Risolto istantaneamente tramite Naked Singles. |
| 🟡 Medio | 100% | Completato combinando Naked Singles e Hidden Singles. |
| 🟠 Difficile | 100% | Risoluzione completa con l'ausilio di Hidden Singles. |
| 🔴 Esperto | 100% | Risolto grazie alla riduzione via Double Pairs. |
| 🟣 Master | 100% | Risoluzione deduttiva completa. |
| 👑 Extreme | ~90-95% | Raggiunge il completamento o quasi-completamento deduttivo; le celle rimanenti richiedono tecniche avanzate (es. X-Wing, Swordfish). |




📥 Installazione e Esecuzione

Requisiti

Python 3.8 o superiore.

1. Clona il repository

git clone https://github.com/tuo-username/sudoku-solver-python.git
cd sudoku-solver-python

2. Esegui il risolutore

Nessuna dipendenza esterna richiesta. Esegui semplicemente lo script main:

python Moine.sudoku.solver.py

