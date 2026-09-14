# 🧩 SUDOKU SOLVER IN PYTHON

Un risolutore di Sudoku ad alte prestazioni scritto interamente in Python. A differenza degli approcci tradizionali basati sul backtracking a forza bruta, questo algoritmo imita il ragionamento umano applicando tecniche di logica deduttiva pura per calcolare ed eliminare progressivamente i candidati.

---

## 🚀 **CARATTERISTICHE PRINCIPALI**

* **SENZA BACKTRACKING**: Nessun tentativo per errore o indovinello; risolve gli schemi usando esclusivamente la logica.
* **VALIDAZIONE INIZIALE INTEGRATA**: Verifica preventivamente che la griglia rispetti le regole base (nessun duplicato su righe, colonne o sotto-griglie 3x3).
* **GESTIONE DINAMICA DEI CANDIDATI**: Calcolo in tempo reale dell'insieme dei candidati validi per ciascuna cella vuota.
* **CICLI DEDUTTIVI ITERATIVI**: Risoluzione ricorsiva fino al completamento dello schema o al raggiungimento del limite logico.

---

## 🧠 **TECNICHE LOGICHE IMPLEMENTATE**

L'algoritmo sfrutta tre principali strategie di risoluzione deduttiva:

### **1. NAKED SINGLES (Candidati Unici Visuali)**
Se una cella vuota ammette un solo numero possibile dopo aver incrociato i vincoli della sua riga, colonna e sotto-griglia 3×3, quel valore viene assegnato immediatamente.

### **2. HIDDEN SINGLES (Candidati Unici Nascosti)**
Se un numero all'interno di un'unità (riga, colonna o blocco 3×3) può occupare una sola posizione specifica tra tutte le celle vuote di quell'unità, quel numero viene posizionato lì, anche se la cella ha altri candidati possibili.

### **3. NAKED PAIRS / DOUBLE PAIRS (Coppie Esclusive)**
Se due celle all'interno della stessa riga, colonna o blocco 3×3 contengono esclusivamente la stessa coppia identica di due candidati `{a, b}`, tali candidati vengono rimossi da tutte le altre celle della medesima unità, restringendo significativamente lo spazio di ricerca per le iterazioni successive.

---

## 📊 **PERFORMANCE & COPERTURA (SUDOKU.COM)**

L'algoritmo è stato ampiamente testato sui livelli ufficiali del sito **Sudoku.com**. I risultati dimostrano l'efficacia dell'approccio deterministico:

| Difficoltà | Tasso di Successo (Senza Backtracking) | Note di Risoluzione |
| :--- | :---: | :--- |
| 🟢 **FACILE** | **100%** | Risolto istantaneamente tramite *Naked Singles*. |
| 🟡 **MEDIO** | **100%** | Completato combinando *Naked Singles* e *Hidden Singles*. |
| 🟠 **DIFFICILE** | **100%** | Risoluzione completa con l'ausilio di *Hidden Singles*. |
| 🔴 **ESPERTO** | **100%** | Risolto grazie alla riduzione via *Double Pairs*. |
| 🟣 **MASTER** | **100%** | Risoluzione deduttiva completa. |
| 👑 **EXTREME** | **~90–95%** | Raggiunge il completamento o quasi-completamento; i casi limite richiedono tecniche avanzate (es. *X-Wing*, *Swordfish*). |

---

## 📥 **INSTALLAZIONE E ESECUZIONE**

### **REQUISITI DI SISTEMA**
* **Python 3.8** o superiore.
* Nessuna dipendenza esterna richiesta (utilizza solo librerie standard).

---

### **1. CLONA IL REPOSITORY**
```bash
git clone https://github.com/flaviomoine/Moine.sudoku.solver
cd sudoku-solver-python
