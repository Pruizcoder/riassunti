
# Riassunto di SDA

## indice
- [Riassunto di SDA](#riassunto-di-sda)
  - [indice](#indice)
  - [01 - Organizzazione della memoria, chiamate di funzioni, ricorsione](#01---organizzazione-della-memoria-chiamate-di-funzioni-ricorsione)
    - [L'organizzazione della memoria](#lorganizzazione-della-memoria)
    - [Record di attivazione](#record-di-attivazione)
    - [La ricorsione](#la-ricorsione)
      - [Esempio di codice dell' algoritmo del pracheggio](#esempio-di-codice-dell-algoritmo-del-pracheggio)
      - [Altri esempi di funzioni ricorsive](#altri-esempi-di-funzioni-ricorsive)
      - [ricorsione: meccanismo computazionale](#ricorsione-meccanismo-computazionale)
      - [ricorsione ed induzione](#ricorsione-ed-induzione)
  - [02 - Trattabilità e complessità computazionale](#02---trattabilità-e-complessità-computazionale)
    - [Problemi decidibili e indecidibili](#problemi-decidibili-e-indecidibili)
      - [Problemi decidibili](#problemi-decidibili)
      - [Problemi indecidibili](#problemi-indecidibili)
    - [Complessità](#complessità)
      - [Torri di Hanoi](#torri-di-hanoi)
      - [Problema della ricerca della coppia di putni più vicini](#problema-della-ricerca-della-coppia-di-putni-più-vicini)
      - [Algoritmi esponenziali ed algoritmi polinomiali](#algoritmi-esponenziali-ed-algoritmi-polinomiali)
    - [Classi di complessità dei problemi](#classi-di-complessità-dei-problemi)
      - [Classi di complessità](#classi-di-complessità)
      - [Problemi in $NP$](#problemi-in-np)
      - [Analisi di complessità](#analisi-di-complessità)
      - [Notazione asintotica e ordini di complessità](#notazione-asintotica-e-ordini-di-complessità)
      - [Ordini di Complessità](#ordini-di-complessità)
      - [Analisi strutturale](#analisi-strutturale)
        - [Guida per il calcolo del costo al caso pessimo](#guida-per-il-calcolo-del-costo-al-caso-pessimo)
  - [03 - Sequenze lineari e allocazione dinamica della memoria](#03---sequenze-lineari-e-allocazione-dinamica-della-memoria)
    - [Sequenze lineari](#sequenze-lineari)
    - [Allocazione dinamica della memoria](#allocazione-dinamica-della-memoria)
      - [Allocazione della memoria in C](#allocazione-della-memoria-in-c)
    - [Array](#array)
      - [array dinamici](#array-dinamici)
      - [array dinamici: descrittore](#array-dinamici-descrittore)
    - [Liste](#liste)
      - [Puntatori a `struct`](#puntatori-a-struct)
      - [terminologia delle liste](#terminologia-delle-liste)
      - [operazioni di accesso](#operazioni-di-accesso)
      - [lunghezza](#lunghezza)
      - [nodi: inserimento in testa](#nodi-inserimento-in-testa)
      - [nodi: inserimento in coda](#nodi-inserimento-in-coda)
      - [descrittore](#descrittore)
      - [creazione dei nodi](#creazione-dei-nodi)
      - [liste: inserimento in testa e coda](#liste-inserimento-in-testa-e-coda)
      - [Liste: eliminazione in testa e coda](#liste-eliminazione-in-testa-e-coda)
      - [liste: proprietà e stampa](#liste-proprietà-e-stampa)
      - [Liste: eliminazione della lista e di nodi](#liste-eliminazione-della-lista-e-di-nodi)
      - [Liste: Frammenti di altre operazioni](#liste-frammenti-di-altre-operazioni)
      - [Liste: considerazioni conclusive](#liste-considerazioni-conclusive)
      - [Liste doppie](#liste-doppie)
      - [Liste doppie: operazioni](#liste-doppie-operazioni)
      - [Liste: Operazioni/complessità](#liste-operazionicomplessità)
  - [04 - algoritmi di ordinamento](#04---algoritmi-di-ordinamento)
    - [Selection sort](#selection-sort)
    - [insertion sort](#insertion-sort)
    - [Bubble sort](#bubble-sort)
    - [riepilogo](#riepilogo)
    - [Limite inferiore di complessità dell' ordinamento](#limite-inferiore-di-complessità-dell-ordinamento)
  - [05 - Pile e code](#05---pile-e-code)
    - [Pile](#pile)
      - [**Implementazione con array**](#implementazione-con-array)
      - [**implementazione con lista**](#implementazione-con-lista)
    - [Code](#code)
      - [Code con array: implementazione](#code-con-array-implementazione)
    - [Code di priorità](#code-di-priorità)
      - [Code di priorità con lista: implementazione](#code-di-priorità-con-lista-implementazione)
  - [07 - Alberi e Heap tree, code di priorità](#07---alberi-e-heap-tree-code-di-priorità)
    - [Alberi](#alberi)
    - [Nodi](#nodi)
    - [Alberi generici, $k$-ari, binari](#alberi-generici-k-ari-binari)
    - [Alberi: implementazione](#alberi-implementazione)
      - [Alberi completi e bilanciati](#alberi-completi-e-bilanciati)
    - [Heap tree](#heap-tree)
      - [Heap tree: rappresentazione implicita in array](#heap-tree-rappresentazione-implicita-in-array)
      - [Code di priorità tramite Heap tree](#code-di-priorità-tramite-heap-tree)
      - [complessità delle operazioni](#complessità-delle-operazioni)
  - [08 - heap sort](#08---heap-sort)
    - [riepilogo degli allgoritmi visti](#riepilogo-degli-allgoritmi-visti)
    - [Una variazione di selection sort](#una-variazione-di-selection-sort)
    - [Heapsort: un algoritmo di ordinamento Ottimo](#heapsort-un-algoritmo-di-ordinamento-ottimo)
    - [Heapsort: versione concettuale](#heapsort-versione-concettuale)
    - [Heapsort: complessità](#heapsort-complessità)
    - [Hap sort: implementazione *in-place*](#hap-sort-implementazione-in-place)
  - [09 - divide et impera](#09---divide-et-impera)
    - [Esempi di algoritmi divide et Impera](#esempi-di-algoritmi-divide-et-impera)
      - [Ordinamento per fusione: merge sort](#ordinamento-per-fusione-merge-sort)
        - [Pseudocodice](#pseudocodice)
        - [equazione ricorsiva di complessità](#equazione-ricorsiva-di-complessità)
    - [Teorema fondamentale delle ricorrente (master theorem)](#teorema-fondamentale-delle-ricorrente-master-theorem)
      - [Analisi del MergeSort con il teorema fondamentale delle ricorrenze](#analisi-del-mergesort-con-il-teorema-fondamentale-delle-ricorrenze)
    - [Ordinamento per distribuzione: QuickSort](#ordinamento-per-distribuzione-quicksort)
      - [quicksort:complessità](#quicksortcomplessità)
      - [Quickselect](#quickselect)
        - [Analisi di complessità del Quickselect](#analisi-di-complessità-del-quickselect)
    - [Altri esempi di divide et impera](#altri-esempi-di-divide-et-impera)
      - [Moltiplicazione veloce di (grandi) interi](#moltiplicazione-veloce-di-grandi-interi)
      - [Prodotto di interi: limite inferiore alla complessità](#prodotto-di-interi-limite-inferiore-alla-complessità)
      - [Moltiplicazione veloce di interi](#moltiplicazione-veloce-di-interi)
      - [Moltiplicazione veloce di interi](#moltiplicazione-veloce-di-interi-1)
      - [Moltiplicazione veloce di interi](#moltiplicazione-veloce-di-interi-2)
    - [Algoritmi ricorsivi su alberi](#algoritmi-ricorsivi-su-alberi)
      - [Esempio: contare i nodi](#esempio-contare-i-nodi)
      - [Esempio: calcolo della profondità](#esempio-calcolo-della-profondità)
      - [Esempio: visita anticipata](#esempio-visita-anticipata)
      - [Esempio di funzione di elaborazione](#esempio-di-funzione-di-elaborazione)
      - [Visita simmetrica e posticipata](#visita-simmetrica-e-posticipata)
      - [Algoritmi su alberi: complessità](#algoritmi-su-alberi-complessità)
  - [10 - dizionari e le loro implementazioni](#10---dizionari-e-le-loro-implementazioni)
    - [Motivazioni](#motivazioni)
    - [Dizionari](#dizionari)
      - [izionari: struttura del dato](#izionari-struttura-del-dato)
      - [dizionario: operazioni di base](#dizionario-operazioni-di-base)
      - [implementazione con sequenze lineari](#implementazione-con-sequenze-lineari)
    - [Alberi binari di ricerca](#alberi-binari-di-ricerca)
      - [visite su alberi binari di ricerca](#visite-su-alberi-binari-di-ricerca)
      - [ricerca negli alberi binari di ricerca](#ricerca-negli-alberi-binari-di-ricerca)
      - [Inserimento negli alberi binari di ricerca](#inserimento-negli-alberi-binari-di-ricerca)
      - [cancellazione negli alberi binari di ricerca](#cancellazione-negli-alberi-binari-di-ricerca)
    - [Alberi AVL](#alberi-avl)
      - [AVL:cancellazione](#avlcancellazione)
    - [tabelle hash](#tabelle-hash)
      - [Dizionari: implementazione con tabelle hash](#dizionari-implementazione-con-tabelle-hash)
      - [Dizionari: implementazione con tabelle hash con liste di trabocco](#dizionari-implementazione-con-tabelle-hash-con-liste-di-trabocco)
      - [Dizionari: implementazioni con tabelle hash con liste di trabocco](#dizionari-implementazioni-con-tabelle-hash-con-liste-di-trabocco)
      - [Tabelle hash con indirizzamento aperto](#tabelle-hash-con-indirizzamento-aperto)
      - [tabelle hash con indirizzamento aperto: implementazione in C](#tabelle-hash-con-indirizzamento-aperto-implementazione-in-c)
      - [Tabelle has con indirizzamento aperto: analisi](#tabelle-has-con-indirizzamento-aperto-analisi)
      - [Tabelle has con indirizzamento aperto: analisi dell' inserimento](#tabelle-has-con-indirizzamento-aperto-analisi-dell-inserimento)
  - [11 - algoritmi greedy](#11---algoritmi-greedy)
    - [Algoritmi greedy](#algoritmi-greedy)
      - [Algoritmi greedy: dipendenza dalla soluzione](#algoritmi-greedy-dipendenza-dalla-soluzione)
  - [Problema di selezione delle attività](#problema-di-selezione-delle-attività)
      - [Euristica 1: minimo tempo di inizio :x:](#euristica-1-minimo-tempo-di-inizio-x)
      - [Euristica 2: intervallo più piccolo :x:](#euristica-2-intervallo-più-piccolo-x)
      - [Euristica 3: numero inferiore di conflitti :x:](#euristica-3-numero-inferiore-di-conflitti-x)
      - [Euristica 4: minimo tempo di fine :white\_check\_mark:](#euristica-4-minimo-tempo-di-fine-white_check_mark)
      - [Selezione delle attività: esempio di esecuzione](#selezione-delle-attività-esempio-di-esecuzione)
      - [Selezione delle attività: osservazioni](#selezione-delle-attività-osservazioni)
    - [Problema del partizionamento delle attività](#problema-del-partizionamento-delle-attività)
      - [Partizionamento delle attività: esempio di soluzione](#partizionamento-delle-attività-esempio-di-soluzione)

## 01 - Organizzazione della memoria, chiamate di funzioni, ricorsione

### L'organizzazione della memoria

![L'organizzazione della memoria](img/stack_memoria.png)

1. **Code segment**
   - Contiene il codice eseguibile del programma, ossia le istruzioni della CPU
   - è un area di sola lettura, per evitare che il codice venga modificato durante l'esecuzione
   - include funzioni, metodi e istruzioni scritte nel programma
   - *esempio* in C contiene il codice compilato dal programma*
2. **Global segment**
   -  Memorizza tutte le variablili globali e statiche del programma
   - le variabili sono allocate una volta sola e persistono per tutta la durata del programma
   - contiene dati sia inizializzati che non
   - *esempio* la variabile int ```x = 5```; verrà memorizzata qui
3. **Stack** 
   - è l'area di memoria utilizzata per la genstione delle chiamate di funzioni e di variabili locali.
   -Cresce 'verso il basso'(verso indirizzi di memoria più bassi)
   - Quando viene chiamata una funzione il suo contesto(variabili Locali, indirizzi di ritorno, ecc.) vengono allocati nello stack
   -*esempio* una variabile locale ```int y = 10``` sarà nello stack.
4. **heap** 
   - è utilizzata per allocare dinamicamente la memoria.
   - è crescente verso l'alto(indirizzi di memoria più alti)
   - l'allocazione e deallocazione è gestita esplicitamente dal programmatore(es.``` malloc/free``` in C)
   - è più flessibile rispetto allo stack, è più lenta ed è più probabile che sia soggetta ad errori come memory leaks
5. **Free memory**
   - è la memoria libera tra lo stack e l'heap
   -se lo stack e l'heap s'incontrano si verifica un' errore di memoria(stack/heap overflow)
   
---
### Record di attivazione
   Ogni funzione crea un suo spazio di memorizzazione specifico nello stack chiamato **record di attivazione**.
   Esso include tutte le variabili locali, i parametri ed i valori di ritorno della funzione.

   E' come una scatola chiusa, la funzione può fare tutto chiò che vuole senza interferire con l'ambiente di altre funzioni.
   
---
### La ricorsione
La ricorsione è una tecnica di programmazione, ma anche uno strumento per risolvere problemi.
Una funzione è ricorsiva quando al suo interno è presente una chiamata a se stessa.
- La funzione ricorsiva può risolvere direttamente dei casi del problema, detti *casi base*, in questo caso restituisce subito un risultato
- Se vengono passati dei dati che non costituiscono uno dei casi base chiama se stessa passando dei dati *ridotti* o *semplificati*
- ad ogni chiamata i dati si riducono fino ad arrivare ad uno dei **casi base**

#### Esempio di codice dell' algoritmo del pracheggio
```
#include <stdio.h>
#include <stdlib.h> //per random

double drand (double low, double high);

void park (double a, double b)
{
   double p;
   p = drand(a,b);
   printf("Auto parcheggiata nella posizione %f\n", p);
   if(p - a >= 1.0) // c'è spazio sufficente a sinistra per almeno un' Auto
   {
      park(a, p - 1.5);
   }
   if(b-p >= 1.0) // c'è spazio a destra per almeno un'auto
   {
      park(p + 1.5, b);
   }
}
int main(){
   double l = 10.0; // abbiamo una strada lunga 10
   park(1,l-1);
   return EXIT_SUCCESS;
}

```

#### Altri esempi di funzioni ricorsive

- **esempio 1**: il Fattoriale $f(n) = n!$ è definita ricorsivamente così:

$$f(n)=\begin{cases}
1 & se\quad n = 0 \\
n \cdot f(n-1) & se\quad n >0

\end{cases}
$$
```
long fattoriale(long n){
   if n == 0
   {
      return 1;
   }
   else
   {
      return n * fattoriale(n-1);
   }
}
```
Il calcolo viene ricondotto al calcolo del fattoriale di un numero più piccolo fino a raggiungere il caso base noto.

#### ricorsione: meccanismo computazionale
quando la funzione chiama se stessa essa si sospende per eseguire la chiamata ricorsiva.
L'esecuzione riprende quando la chiamata interna termina
la sequenza di chiamate ricorsive termina quando quella più annidata incontra uno dei casi si base
Ogni chiamata alloca sullo *stack* nuove istanze dei parametri e delle variabili locali all' interno dei [**record di attivazione**](#record-di-attivazione)

#### ricorsione ed induzione
La ricorsione è basata sul principio di *induzione matematica*:
   - se una proprietà $P$ vale per $n = n_0$ (**Caso base**)
   - e se posso provare che, *assumendola valida per*  $n$, vale ancheper $n+1$ (**passo induttivo**)
   - allora $P$ vale per ogni $n \geq n_0 $

Risolvere il problema con un approccio ricorsivo comporta: 
1. l'identificazione del **caso di base** in cui la soluzione è nota
2. la capacità di **esprimere il caso generico** in termini dello stesso problema ma in uno o più casi semplificati

- **Esempio 2**: Numeri di Fibonacci
```
inf f(int a, int b){
   assert(b>= 0);//assumiamo b >= 0
   if (b == 0)
      return a;
   else 
      return f(a, b - 1) + 1;

}

```
La successione è definita come 
| $n$   | 0   | 1   | 2   | 3   | 4   | 5   | 6   | 7   | 8   | 9   | 10  | 11  |
| ----- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| $F_n$ | 1   | 1   | 2   | 3   | 5   | 8   | 13  | 21  | 34  | 55  | 89  | 144 |

- $F_0 = 1$
- $F_1 = 1$
- $F_n F_{n-1} + F_{n-2}$ per $n \geq 2$

Numeri di Fibonacci

```
int fibonacci(int n) {
if (n == 0 || n == 1)
return 1;
else
return fibonacci(n - 1) + fibonacci(n - 2;
}
```

## 02 - Trattabilità e complessità computazionale

### Problemi decidibili e indecidibili

Non tutti i problemi computazionali possono essere risolti algoritmicamente, per esempio il problema della fermata(halting problem)
(Turing, 1937)
Non c'è una soluzione nel caso generale(cioè una dimostrazione che consenta di rispondere per un *qualunque algoritmo*)
In alcuni casi specifici tuttavia è possibile dare delle risposte

#### Problemi decidibili
- un problema è **decidibile** (o **calcolabile**) se esiste un algoritmo che per ogni istanza è in grado di **terminare** la sua esecuzione giungendo ad una soluzione
- **Esempio**: *determinare se un numero è primo*
```
#include <stdbool.h>

bool primo (int n)
{
   int fattore;
   if (n== 1)
      return false;
   if (n == 2)
      return true;
   for (fattore = 2; fattore < n / 2; fattore++)
   if (n % fattore == 0)
      return false;
   return true;
}
```

#### Problemi indecidibili
 - un problema è **indecidibile** ( o **non calcolabile**) se nessun algoritmo sia in grado di terminare la sua esecizone giungendo ad una soluzioni ad **ogni istanza**
    
    dato un programma ```A```, non esiste un algoritmo per stabilire se esso terminerà o meno la sua esecuzione su un qualunque input **Problema della fermata(Turing, '37)**
---
### Complessità
alcuni problemi, nonostante decidibili, possono richiedere un tempo di risoluzione notevole, per esempio il problema delle 
#### Torri di Hanoi
- **Obiettivo**: spostare tutti i dischi dal piolo ```a``` al piolo ```c```
- Ogni mossa sposta un disco in cima a un piolo con il vincolo che un disco non può poggiare su uno più piccolo 
- **Descrizione delle mosse**: Supponiamo che i pioli siano etichettati con `A`, `B`, `C`, e i dischi numerati da $1$ (il più piccolo) a $n$ (il più grande).
- **algoritmo ricorsivo**
   1. sposta i primi $n-1$ dischi da `A` a `B`
   2. sposta il disco n da `A` a `C`
   3. sposta i primi $n-1$ dischi da `B` a `C`
   
   per spostare gli n dischi effettuiamo un operazione elementare(la 2, spostamento di un disco) e delle operazioni complesse(la 1 e la 3) che, però, hanno la stessa struttura del problema originale, ossia lo spostamento di $n-1$ dischi, solo su un numero di dischi ridotto di un' unità.
- **stampa delle mosse**
```
void torri_hanoi(int n, char partenza, char intermedio, char destinazione) {
if (n > 1) {
// Sposto tutti gli n - 1 dischi dal piolo partenza
// al piolo intermedio usando il piolo destinazione come appoggio
torri_hanoi(n - 1, partenza, destinazione, intermedio);
/* Sposto il disco rimanente (più largo di tutti) sul piolo destinazione */
printf("disco %d: %c -> %c\n", n, partenza, destinazione);
// Sposto tutti gli n - 1 dischi dal piolo intermedio
// al piolo destinazione usando il piolo partenza come appoggio
torri_hanoi(n - 1, intermedio, partenza, destinazione);
} else {
// È rimasto un solo piolo, lo sposto dal piolo partenza a quello destinazione
printf("disco %d: %c -> %c\n", n, partenza, destinazione);
}
}
/* esempio di chiamata iniziale */
torri_hanoi(5, 'A', 'B', 'C');
```
-**numero di mosse**
 > Per spostare gli n dischi servono $2^n-1$ mosse.
 
 Dimostrabile per induzione:
   - **Caso base**, n = 1: è necessaria una sola mossa, e coerentemente $1=2^1-1$ù
   - **Passo induttivo**, $n>1$: per ipotesi induttiva lo spostamento di $n-1$ dischi richiede un numero di passi pari a $2^{n-1}-1$

L'algoritmo sposta tutti gli $n-1$ dischi dal piolo di partenza al piolo intermedio, poi sposta il disco rimasto sul piolo di destinazione e infine risposta tutti gli $n-1$ dischi dal piolo intermedio a quello di destinazione:
$$
\overbrace{(2{n-1}-1)}^\text{n-1 dischi dal piolo A al B}\quad + \quad \overbrace{1}^{disco n a C}\quad + \quad \underbrace{(2^{n-1}-1)}_\text{n-1 dischi dal piolo B al C}\quad (2^{n-1}-1) + 1 = 2^n-1
$$
-**tempo di calcolo**: Supponiamo di fare una mossa al secondo, i tempi di calcolo seguono la seguente legge

| $n$   | 5     | 10    | 15   | 20    | 25   | 30    | 35      | 40       | 64                |
| ----- | ----- | ----- | ---- | ----- | ---- | ----- | ------- | -------- | ----------------- |
| tempo | $31s$ | $17m$ | $9h$ | $12g$ | $1a$ | $34a$ | $1089a$ | $34865a$ | $585 \cdot 10^9a$ |

E se invece di fare una mossa al secondo potessi fare $b$ mosse al secondo per quanti dischi $m$ aggiuntivi rispetto a $m$ riesco a risolvere il gioco in un dato tempo $t$?

Devoi risolvere l'equazione:
$$
(2^{n+m}-1)/b=t \\
2^{n+m} = tb+1 \\
n+m = log_2(tb+1)\approx log_2\,t + log_2\,b
$$

poichè facendo una mossa al secondo nel tempo $t$ riesco a risolvere $n$ dischi:$n \approx log_2\,t$ e dunque $n+m \approx n+ log_2 \, b \implies m \approx log_2\,b$

Quindi, dato che $m \approx log_2 \, b$, se **raddoppio l amia velocità $(b=2)$, riesco a risolvere $1$ solo disco in più.

Ad esempio, per il numero di dischi *"trattabili"* in un giorno ( <24h )

| **operazioni/sec** | 1   | 10  | 100 | $10^3$ | $10^4$ | $10^5$ | $10^6$ | $10^9$ |
| ------------------ | --- | --- | --- | ------ | ------ | ------ | ------ | ------ |
| $n+m$              | 17  | 20  | 23  | 26     | 29     | 32     | 35     | 45     |

 > Il problema delle torri di hanoi è **intrattabile**: è dimostrabile che non è possibile usare meno di $2^n-1$ mosse.
 (non può esistere un algoritmo che usi un numero inferiore di mosse)

#### Problema della ricerca della coppia di putni più vicini
Dato un insieme di punti $P$ disposti su di un piano, trovare il valore della distanza della coppia di punti che si trova a distanza minima

![distanza minima](img\dist_minima.png)

- **Problema della ricerca della coppia di punti più vicini
```
#include <math.h>
double puntiPiuVicini(/* insieme di punti */P, int n)
{
   double min = +INFINITY, d;
   for (i=0; i<n; i++)
   {
      for (j=0; j<n; j++)
      {
         d = distanza(P,i,j);// distanza fra i punti i e j
         /*confronto*/
         if(i != j && d <min)
         {
            min = d;
         }
      }
   }
   return min;
}

```
- **Tempo di calcolo**

Quante operazioni di calcolo della distanza fra punti verranno effettuate?

$$
\sum_{i=0}^{n-1}\sum_{j=0}^{n-1}1=\sum_{i=0}^{n-1}n = n \, \cdot \, n = n^2
$$

Supponendo di effettuare un controllo al secondo, i tempid i calcolo crescono secondo la seguente legge:
|  $n$  | **5** | **10** | **15** | **20** | **25** | **30** | **35** | **40** |
| :---: | :---: | :----: | :----: | :----: | :----: | :----: | :----: | :----: |
| tempo | $25s$ | $100s$ |  $4m$  |  $7m$  | $10m$  | $15m$  | $20m$  | $26m$  |

Se invece di fare un confronto al secondo, si fanno $b$ confronti al secondo del tempo $t$ riesco a risolvere il problema per uin vettore di dimensione $n+m$, dove $t = (n+m)^2/b$
$$
n+m=(tb)^{1/2}=\sqrt{t}\sqrt{b}=n\sqrt{b}

$$

Aumentare di un fattore moltiplicativo $b$ (ossia $b$ operazioni/sec) migliora di un fattore moltiplicativo circa pari a $\sqrt{b}$
| **operazioni/sec** |   1   |  10   |  100  | $10^3$ | $10^4$ | $10^5$ | $10^6$ |
| :----------------: | :---: | :---: | :---: | :----: | :----: | :----: | :----: |
|       $n+m$        |  64   |  202  |  640  |  2023  |  6400  | 20238  | 64000  |

#### Algoritmi esponenziali ed algoritmi polinomiali

L'algoritmo delle torri di Hanoi è un algoritmo **esponenziale**: richiede un tempo proporzionale ad una funzione esponenziale della dimensione dell' input.
> EPr inciso é la stessa situazione del riempimento delle Terapie intensive in caso di malattie contagiose in assenza di controlle: possiamo raddoppiarne i posti ($b=2$), ma il numedo di giorni che servirà per riempirle interamente si sposta solamente si qualche unità ma no raddoppia.
L'algoritmo della ricerca della coppia di putni vicini è un' algoritmo **polinomiale** proporzionalmente a un polinomio della dimensione dell'input (solitamente di grado basso)

- **Dimensione dei dati per un problema generico**
  
Esistono diverse caratterizzazioni dimensionali per i dati di un problema:
per la rappresentazone dei dati: $k$ bit possono rappresentare interi in 
$$
\{0,1,\dots,2^k -1\}
S$$
 
 Esempio, per $k=3$ 
 | **000** | **001** | **010** | **011** | **100** | **101** | **110** | **111** |
 | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: | :-----: |
 |    0    |    1    |    2    |    3    |    4    |    5    |    6    |    7    |

 *numero di elementi di una struttura dati: array, stringhe, liste, insiemi, alberi*

 *Numero di celle di memoria: occupate dai dati (ognuna contiene $\approx logn$* bit)

-**Definizione**: Un algoritmo è detto ***polinomiale***, nella dimensione di in put $n$, se esistono due costanti $c, n_0 > 0$ tali che il numero di passi elementari da esso eseguiti è al più $n^c$, per ogni input  di dimensione $n$ e per ogni $n> n_0$

-**Definizione**: Un algoritmo è detto ***polinomiale***, nella dimensione di in put $n$, se esistono due costanti $c, n_0 > 0$ tali che il numero di passi elementari da esso eseguiti è al più $c^n$, per ogni input  di dimensione $n$ e per ogni $n> n_0$

- **Problema trattabile**: esiste un algoritmo polinomiale che lo risolve.
- **Problema intrattabile**: non esiste un algoritmo polinomiale che lo risolve.

---
### Classi di complessità dei problemi

  ![Classi di complessità](img\ClassiComplessita.png)

#### Classi di complessità 

- $P$ classe dei problemi risolvibili(*deterministicamente*) in tempo polinomiale
- $EXP$ classe dei problemi risolvibili(*deterministicamente*) in tempo esponenziale
- $NP$ classe dei probleni per i quali verificare una soluzione richiede tempo polinomiale(risolvibili(*non-deterministicamente*)in tempo polinomiale)
- $NPC$ classe dei problemi *completi* per $NP£, detti $NP$-Completi
  
#### Problemi in $NP$

Basato sul concetto di *"certificato polinomiale"* per un problema computazionale $\Pi$
   - chi ha la soluzione per in istanza di $\Pi$ può convincere che la soluzione è giusta in tempo polinomiale
   - chi non ha tale soluzione deve procedere per tentativi richiedendo tempo esponenziale

**Esempio**: date le tre variabili proposizionali $p,q,r \in \{T,F\}$ e la formula logica $\Phi \equiv ( p\,\lor \bar q \lor r) \land(p \, \lor \,r)$, verificare che $p := T, \,q:=F \, r:= F$ soddisfa la formula $\Phi$ è facile, basta sostituire i valori di verità e applicare le regole di valutazione:
$$
(T\lor\bar F\lor F)\;\land\;(T\lor F) \equiv T \land T \equiv T

$$

Per trovare la soluzione è necessario provare le $"2^n$ combinazioni
$(p,q,r) := (T,T,T),(T,T,F), (T,F,T), \dots$di valori di verità per $p,q,r$

$NP$ è la classe di problemi che ammettono un certificato polinomiale

Ovviamente, $P\subseteq NP$ 
   - infatti, quando il problema $\Pi$ sia polinomiale (ossia $\Pi\in P$), il certificato coincide con la soluzione del problema

Riguardo la relazione inversa, non sappiamo se $NP\overset{?}{\subseteq}$ oppure $NP\overset{?}{\nsubseteq}P$

---
#### Analisi di complessità

Negli esempi precedenti abbiano fatto una stima grossolana del numero di operazioni necessarie per risolvere un problema di input $n$

Per avere delle stime più accurate è necessario introdurre un modello di calcolo generico(astratto) e una misura delle operazioni su tale modello di calcolo

- Miusra di **performance** di un *algoritmo* espresse in funzione della dimensione dei dati in input $n$
  - **tempo** numero di operazioni RAM(elementari) eseguite
  - **spazio** numero di celle di memoria occupate(in aggiunta a quelle per l'input)
- **Complessità** o **Costo computazionale** $f(n)$ in tempo e *spazio* di un problema $\Pi$:
  - caso *pessimo* o *peggiore*: costo massimo fra tutte le istanzs di $\Pi$ aventi dimensioni dei dati pari a $n$
  - caso *medio*: costo mediato tra tutte le istanza di $\Pi$ aventi dimensioni pari a $n$
  - ~~caso *ottimo*: costo minimo fra tutte le istanze di $\Pi$ aventi dimensione dei dati pari a $n$~~

**Scopi:**
- Stimare il tempo impiegato per elaborare un dato input
- Stimare il più grande input gestibile in tempi "ragionevoli"
- **Confrontare l'efficenza di algoritmi diversi**
- ottimizzare le parti più importanti

**Dimensione dell' input**
- Costo *logaritmico*: la taglia dell' input è il numero di bit necessari per rappresentarlo
  - Esempio: moltiplicazione di numeri binari lunghi $n$ bit
- Costo *uniforme*: la taglia dell' input è il numero di elementi di cui è costituito
  - Esempio: ricerca minimo in un vettore di $n$ elementi

> Possiamo assumere che gli "elementi" siamo rappresentati da un numero costante di bit e pertanto le due misure coincidono a meno di una costante moltiplicativa

#### Notazione asintotica e ordini di complessità

> Dato che l'accuratezza dei risultati non è il nostro interesse principale utilizzeremo una notazione asintotica, che si avvicina a come si comporta l'algoritmo al crescere delle dimensioni del suo input

- **Limitazione superiore $O(f(n))$**
  
   Definiamo $g(n) = O(f(n))$ se e solo se $\exists \;c, n_0 : g(n) \leq cf(n)\forall n > n_0$

 ![Limite superiore](img\limSup.png)

- **Limitazione inferiore $\Omega(f(n))$**

   Definiamo $g(n) = \Omega(f(n))$ se e solo se $\exist \; c, n_0 : g(n) \geq cf(n)\forall n > n_0$

![Limite inferiore](img\liminf.png)

- **Limitazione $\Theta(f(n))$**
  
  Definiamo $g(n) = \Theta(f(n))$ se e solo se $\exist c_1,c_2,n_0:c_1f(n)\geq g(n) \geq c_2f(n)\forall n > n_0$

![caso medio](img\CasoMedio.png)

#### Ordini di Complessità
|    $f(n)$     | $10^1$ | $10^2$  |  $10^3$  |  $10^4$   |     Tipo     |
| :-----------: | :----: | :-----: | :------: | :-------: | :----------: |
|   $log \;n$   |   3    |    6    |    9     |    13     | Logaritmico  |
|   $\sqrt n$   |   3    |   10    |    31    |    100    |  sublineare  |
|      $n$      |   10   |   100   |   1000   |   10000   |   lineare    |
| $n\; log \;n$ |   30   |   664   |   9965   |  132877   |  loglineare  |
|     $n^2$     | $10^2$ | $10^4$  |  $10^6$  |  $10^8$   |  quadratico  |
|     $n^3$     | $10^3$ | $10^6$  |  $10^9$  |  $10^12$  |    cubico    |
|     $2^n$     | $1024$ | $10^30$ | $10^300$ | $10^3000$ | esponenziale |

$$
O(1) \sub O(log\;n ) \sub O(n^h)\sub(n^hlog\;n)\sub O(a^n) \sub O(n^n)
$$

**Proprietà della notazione asintotica**

Per stimare gli ordini di grandezza non è necessario applicare le definizioni ma si possono usare le seguenti regole per semplificare i calcoli
- **Riflessività**: per ogni costante $c, c\cdot f(n)$ é $O(f(n))$(lo stesso per $\Omega$ e $\Theta$)
- **Transitività**: se $g(n) = O(f(n))$e $f(n)= O(h(n))$allora$g(n)=O(h(n))$(lo stesso per $\Omega$e  $\Theta$)
- **Simmetria**: $g(n)=\Theta(f(n))$ se e solo se $f(n)= \Theta(g(n))$
- **Simmetria trasposta**: $g(n)=\Theta(f(n))$ se e solo se $f(n)= \Omega(g(n))$
- **Somma**: $f(n) + g(n) = O(max\{f(n),g(n)\})$(lo stesso per $\Omega$ e $\Theta$)
- **Prodotto**: $g(n)= O(f(n)), h(n) = O(q(n))$allora $g(n)\cdot h(n) = O(f(n)\cdot q(n))$(lo stesso per $\Omega$ e $\Theta$)

---
  
#### Analisi strutturale

Per gli algoritmi descritti in linguaggi imperativi come il C é possibile definire delle regole che consentono di stimare la complessità computazionale direttamente dalla struttura del programma.
> La stima strutturale al caso pessimo risulta essere particolarmente agevole grazie all' assorbimento degli ordini di crescita inferiori nella notazione asintotica

##### Guida per il calcolo del costo al caso pessimo

- La complessità di una sequenzqa di istruzioni è data dalla somma delle complessità delle singole istruzioni della sequenza
- Il costo di una chiamata a funzione è il costo del suo corpo più il passaggio dei parametri(qualora siano a loro volta delle operazioni non elementari)
  - Le funzioni ricorsive saranno trattate a parte
- la complessita di una condizione `if(guardia)blocco1 else blocco2` è data da:
$$
costo(guardia)+ max\{costo(blocco1), costo(blocco2)\}
$$
- la complessità di un ciclo con un numero determinato di iterazione `for i = 0; i<m; i++` è data da:
$$
\sum^{m-1}_{i=0}costo(corpo)_i+2costante
$$
   costo del corpo all' iterazione $i$, più due volte un costo costante dovuto alla valutazione di  inizializzazione / incremento e condizione
- la complessità di un ciclo con un numero indeterminato di iterazioni`while(guardia)corpo` è data da:
$$
\sum^{m-1}_{i=0}costo(guardia)_i + costo(corpo)_i + costo (guardia)_m
$$
dove $m$ é il massimo numero di volte in cui la guardia risulta soddisfatta.
**Esempio**
Costo computazionale nel calcolo del minimo di un vettore (versione naive)
```
int minNaive(int a[], int n)
{
   int i,j;
   bool is_min;
   for (i = 0;i < n; i++)
   {
      is_min = true;
      for(j = 0, j< n; j++)
      {
         if(a[i]> a[j])
         {
            is_min = false;
         }
      }
   if(is_min)
   {
      return a[i];
   }
   }
}
```
$$
T(n) = 2c_1\cdot n + c_2 \cdot n + 2c_3 \cdot n \cdot n + c_4 \cdot n \cdot n + c_5 \cdot n \cdot n +c_6 \cdot n+c_7 = \\
 n^2(2c_3+c_4+c_5)+n(2c_1+c_2+c_6)+ 1(c_7)\\
 T(n)= n^2  \underbrace{(2c_3+c4+c_5)}_{c^\prime}+n\underbrace{(2c_1+c_2+c_6)}_{c^{\prime \prime}}+1\underbrace{(c_7)}_{c^{\prime \prime \prime}} \\
 O(n^2)+ O(n)+ O(1) = O(n^2)
$$
*(per le regole di **riflessività** e **somma** della notazione asintotica)*

**Caso medio**
Supponendo che i valori nell' array siano distribuiti uniformemente, il minimo ha la probabilità $\frac{1}{n}$ di trovarsi in un punto $j$ del vettore e il csoto dell'algoritmo, per la posizione $j$ è dato da:
$$
jn(1-\frac{1}{n})^{j-1}
$$
- $j\cdot n$ è il numero di elementi verificati(il numero di iterazioni del ciclo esterno $j$ moltiplicato per quelle del ciclo interno $n$)
- $jn(1-\frac{1}{n})^{j-1}$è la probabilità che il minimo non fosse nessun elemento in posizione minore di $j$(la probabilità che non sia il primo è $(1-\frac{1}{n})$, che non sia il secondo $(1-\frac{1}{n})^2$, che non sia il terzo $(1-\frac{1}{n})^3$, e così via)

Il** valore atteso** (la media) del numero di valori verificati è dato dalla somma di tali valori per tutte le posizioni $j$, diviso per il numero $n$ di valori
$$
\mathbb{E}[T(n)]=\sum^{n}_{j=1}{\frac{jn(1-\frac{1}{n})^{j-1}}{n}}=(1-2(1-\frac{1}{n})^n)n^2
$$
si ha
$$
\lim_{n\rightarrow \infty}(1-\frac{1}{n})^n = \frac{1}{e}
$$
dunque
$$
\mathbb{E}[T(n)]\approx(1-\frac{2}{e})n^2=O(n^2)
$$

---

## 03 - Sequenze lineari e allocazione dinamica della memoria

### Sequenze lineari

- Sono delle **strutture di dati astratte** costituite da $n$ elementi $a_0, a_1,\dots, a_{n-1}$ dove $a_j$ è il $(j+1)$-esimo elemento, $0\leq j \leq n-1$
- É in genere rilevante il loro ordine relativo
- Duen modalità di accesso:
  - *diretto*: dato $j$ si accede solo ad $a_j$(**array**)
  - *sequenziale*: dato $j$ è necessario accedere ad $a_0, a_1,\dots, a_{j-1}$  per poi accedere ad $a_j$(**liste**)
    - modalità di elaborazione, in un certo senso simile a quello dei file.
Prima però è da considerare un altro argomento

### Allocazione dinamica della memoria
La gestione dell' **heap** da parte del programmatore avviene, in C, attraverso le seguenti funzioni:
-  `void* malloc(int n)`**alloca** nell' heap un numero di byte pari a `n` e restituisce l'indirizzo di memoria dello spazio allocato sottoforma di un puntatore *generico*
-  `void   free(void*)` **dealloca** lo spazio di memoria iniziallmente puntato dal puntatore passato come parametro

Il valore restituito è di tipo `void*`:
- questa scelta è stata fatta per rendere indipendente la funzione dal tipo di dato allocato (la funzione riserva `n` bytes per il programma)
- per poter utilizzare proficuamente quell'area di memoria sarà necessario convertire il `void*` nel tipo opportuno(ad esempio `int*`, se destinato ad interi, ecc.)

#### Allocazione della memoria in C

Cme specifiare a `malloc` di quanti byte occuperò senza dover ricordarmi la dimensione di ogni tipo di dato?
- posso utilizzare la funzione `sizeof(<tipo_di_dato>)` che restituisce il numero di byte necessari per memorizzare il tipo di dato passato come parametro(es.: `sizeof(int)` restituirà il numero di byte recessari per memorizzare un intero)

Per elaborare dati in alcuni casi è anche necessario anche poter rappresentare un puntatore non inizializzato 
- la constante simbolica `NULL`, di tipo puntatore, indica un puntatore che non punta a nessuna locazione di memoria

**Esempio**: Dichiarazione di una variabile di tipo puntatore

*istruzioni C*
```
int* p_a; // dichiarazione di una variabile di tipo puntatore (4 0 8 byte se 32 o 64bit)

p_a = (int*)malloc(sizeof(int)); // richiesta di allocazione di memoria per un dato di tipo  intero

/* viene creata una licazione di memoria nuova sull'heap(generica, ma di grandezza sufficente a
   contenere un int) il cui indirizzo viene coinvertito ad un puntatore ad intero */

*p_a = 5; // posso utilizzare la nuova memoria allocata attraverso il puntatore

free(p_a);
/* É responsabilità del programmatore liberare la memoria una volta che una variabile non è più necessaria (è imperativo farlo, altrimenti si creano **memory leaks** e il programma potrebbe esaurire rapidamente lo spazio a sua disposizione)

```

### Array

La rappresentazione di un array avviene attraverso l'indirizzo `a` del suo *primo elemento*

I suoi elementi sono memorizzati in posizioni **consecutive**, multiple della dimensione dei dati memorizzati(ad esempio 4 byte per elemento per un intero)

- **vantaggi**: tempo di accesso costante
- **svantaggi**: dimensione fissata, a meno del trucco di sovradimensionare l'array(dimensione *fisica* vs *logica*)

![array](img\array.png)

- `a` rappresenta l'indirizzo di `a[0]`, `a[j]`:`a`+`j`$\times$ dimensione elemento(=`a+j*4`)
  - $\rightarrow$ Accesso all'elemento$a_j$ in tempo $O(1)$

#### array dinamici

Alcimo linguaggi di programmazione(C++, Java, Python, C#) prevedono array  che possono essere creati(e ridimensionati) dinamicamente, cerchiamo di farlo anche in C
```
float* allocaVettore(int n)
{
   float* a = (float*)malloc(n * sizeof(float));
   assert(a!= NULL);
   //la memoria potrebbe non essere allocata e si dovrebbe gestire l'errore
   reuturn a;
}
void dealloca_vettore(float* a)
{
free(a);
a = NULL;
}
```
La funzione `alloca__vettore` restituisce "il vettore" appena allocato(attraverso il puntatore al suo primo evento)
- ciò è possibile perchè il vettore è alloato nell'heap
- non sarebbe corretto se il vettore fosse dichiarato come variabile locale della funzione(e, di conseguenza, allocato sullo stack), perchè quando la funzione termina la memoria viene rilasciata.


L'operazione caratteristica degli array dinamici è quella di ridimensionamento:
```
float* ridimensiona_vettore(float* a, int n, int d)
{
/*la funzione realloc alloca un nuovo spazio di memoria e copia i valori precedentemente memorizzati nell' array:
richjede tempo O(min{n,d}), pari al numero di elementi da copiare
*/
float* a = (float*)realloc(a,d * sizeof(float));
assert(a!=NULL);
return a;
}
```

Il codice di `realloc()` coincide, **concettualmente**, con (i) un'allocazione di un nuono vettore, (ii)la copia dei valori precedentemente memorizzati nel vettore originale e (iii) la deallocazione del vettore originale.

**Osservazione** $d$ può essere più grande o più piccolo di $n$ a seconda che vogliamo estendere o ridurre il vettore originario

L'operazione tipica di ridimensionamento su di un array è quella di aggiunta o di eliminazione di una posizione *in fondo* all'array

- Aggiunta di un nuovo elemento:
  - Alloca lo spazio per un nuovo array $b$ di dimensione $n+1:O(1)$
  - Copia gli elementi di $a$ in $b$: $O(n)$
  - Dealloca $a$ dalla memoria: $O(1)$
  - Ridenomina $b$ come $a$: $O(1)$
- Rimozione di un elemento esistente
  - Alloca lo spazio per un nuovo array $b$ di dimensione $n-1:O(1)$
  - Copia gli elementi da $a$ in $b$: $O(n-1)= O(n)$
  - Dealloca $a$ dalla memoria: $O(1)$
  - Ridenomina $b$ come $a$: $O(1)$

**Inefficente**: richiede tempo totale $O(n)$

**Approccio ammortizzato**

È possibile ottenere qualcosa di più efficente quando le operazioni di inserimento/cancellazione degli elementi in fondo all' array sono più di una?

**Idea**: usiamo un *sovradimensionamento* come per gli array memorizzati sullo stack(lasciando degli elementi **fisici** liberi per ulteriori operazioni)
- per ciascun array necessitiamo di mantenere due informazioni dimensionali:
  - $n$, il numero di elementi significativi(**dimensione logica**)
  - $d>n$, il numero di elementi allocati in memoria, compresi quelli non utilizzati(**dimensione fisica**)
- in particolare decidiamo di effetturare operazioni di aumento o diminuzione raddoppiando o dimezzando la dimensione dell'array(di seguito il perché)

```
//estende il vettore di un elemento
float* estendiVettore (float a[], int* n, int*d)
{
*n = *n +1;
if (*n >=*d)
{//raddoppio
   a = ridimensionaVettore(a, *d, 2*(*d));
   *d = 2* (*d);

}
return a;
}
float* riduciVettore(float a[], int* n, int*d)
{
   *n = *n -1;
   if(*d > 1 && n <= d / 4)
   {//dimezzamento
      a = ridimensiona_vettore(a, *d, *d/2);
      *d = *d / 2; 
   }
return a;
}

```

Con un **raddoppio**, $n=d$ elementi sono copiati nell'array ridimensionato a $2d$ elementi:
occorrono almeno antri $n$ estensioni prima che sia necessario un ulteriore raddoppio

![estensione_vettore](img\estensioneVettore.png)

Il costo di ridimensionamento $O(n)$ è **"spalmato"** su almeno$^\dag$ altre $n$ operazioni di estensione per le quali il costo sarà  $O(1)$(si tratterà di aggiornare la dimensione $n$); il costo **"ammortizzato"** di questa operazione è, pertanto:
$$
\frac{O(n)}{n}= O(1)
$$

$\dag$ portrebbero essere più di $n$ se intercalate con operazioni di riduzione.

:Con un **dimezzamento**, $n= \frac{d}{4}$ elementi sono copiagi nell'array ridimensionato a $\frac{d}{2}$ elementi: occorrono almeno altre $\frac{n}{2}$ riduzioni prima di un unteriore dimezzamento

![riducivettore](img\RiduciVettore.png)

Il costo di ridimensionamento $O(n)$ è **"spalmato"** su almeno altre $\frac{n}{2}$ eventuali operazioni di riduzione o $n$ operazioni di estensione per le quali il costo sarà $O(1)$(si tratterà di aggiornare la dimensione $n$), dunque il costo **"ammortizzato"** sarà:
$$
\frac{O(n)}{n/2}= \frac{2O(n)}{n}= O(1)
$$

In tutti i casi il costo $O(m)$ di tempo di raddoppio o dimezzamento può essere virtualmente distrubuito tra le $m-1=\Omega (m)$ operazioni che lo hanno causato ottenendo una complessità ammortizzata di $O(1), ossia **virtualmente costante**

**implementazione di base**

La logica vista nell'estensione e riduzione del vettore dinamico richiede che per rappresentarlo sia necessario mantenere (e gestire) contemporaneamente 3 informazioni:
- `a` il **puntatore** all' area di memora dell'array(primo elemento)
- `n` la dimensione **logica** dell'array
- `d` la dimensione **fisica** dell'array
```
float* allocaVettoreDinamico(int n, int*d)
{
   float* a = (float*)malloc(n*2*sizeof(float));
   assert(a!=NULL)
   *d = n*2;
   return a;
}

```

Ciò comporta che sia necessario, oltre che modificarle coerentemente, "portandosele dietro" in tutte le funzioni di manipolazione.

**implementazione "ingegnerizzata"**

Il probleda di gestire contemporaneamente più informazioni / variabili per rappresentare una struttura dati concreta è comune a tutte le strutture dati concrete
- anche la più semplice di esse, ossia l'array soffre di questo problema

Vorremmo rappresentare e gestire tutte le informazioni in un "contenitore" logico, che consente di accedere a ciascuna di esse ma che le tratti come un *unicum*
- che costrutto di programmazione possiamo utilizzare per questo?

#### array dinamici: descrittore

Rappresentiamo tutte le informazioni che descrivono la struttura dati attraverso un **record**, detto **descrittore**, che combina insieme tutte le informazioni necessarie
```
typedef struct /*anonima*/
{
   //Puntatore allo spazio di memoria allocato per il vettore nell'heap
   float *dati;
   //Dimensione logica del vettore:Numero di elementi effettivi
   int dimensione;
   //Dimensione fisica del vettore: numero di elementi allocati nell'heap
   int capacita;
}vettore_dinamico;
```

**Convenzione** tutte le operazioni di manipolazione *restituiscono* il nuovo descrittore(esplicitamente o attraverso il passaggio per riferimento)

**Nota**: l'istruzione `typedef <tipo> <nome_alias>` crea un alias per un determinato tipo di dato consentendo di omettere`struct <nome_struct>` quando dichiariamo le variabili

**Funzioni di manipolazione**
```
vettore_dinamico creaVettoreDinamico(int n)
{
vettore_dinamico v;
//non ha senso creare vettori con dim negativa
assert(n>=0)
if(n>0)
{
   //alloca lo spazio per i dati, memorizzando il puntatore del descrittore
   v.dati = (float*)malloc(2* n * sizeof(float));
   //verifica che l'allocazione abbia avuto buon esito
   assert(v.dati != NULL)
}
else 
   {
      v.dati = NULL;
   }
v.dimensione = n;
v.capacita = 2*n;
return v;
}

```
```
void ridimensiona_vettore_dinamico(vettore_dinamico *v, int n)
{
   assert(n >= 0);
    if(n>= v->capacita)
    {\\raddoppia
      v-> dati = (float*)realloc(v->dati, 2*n*sizeof(float));
      //verifica che la riallocazione abbia avuto buon esito
      assert(v-> dati != NULL);
      v->capacita = 2*n;
    }else if(v-> capacita > 1 && n <= v-> capacità /4)
    {//dimezza
      // si osservi che v->capacita / 2 == n * 2 (perché n <= v->capacita / 4)
      v-> dati = (float*)realloc(v->dati, 2*n*sizeof(float));
      assert(v->dati != NULL);
      v->capacita = 2*n;
    }else if (v->capacita == 0 && n > 0)
    {//passa da zero ad una dimensione diversa da zero
     v->dati = (float*)malloc(2*n*sizeof(float));
     assert(v->dati != NULL);
     v-> capacita = 2*n;
    }
    v->dimensione = n;
}

```
```
void elimina_vettore_dinamico(vettore_dinamico *v)
{//elimina dati
   free(v->dati);
   v->dimensione = 0;
   v->capacita = 0;
}

void stampa_vettore_dinamico(vettore_dinamico v)
{
   int i;
   for(i = 0; i < v.dimensione; i++)
      prinf("%g", v.dati[i]);
   if(v.dimensione > 0)
      printf("\n");
}
```

La definizione del descrittore e di queste funzioni è compresa nella libreria di **Strutture dati e Algoritmi** in un header chiamato `array.h`(disponibile su e-learning)

**Considerazioni finali**

Vantaggi:
- Dimensione **veramente** dinamica
- efficenza nelle operazioni di ridimensionamento di un'unità(quelle più tipiche) che richiedono tempo costante

Limiti:
- Necessità di mantenere più informazioni in modo coerente(comune anche agli array classici)
- Vincolo **forte** sul tipo di dato contenuto nell'array
  - in principio dovremmo definire un nuovo descrittore e "ricopiare il codice" delle funzioni per adattare i dati ad un altro tipo diverso da `float`

---
  
### Liste
![liste](img\liste.png)

Una **lista** è l'implementazione concreta di una struttura dati *sequenza* ad **accesso sequenziale**.

È rappresentata dall'indirizzo $a$ (del primo elemento della lista, detto **nodo**) e le altre posizioni sono sparse(a causa della gestione dinamica della memoria nell'heap)
Struttura:
-  $a$ indirizzo del primo elemento $a_0$
-  l'elemento $a_j$ contiene il dato e l'indirizzo dell'elemento $a_{j+1}$(se esiste)
```
typedef struct _nodo_lista{
   //dato contenuto nel nodo corrente
   float dato;
   //successore del nodo corrente(NULL in caso non esista)
   struct _nodo_lista *succ;
}nodo_lista;
```
- il campo `dato` contiene il dato, mentre il campo `succ` indica l'elemento successivo
- il valore `NULL` indica la fine della lista
- la lista vuota è indicata da $a$ avente valore `NULL`

Sostanzialmente, dunque, una lista può essere rappresentata da un puntatore al suo primo elemento con la struttura descritta in precedenza

Alcune osservazioni sulla definizione:
- la `struct _nodo_lista` è **ricorsiva**(ossia utilizza, nella sua definizione, un puntatore a se stessa), pertanto *non può essere definita in modo "anonimo"*
- Utilizzeremo la convenzione di premettere un carattere di sottolineatura `_` ai nomi che è necessario definire ma che non ci interessano

#### Puntatori a `struct`

Nel caso di una variabile che contenga un puntatore a `struct` la notazione per accedere ad un elemento della struct stessa può essere semplificato
```
nodo_lista* p = ...; //supponiamo p sia un nodo della lista

(*p).dato = 5; //accesso tradizionale(dereferenzio p e accedo al campo dato)

p->dato = 5; // accesso semplificato (accedo al campo dato puntato da p)
```

#### terminologia delle liste

- un **nodo** della lista, detto anche **elemento**, è una variabile del tipo`struct _nodo_lista` memorizzata sull'heap
- il primo elemento della lista $(a_0)$ è detto **testa** della lista e rappresenta il punto di accesso alla lista stessa
- l'ultimo elemento della lista $a_{n-1}$ è detto **coda** della lista, talvolta può essere gestito esplicitamente anche se non è indispensabile
- dato un nodo $a_j$, il dono $a_{j+1}$ raggiungibile attraverso il puntatore `succ` è detto **successore** del nodo $a_j$
  - il successore **non esiste** nel caso $j = n-1$, in tal caso il puntatore è `NULL`
- il nodo $a_{j-1}$,  se $j>0$, è detto **predecessore** del nodo $a_j$
  - non esiste predecessore della testa

#### operazioni di accesso

Accesso ad $a_j$:scandire i primi $j$ elementi, iniziando da $a_0$ e accedere via via al successivo: tempo totale $O(j+1)$(qualora si possa partire da $a_{j-k}$ il costo è $O(k)$)
```
nodo_lista* elemento_lista(nodo_lista* t, int j)
{//questo frammento di codice può essere utilizzato anche al di fuori della funzione
   int i = 0;
   nodo_lista *c = t; //t è la testa della litsa, c è il nodo corrente
   while(i < j && c |= NULL)
   {
      i++;
      c = c->succ;
   }
   //se i >= j vuol dire che la lista non aveva almeno j elementi
   //in tal caso c == NULL
   return c;
}
```

Caso pessimo$O(n)$ con $n$ lunghezza della lista

#### lunghezza

Per conoscere la lunghezza della lista, senz'alcun'altra informazione, devo scandirla interamente contando di quanti elementi è costituita
```
int lunghezza_lista(nodo_lista* t)
{
int i = 0;
nodo_lista *c = t;//t è la testa della lista, c è il nodo corrente
while(c != NULL)
{
   i++;
   c = c->succ;
}
return i;

}
```

Per migliorare la complessità, in genere oltre ad $a$, puntatore al primo elemento della lista si potrebbe anche mantenere la lunghezza della lista $l$

#### nodi: inserimento in testa

Inserimento in testa dell'elemento `s`(`t` è la testa precedente):
```
nodo_lista* inserisci_in_testa(nodo_lista *t t, nodo_lista *s)
{
   s->succ = t;
   t = s;
   return t;
}
```
![inserimento in testa della litsa](img\inserimentoInTestaLista.png)

Tempo $O(1)$


#### nodi: inserimento in coda

Inserimento in coda alla lista dell'elemento `s`:

```
nodo_lista* inserisci_lista_coda(nodo_lista *t t, nodo_lista *s){
   nodo_lista*c = t;
   if(c == NULL)
   {
      t = s;
      return s;
   }
while(c->succ != NULL)
   c = c->succ;
   //aggiungi l'elemento in coda
   c-> succ = s;
   s-> succ = NULL;
   return t;
}
```

Tempo $O(n)$ dovuto alla ricerca dell' elemento in coda attraverso `c`. Qualora si memorizzasse sempre anche il puntatore all'ultimo elemento della lista: $O(1)$

#### descrittore

Analogamente al caso degli array, per riunire in un unico contenitore tutte le informazioni relative ad una lista utilizziamo un descrittore che **rappresenta** la lista e verrà modificato dalle funzioni di manipolazione delle liste
```
typedef struct{
   //per la manipolazione della lista e l'accesso sequenziale
   nodo_lista *testa;
   //per rendere più efficente l'eventuale inserimento in coda
   nodo_lista *coda;
   //per rendere più efficente l'interrogazione sulla lughezza della lista
   int lunghezza;
}lista;
```
**Convenzione**: tutte le operazioni di manipolazione di liste *restituiscono*(direttamente o per passaggio per riferimento) il nuovo descrittore alla lista

#### creazione dei nodi
```
nodo_lista *crea_nodo(float dato){
   nodo_lista *n = (nodo_lista)malloc(sizeof(nodo_lista));
   n->dato = dato;
   n->succ = NULL;
   return n;
}

lista crea_lista(){
   lista l;
   l.testa = NULL;
   l.coda = NULL;
   l.lunghezza = 0;
   return l;
}
```
#### liste: inserimento in testa e coda

```
void aggiungi_in_testa(litsa *l, float dato){
   nodo_lista *n = crea_nodo(dato);
   if (l->lunghezza == 0)
   {
      l->coda = n;
   }
      n->succ = l->testa;
      l->testa = n;
      //dobbiamo mantenere la coerenza
      //anche di questo dato
      l->lunghezza++;
}
```
```
void aggiungi_in_coda(lista *l, float dato){
   nodo_lista *n = crea_nodo(dato);
   if (l->lunghezza > 0)
   {
      l->coda->succ = n;
   }else{
      l-> testa = n;
   }
   l->coda = n;
}
```
#### Liste: eliminazione in testa e coda

```
void elimina_in_testa(lista *l){
   nodo_lista *n = l-> testa;
   // se la lista è vuota non c'è nulla da eliminare
   if(l->lunghezza == 0)
      return;
   // altrimenti sposta i puntatori
   l->testa = l->testa->succ;
   //aggiorna la lunghezza
   l-> lunghezza--;
   //elimina il nodo
   elimina_nodo(n);
   //mantieni la coda coerente
   if(l->lunghezza == 0)
      l->coda = NULL;
}
```
```
void elimina_in_coda(lista *l){
   nodo_lista *c = l->testa, *n = l->coda;
      if(l->lunghezza == 0 )
      return;
      //cerca il predecessore della coda
      //che diventerà la nuova cosa
      if (l->lunghezza == 1){
         l->testa = NULL;
         l->coda = NULL;
      }
      else
      {
         while(c->succ != n)
            c = c->succ;
         l->coda = c;
         l-coda->succ = NULL;
      }
      l->lunghezza--;
      elimina_nodo (n);
}
```
#### liste: proprietà e stampa

```
int lunghezza(lista l){
   return l.lunghezza;
}
bool lista_vuota(lista l){
   return l.lunghezza == 0;
}

```

```
void stampa_lista(lista l){
   nodo_lista *n = l.testa;
   while(n!= NULL){
      printf("%g", n->dato);
      n = n-> succ;
   }
   if (l.lunghezza > 0)
   printf("\n")
}
```
#### Liste: eliminazione della lista e di nodi

```
void elimina_lista(lista *l){
   nodo_lista *n = l->testa;
   while(n!= NULL){
      nodo_lista *s = n->succ;
      elimina_nodo(n);
      n = s;
   }
   l->testa = NULL;
   l->coda = NULL;
   l->lunghezza = 0;
}
```

```
void elimina_nodo(nodo_lista *n){
   free(n);
   n = NULL;
}
```

#### Liste: Frammenti di altre operazioni

**Inserimento di un nuovo elemento** `s` come successore di un elemento arbitrario `p` (se `p !=  NULL`, tempo $O(1)$).

```
s->succ = p->succ;
p->succ = s;
```
**Rimozione** di un elemento `n` se il suo predecessore non è noto (Tempo $O(n)$)

```
nodo_lista* c = l.testa->succ, *p = l.testa;
//determino p, il predecessore di n
while (p->succ != n){
   p = c;
   c = c->succ;
}
p->succ = n->succ;
```

**Schema di iterazione ed elaborazione** lungo tutti gli elementi di una lista:
```
nodo_lista* c = l.testa;
while(c!= NULL){
   Elabora(c);
   c = c-> succ;

}
//la funzione di elaborazione di ciascun nodo dev'essere qualcosa del tipo:
//void Elabora(nodo_lista c)
```

#### Liste: considerazioni conclusive

**vantaggi**
- dimensione dinamica senza necessità di sovradimensionamento
- possibilità di inserimento di un elemento esistente in qualunque punto della sequenza a differenza dei vettori nei quali posso solo aggiungere ed eliminare alla fine del vettore

**svantaggi**
- tempo di accesso dipendente dalla posizione dell'elemento
- asimmetria nelle operazioni di accesso sequenziali per indici crescenti(facile, $O(1)$) o decrescenti(costosa, $O(n^2)$)

---

#### Liste doppie

Uno degli svantaggi della lista(semplice) è la necessità di ripartire dalla sua testa qualora sia necessario trovare il predecessore di un elemento
- ad esempio per effettuare un inserimento in coda o l'eliminazione di un nodo arbitrario

Ovviamo a questa limitazione con una struttura leggermente diversa in chi viene mantenuto anche il puntatore all'elemento precedente

![listeDoppie](img\listeDoppie.png)

Ciò consente lo spostamento, seppur sequenziale, da qualunque nodo in entrambe le direzioni (avanti e indietro)

La struttura è analoga a quella della lista semplice, il descrittore è praticamente uguale, cambia la descrizione del singolo nodo
```
typedef struct _nodo_lista_doppia{
   float dato; // dato contenuto nel nodo corrente
   struct _nodo_lista_doppia* succ; // successore del nodo corrente
   struct _nodo_lista_doppia* pred; // predecessore del nodo corrente
}nodo_lista_doppia;

typedef struct{
   nodo_lista_doppia* testa;
   nodo_lista_doppia* coda;
   int lunghezza;
}lista_doppia;

```

#### Liste doppie: operazioni
Sostanzialmente simili a quelle della lista semplice, con la differenza di **dover mantenere la coerenza** anche del puntatore all'elemento precedente, ad esempio:
```
void aggiungi_in_testa_d(lista_doppia *l, float dato){
   nodo_lista_doppia *n = crea_nodo_d(dato);
   if(l->lunghezza == 0)
      l->coda = n;
   if( l->lunghezza > 0)
      l->testa->pred = n; // anche il predecessore va mantenuto coerente
   n-> succ = l->testa;
   l-> testa = n;
   l->lunghezza++;

}
```

#### Liste: Operazioni/complessità

Complessita temporale $T(n)$ delle operazioni con $n$ lunghezza corrente della lista

|             Operazione             | lista semplice(senza puntatori aggiuntivi) | lista semplice(con puntatori aggiuntivi) | lista doppia |
| :--------------------------------: | :----------------------------------------: | :--------------------------------------: | :----------: |
|             Creazione              |                   $O(1)$                   |                  $O(1)$                  |    $O(1)$    |
|        inserimento in testa        |                   $O(1)$                   |                  $O(1)$                  |    $O(1)$    |
|        inserimento in coda         |                   $O(1)$                   |                  $O(1)$                  |    $O(1)$    |
|       ricerca di un elemento       |                   $O(n)$                   |                  $O(n)$                  |    $O(n)$    |
| inserimento in un punto arbitrario |                   $O(n)$                   |                  $O(1)$                  |    $O(1)$    |
|       eliminazione in testa        |                   $O(1)$                   |                  $O(1)$                  |    $O(1)$    |
|       eliminazione in testa        |                   $O(n)$                   |                  $O(n)$                  |    $O(1)$    |
|            distruzione             |                   $O(n)$                   |                  $O(n)$                  |    $O(n)$    |


## 04 - algoritmi di ordinamento

**il problema dell' ordinamento**

Data una **sequenza** di $n$ elementi e una loro relazione d'ordine $\leq$, disporre gli elementi **nell'array** in modo che risultino ordinati secondo la relazione $\leq$

Nota:
- la relazione d'ordine non è necessariamente quella crescente e dipende dal tipo di dato conenuto nel vettore, per ora considereremo interi e la relazione $\leq$ su di essi 
- La sequenza non é necessariamente contenuta in un array (ipotesi necessaria ora per le conoscenze attuali)

### Selection sort 

**Idea**: al passo $i$ selezione l'elemento di rango $i$ ossia il minimo tra i rimanenti $n-i$ elementi e scambialo con l'elemento in posizione $i$

![selection sort](img\selectionsort.png)

**Nota**: il rango di un elemento del vettore è costituito dal numero di elementi più piccoli di esso che corrisponde alla sua posizione nel vettore ordinato

```
void selection_sort(int a[], int n){
   int i, indice_minimo;
   for(i = 0, i< n-1; i++){
      indice_minimo = minimo_a_partire_da(a,n,i);
      scambia(&a[i], &a[indice_minimo];)
   }
}

int minimo_a_partire_da(int a[], int n, int i){
   int j, m = i;
   for (j = i + 1;j<n; j++){
      if(a[j] < a[m])
         m = j;
   }
   return m;
}

```

A meno di componenti di costo costante, al passo $i$-esimo il costo del corpo del `for` è pari al costo $t(i,n)$ della chiamata della funzione `minimo_a_partire_da()`
-  esso non è costante ma dipende da $i$(oltre che da $n$)
-  dunque il costo totale è pari a $\sum^{n-1}_{i=0}t(i,n)+O(1)$

Il costo della funzione t(i,n) in dipendenza di $i$ è proporzionale al numero di iterazioni del ciclo(più l'assegnamento esterno) quindi $t(i,n)=O(n-i)$

Pertanto
$$
T(n) = \sum^{n-2}_{i=0}O(n-i)+O(1)= O(\sum^{n-2}_{i=2}n-i)=O(\sum^{n-2}_{i=2}i)= O(n^2)
$$

A causa del calcolo del minimo fra gli elementi rimasti anche la complessità del caso migliore è $O(n^2)$(e quindi anche nel caso medio)

### insertion sort

**Idea** al passo $i$-esimo inserisci l'elemento in posizione $i$ al posto giusto tra i primi $i$ elementi(già ordinati)


![InsertionSort](img\insertionSort.png)
```
void insertion_sort(int a[], int n){
   int i, j , prossimo;
   for (i = 1, i <n; i++){
      //estrae il prossimo elemento da inserire
      prossimo = a[i];
      //j è la posizione candidata all'inserimento
      j=i;
      //verifica se la posizione corrente è quella giusta
      while(j > 0 && a[j - 1] > prossimo){
         //altrimenti fai spazio;
         a[j]= a[j-1];
         j = j - 1;
      }
      a[j] = prossimo;
   }
}

```

Per poter inserire in un qualunque punto fra gli elementi già ordinati devo fare spazio (non posso modificare un vettore creando un elemento in un punto qualunque)

Il ciclo `while`, se necessario, sposta gli elementi verso destra per fare spazio al prossimo elemento da inserire

Al passo $i$ del `for` esterno il costo è dominato dal costo $t(i)$ del ciclo `while` interno
- il ciclo `while` richiede al massino $i+1$ iterazioni, ciascuna di costo costante
  - $t(i) = O(i+1)$ per il ciclo while

In totale $\sum_{i=0}^{n-1}O(i+1)= O(\sum_{i=0}^{n-1}i+1)=O\frac{n(n+1)}{2}= O(n^2)$

**Osservazione**:l'algoritmo richiede solo $O(n)$ operazioni quando l'array è già ordinato
   In generale è possibile provare che l'algoritmo richiede tempo $O(nk)$ se ciascun elemento si trova al più a distanda $k$ dalla sua posizione nell'array ordinano(quindi parecchio efficente per array quasi ordinati)

### Bubble sort

**Idea**:confrontare gli elementi a coppie e fare salire i valori più grandi verso la fine dell'array(e scendere quelli più piccoli verso l'inizio)

![bubble sort](img\BubbleSort.png)
```
void bubble_sort(int a[], int n){

int i, k = n - 1;
bool scambio = true;
while(scambio){
scambio = false;
for (i = 0; i < k; i++)
   if(a[i]> a[i+1]){
      scambia(&a[i], &a[i+1])
      scambio = true;
   }
   k = k - 1;
}
}

```

All'iterazione $i=1, \dots,n$ del ciclo `while` l'elemento di posizione $n-i=k$ sarà salito nella sua posizione definitiva
- la porzione di vettore compresa fra gli indici $k$e $n-1$ è ordinata
- Al passo $k$ del ciclo `while` il costo del suo corpo$t(k)$ è dominato dal ciclo for interno che richiede tempo $O(k)$

Il corpo del ciclo `while` può essere eseguito al più $n$ volte (per $k=n-1,\dots$,0) quindi in totale
$$
T(n)= \sum_{k=0}^{n-1}t(k) =\sum_{k=0}^{n-1} O(k) = O(\sum_{k=0}^{n-1}k) = o(\frac{n(n-1)}{2})= O(n^2)
$$

Nel caso di un array già ordinato, il numero di operazioni svolte è $O(n)$, corrispondenti all'esecuzione del ciclo `for` che determina che nessuno scambio è necessario e in tal caso il ciclo `while` viene eseguito una volta sola.

### riepilogo
|   **Algoritmo**    |                                                **Idea**                                                 | **Caso Pessimo** | **Caso Ottimo** |
| :----------------: | :-----------------------------------------------------------------------------------------------------: | :--------------: | :-------------: |
| **Selection sort** | Cerco(seleziono) l'elemento minimo fra quelli rimasti da ordinare e lo scambio con l'elemento corrente  |     $O(n^2)$     |    $O(n^2)$     |
| **Insertion Sort** |                Cerco di inserire l'elemento corrente fra quelli precedenti, già ordinati                |     $O(n^2)$     |     $O(n)$      |
|  **Bubble sort**   | Effettuo più passaggi facendo *affiorare* gli elementi più grandi, finchè non sono necessari più scambi |     $O(n^2)$     |     $O(n)$      |

è possibile fare di meglio?
### Limite inferiore di complessità dell' ordinamento

Qual'è, nel caso peggiore, il **numero minimo di operazioni** richieste da un qualunque algoritmo di ordinamento basato sul confronto di elementi?

- il cuore degli algoritmi di ordinamento sono le operazioni di confronto, contiamo quindi tali operazioni
- Consideriamo un qualunque algoritmo di ordinamento $\mathcal{A}$ che usa confronti tra coppie di elementi

In $t$ confronti (*passi,operazioni*), $\mathcal{A}$ può discernere sl più $2^t$ situazioni distinte:
- sono infatti possibili due risposte per ogni confronto: $a_i\leq a_j$, oppure $a_i > a_j$

Il numero di possibili ordinamenti di $n$ elementi é $n!$(tutte le loro permutazioni)

Poiche $\mathcal{A}$ deve discernere tra $n!$ possibili situazioni, deve valere $2^t\geq n!$, pertanto, risolvento in $t$

$$
t= log 2^t \geq log \underbrace{n!}_{\sqrt{2\pi n}(\frac{n}{e})^n}  = log \;O(n^n) = O (n\,log\,n)


$$

Dunque t = $\Omega(n\;log\,n)$(perchè $t\geq O(f(n))$) è un limite inferiore alla complessità di qualunque algoritmo di ordinamento basato sui confronti

## 05 - Pile e code

### Pile

Collezioni di  elementi in cui le operazioni disponibili, come l'estrazione di un elemento sono ristrette unicamente a quello più recentemente inserito
- Politica di accesso **Last In First Out(LIFO)**: l'ultimo elemento inserito è il primo ad essere estratto
- Operazioni:
  - `Push(p,d)`: inserisce un nuovo elemento in cima alla pila
  - `Pop(p)`: estrae l'elemento in cima alla pila (opzionalmente restituendo l'informazione in esso contenuta, non per noi)
  - `Top(p)`: restituisce l'informazione contenuta nell'elemento in cima alla pila
  - `Empty(p)`: verifica se la pila è vuota


#### **Implementazione con array**

- Elementi della pila memorizzati in un array di dimesione iniziale predefinita
- Array ridimensionato per garantire che la dimensione sia proporzionale al numero di elementi effettivamente nella pila
- Elementi  memorizzati in sequenza nell'array a partire dalla locazione iniziale, inserendoli man mano nella prima locazione disponibile
- La cima della pila corrisponde all'ultimo elemento della sequenza

![cima pila](img\cimapila.png)

- dopo un `Pop(p)`

![cimapila](img\pop.png)

Dopo `Push(p,1)`,·`Push(p,3)`

![push](img\push.png)

#### **implementazione con lista**

- Elementi della pila memorizzati in una lista ordinata per istante di inserimento decrescente
- La cima della pila corrisponde all'inizio della lista
- Le operazioni agiscono tutte sull'elemento iniziale della lista


![pila lista](img\pilalista.png)

- dopo un `Pop(p)`

![poplista](img\poplista.png)

- dopo `Push(p,1)`,`Push(p,3)`,`Push(p,11)`
  
![pushlista](img\pushlista.png)

### Code

Collezione di elementi in cui le operazioni disponibili, come l'estrazione di un elemento, sono ristrette unicamente a quello inserito meno recentemente

Politica di accesso **First In First Out(FIFO)**: il primo elemento inserito è il primo ad essere estratto

- Operazioni
  - `Enqueue(q,d)`: inserisce un nuovo elemento in fondo alla coda
  - `Dequeue(q)`: estrae l'elemento in testa alla coda(opzionalmente restituendo l'informazione in esso contenuta, non per noi)
  - `First(q)`: restituisce l'informazione contenuta nell'elemento in testa alla coda senza estrarlo
  - `Empty(q)`: verifica se la coda è vuota o meno

#### Code con array: implementazione

- Elementi della coda memorizzati in un array di dimensione iniziale predefinita
- Arrray ridimensionato per garantire che la dimensione sia proporzionale al numero di elementi effettivamente nella coda
- Elementi memorizzati in sequenza nell'array a partire dalla locazione iniziale, inserendoli man mano nella prima locazione disponibile
- La testa della coda corrisponde al primo elemento della sequenza 
- Il fondo della coda corrisponde all'ultimo elemento della sequenza
- Gestione "circolare" della coda

![gestioneCircolare](img\gestioneCircolare.png)

- Nodi concatenati e ordinati in modo crescente secondo l'istante di inserimento
- Il primo nodo della sequenza corrisponde alla "testa" della coda ed è il nodo da estrarre nel caso di una `Dequeue`
- l'ultimo nodo corrisponde al "fondo" della coda ed è il nodo a cui concatenare un nuovo nodo, inserito mediante `Enqueue`

### Code di priorità

- Collezioni di elementi in cui a ogni elemento è associato un valore(priorità) appartenente a un insieme totalmente ordinato (solitamente l'insieme degli interi positivi)
- estensione della coda:le operazioni sono le stesse della coda: `Empty`, `Enqueue`, `First` e `Dequeue`
- `First` restutuisce l'elemento di priorità massima(o minima)


#### Code di priorità con lista: implementazione

- Prima soluzione: *lista non ordinata*
  - La `Enqueue` richiede tempo costante, con i nuovi elementi inseriti a un estremo della lista
  - La `Dequeue` e la `First` richiedono tempo $O(n)$: perchè è necessario individuare l'elemento di priorità massima all'interno della lista
- Seconda soluzione: *lsita ordinata*
  - La `Dequeue` e la `First` richiedono tempo costante: l'elemento di massima priorità si trova in testa alla lista
  - La `Enqueue` richiede tempo $O(n)$: i nuovi elementi vanno inseriti alla posizione corretta rispetto all'ordinamento

Il costo delle operazioni è sbilanciato: vi è la necessità di un implementazione che lo renda più simile

## 07 - Alberi e Heap tree, code di priorità

### Alberi

- Stuttura dati gerarchica, generazillazione delle liste, più successori per ciascun nodo, detti figli

- **Nodo**: elemento dell'albero
- **Arco**: collegamento tra due nodi
- **Radice**: nodo che si trova al livello più elevato della gerarchia(non è figlio di alcun nodo)
- **Foglia**:nodo che non ha figli
- **Nodo interno**: odo intermedio fra la radice e le foglie
- **Profondità**: distanza (in numero di archi) fra qualunque nodo e la radice
- **Altezza**: profondità massima delle foglie

### Nodi

Nodi contenitori di informazione, senza perdita di generalità possono contenere dei dati  di tipo `float`

Vedreno prossimamente quando tratteremo i dizionari, l'estensione al caso struttura *chiave/valore*

### Alberi generici, $k$-ari, binari

Gli alberi sono classificati attraverso il nuemero di figli
- nel caso il numero di figli è arbitrario
- altrimenti se è limitato al valore $k$ li chiamiamo alberi $k$-ari
- se $k=2$ si dicono *binari* e i figli sono, tipicamente denominati `Sinistro(n)` e `Destro(n)`

### Alberi: implementazione

**Vettore di *puntatori* ai figli**

```
typedef struct _nodo{
   float dato;
   struct _nodo** figli;
   int num_figli;
   struct _nodo* padre; /* opzionale */

}nodo_albero_generico
```

Osservare la notazione `struct _nodo**`, essa indica un puntatore(vettore) a puntatori

Se $k$-ario, già conosciamo la lunghezza dell'array `figli`, altrimenti nel caso generale dovremmo aggiungere alla `struct` anche la lunghezza del vettore (ossia il numero di figli di ciascun nodo) 

**Puntatore al primo figlio e lista di puntatori ai fratelli**
```
typedef struct _nodo{
   float dato;
   struct _nodo* primo_figlio;
   struct _nodo* fratello;
   struct _nodo* padre; /*opzionale*/
}nodo;
```

**Puntatori sinistro e destro per i binari**

```
typedef struct _nodo{
   float dato;
   struct _nodo* sinistroM
   struct _nodo* destro;
   struct _nodo* padre;/* opzionale */
}
```
#### Alberi completi e bilanciati


Gli alberi binari sono interamente descritti da due puntatori, al figlio sinistro e al figlio destro del nodo corrente (con valore `NULL` se essi non esistono).

- Un albero (binario) è detto **completo** se ogni nodo ha esattamente due figli, non vuoti
- Un albero (binario) è detto **completamente bilanciato** se, oltre ad essere completo, tutte le foglie hanno la stessa profondità
- Un albero (binario) di altezza $h$ è detto **completo a sinistra** se i nodi di profondità minore di $h$ formano un albero completamente bilanciato e se i nodi di profondita $h$ sono tutti accumulati a sinistra

**Limite superiore all'altezza**

L'altezza $h$ di un albero completamente bilanciato con $n$ nodi è $O(log\;n)$
- un albero completamente bilanciato di altezza $h$ ha $2^h -1$ nodi interni e $2^h$ foglie: ne deriva che la relazione tra l'altezza h e il numero di nodi è la seguente:
$$
2^h-1+2^h=2^{h+1} -1 \text{ pertanto} h = log\, (n+1)-1
$$

inoltre se $h$ è l'altezza di un albero completo a sinistra con $n$ nodi, allora anche in questo caso $h = O(log\; n)$
- se $m$ è il numero di nodi a profondità minore di $h$ si ha che
$$
h \leq log\,(m+1) -1 < log\, (n+1) -1 = O(log \;n)
$$

### Heap tree

Un **Heap tree** è un albero *binario completo a sinistra* che soddisfa la seguente proprietà (**heap property**):
1. è un albero vuoto oppure se `r` è la sua radice e `v_s` e `v_d` i suoi figli valgono `r->dato` $\geq$ `v_s->dato` e `r->dato` $\geq$ `v_d->dato`
2. la proprietà vale ricorsivamente per i sottoalberi radicati in `v_s` e `v_d`


![heaptree](img\heaptree.png)

Dove si trova il massimo dei valori?


#### Heap tree: rappresentazione implicita in array

Un albero *binario* completo a sinistra con $n$ può essere rappresentato in un array $t$ di dimensione $n$ con le seguenti convenzioni:
- $t[0]$ è il nodo radice
- Dato un qualunque nodi $i$ dell'albero `Sinistro(i) = 2 * i + 1` e ` Destro(i) = 2 * i +2`, `Padre(i) =`$\lfloor$` (i-1)/2`$\rfloor$

#### Code di priorità tramite Heap tree

Il fatto che l'altezza di un heap tree sia logaritmica ci consente di effettuare le operazioni `Enqueue` e `Dequeue` in tempo $O(log \; n)$


**`Enqueue`**
1. inseriamo un nuovo `n` come foglia, mantenendo l'heap tree completo a sinistra
2. confrontiamo la priorità del nodo `n` con quella del padre e scambiamo i due nodi se la *heap property* non vale (ovvero se `n` ha priorità maggiore di quella del padre)
3. ripetiamo il punto 2 finchè non giungiamo ad un nodo per cui la *heap property* è soddisfatta oppure quando `n` è salito fino alla radice

- Tempo $O(h) = O(log\; n)$, il numero di passi necessari per salire dalla foglia alla radice


**`Dequeue`**

1. Estraiamo l aradice(l'elemento di priorità più grande) e la scambiamo con la foglia più a destra `n` nell'ultimo livello(per mantenere l'heap teee completo a sinistra)
2. confrontiamo la priorita del nodo `n` con quella dei suoi figli e scambiamo `n` con il figlio di priorità massima se la *heap property* non vale (ovvero se `n` ha la priorità inferiore di quella dei figli)
3. ripetiamo il punto 2 finchè l l'*heap property* è soddisfatta oppure `n` è sceso fino ad una foglia

- Tempo $O(h) = O(log\;n)$, il numero di passi necessari per far scendere la nuova radice fino ad una foglia

#### complessità delle operazioni 

L'esecuzione di $k$ operazioni `empty`, `first`, `enqueue` o `Dequeue` su un heap tree contenente inizialmente $m$ elementi richiede tempo $O(k\; log\; n)$ dove $n = m+k$

**Dimostrazione**: `Empty` e `First` hanno, ovviamente, complessità costante, `Enqueue` deve verificare se l'array necessiti di essere raddoppiato (tuttavia la complessità ammortizzata è $O(1)$), inoltre ha bisogno di tempo $O(h)\leq o(log \; n)$

---  

## 08 - heap sort

### riepilogo degli allgoritmi visti

|   **Algoritmo**    |                                                **Idea**                                                 | **Caso Pessimo** | **Caso Ottimo** |
| :----------------: | :-----------------------------------------------------------------------------------------------------: | :--------------: | :-------------: |
| **Selection sort** | Cerco(seleziono) l'elemento minimo fra quelli rimasti da ordinare e lo scambio con l'elemento corrente  |     $O(n^2)$     |    $O(n^2)$     |
| **Insertion Sort** |                Cerco di inserire l'elemento corrente fra quelli precedenti, già ordinati                |     $O(n^2)$     |     $O(n)$      |
|  **Bubble sort**   | Effettuo più passaggi facendo *affiorare* gli elementi più grandi, finchè non sono necessari più scambi |     $O(n^2)$     |     $O(n)$      |


### Una variazione di selection sort

Lo schema di selection sort può essere opportunamente modificato per funzionare anche con l'elemento massimo, anzichè quello minimo

```
void SelectionSortMax(int a[], int n){
int indice_massimo, i;
   for (int i = n - 1; i > 0; i--){
      indice_massimo = CercaMassimoFinoA(a,n,i);
      Scambia(&a[i], &a[indice_massimo]);
   }

}

int CercaMassimoFinoA(int a[], int n, int i){
   int j, m = 0;

   for (j=1; j <= i; i++)
      if(a[m] < a[j])
      m = j;

return m;
}
```

La complessità è sempre $O(n^2)$

In particolare, il contributo alla complessità totale della funzione di ricerca del massimo $t(n,i)$ è lineare in $i(t(n,i))= O(i)$

È possibile diminuire tale complessità?
- esiste una struttura dati che consente di estrarre l'elemento massimo in modo più efficente?

### Heapsort: un algoritmo di ordinamento Ottimo

**Idea**: uso lo stesso schema del **selection sort** ma sfruttando una struttura dati più efficente per ottenere il massimo di un insieme di valori: utilizzando un **heap tree**(cfr.coda di priorità)

Schema concettuale:

1. costruisco un heap tree con i valori del vettore aggiungendone gli elementi uno alla volta(è come se facessi `Enqueue` su una coda di priorità in cui il valore di priorità coincide con il dato dell'array)
2. finchè ci sono elementi estraggo il massimo deall' heap tree e lo inserisco nella sua posizione definitiva nell'array ordinato(`Dequeue`)

### Heapsort: versione concettuale

```
Heapsort(v,n):
/* IN questa versione usiamo concettualmente tre strutture distinte:
   1. l'array originale v,
   2. una coda di priorità pq
   3. un array destinazione r
*/
pq = CreaCodaPriorita();
r = CreaArray (n);
for (i = 0; i < n; i++)
   Enqueue(pq, v[i]);
for (i = n-1; i >= 0; i--)
{
   r[i] = First (pq);
   Dequeue(pq);
}
/* r è il vettore ordinato*/
```

### Heapsort: complessità

- $n$ operazioni di `Enqueue` nell'albero, ciascuna costa $O(log\;i) \subseteq O(log\;n)$, dunque questa parte costa $O(log\;n) = O(n\,log\;n)$
- $n$ operazioni di `Dequeue` dall' albero, ciascuna delle quali ha  costo $O(log\;i)$, pertanto anceh questa parte costa $O(log\;n)$
- la complessità complessiva dell' algoritmo è dunque $O(log\;n)$, ossia Heap sort è un algortimo di ordinamento **ottimo**

### Hap sort: implementazione *in-place*

```
void heap_sort(float a[], int n)
{
   int i;
   for (i = 0; i<n; i++)
   {
   // di fatto  è equivalente ad effettuare un Enqueue()
      _hs_riorganizza_heap_enqueue(a, i+1, i);
   }
    i = n-1;
    while (i >  0){
      // e le due istruzioni seguenti sono equivalenti ad effettuare un Dequeue()
      _scambia(&a[0], &a[i]);
       i = i-1;
      _hs_riorganizza_heap_dequeue(a, i+1);

    }

}
```

```
void _hs_riorganizza_heap_enqueue(float a[], int n, int i){
   /*Enqueue*/
   while(i > 0 &&  a[i] > a[_hs_padre(i)]){
      _scambia(&a[i], &a[_hs_padre(i)]);
      i = _hs_padre(i);
   }
}

void _hs_riorganizza_heap_dequeue(float a[], int n){
   int i = 0;
   /*Dequeue*/
   while(_hs_sinistro(i) < n && i != _hs_migliore_padre_figli(a ,n ,i)){
      int figlio_migliore = _hs_migliore_padre_figli(a ,n ,i);
      _scambia(&a[i], &a[figlio_migliore]);
      i = figlio_migliore;
   }
}

```

```
int _hs_migliore_padre_filgi(float[a], int n, int i){
   int k = i;
   if(_hs_sinistro(i) < && a[k] < a[_hs_sinistro(i)])
      k = _hs_sinistro(i);
   if(_hs_destro(i) < && a[k] < a[_hs_destro(i)])
      k = _hs_destro(i);
   return k;
}
```

```
int _hs_padre(int i){
   return (i-1) / 2;
}

int _hs_sinistro(int i){
   return 2 * i + 1;
}

int _hs_destro(int i){
   return 2 * i + 2;
}

```

---

## 09 - divide et impera

- Questo paradigma(**divide and conquer**) è una metodologia generale per la soluzione di problemi che fa uso della ricorsione ed è strutturata in tre fasi:
  - **decomposizione**: identificazione di un (piccolo) numero di problemi dello stesso tipo, ciascuno definito su di un insieme di dati di dimensione inferiore a quello di partenza
  - **ricorsione**: soluzione ricorsiva di ciascun sottoproblema fino ad ottenere sottoproblemi di dimensioni tali da poter essere risolti direttamente
  - **ricombinazione**: combinazione delle soluzioni dei sottoproblemi per fornire una soluzione al problema di partenza

### Esempi di algoritmi divide et Impera

#### Ordinamento per fusione: merge sort

:bulb: **Idea**: decomporre il problema dell'ordinamento di una sequenza nel modo seguente:

- **decomposizione**: se la sequenza di due elementi viene divisa in due sotto-sequenze di lunghezza uguale(o quasi, a meno di un elemento)
1. *dividi a metà l'array*
- **ricorsione**: le due sottosequenze sono ordinate ricorsivamente applicando lo stesso algoritmo
2. *Ordina separatamente le due metà*
- **ricombinazione**: le due sottosequenze ordinate sono fuse(*merge*) in una sequenza ordinata
*3. FOndi le due metà*

##### Pseudocodice

```
void merge_sort(float a[], int sinistra, int destra){
   int centro;
   //caso di base, sinistra == destra, vettore con un elemento
      if(sinistra < destra){
         centro = (sinistra + destra) / 2;
         merge_sort(a,sinistra,centro);
         merge_sort(a,destra ,centro+1);
         merge(a, sinistra, centro, destra);
      }
}
```
**Idea per `merge()`: due mazzi di carte, ciascun mazzo ordinato
1. confronta la carta in cima di un mazzo con quella in cima all'altro
2. rimuovi la minima tra le due
3. se un mazzo si svuota, prendi le rimanenti carte dell' altreo mazzo nel loro ordine

Ad ogni confronto sistemiano una carta nella sequenza ordinata (tempo $O(n)$)

**funzione `merge`**
```
void merge(float a[], int sinistra, int destra, int centro){
   int i, k, k, n = destra - sinistra + 1;
   float *b = (float*)malloc(n*sizeof(float));
   i = sinistra; j= centro +1; k = 0;
   while (i<= centro && j <= destra){
      if (a[i] <= a[j]){
         b[k] = a[i]; i++;
      }else{
         b[k] = a[j], j++
      }
      k++
   }
   for (; i<= centro; i++,k++){
      b[k] = a[i];
   for(; j<= destra; j++, k++)
      b[k] = a[i];
   }
   //ricopia gli elementi da b ad a
   for(i = sinistra; i<= destra; i++)
      a[i] = b[i-sinistra];
   free(b);
}
```

##### equazione ricorsiva di complessità

$$
T(n) = \begin{cases}
O(1) \quad  se \; n\leq 1 \\
\underbrace{2T(\frac{n}{2})}_{chiamate\, ricorsive} \quad \underbrace{+O(n)}_{merge} \quad se \; n > 1
\end{cases}
$$

### Teorema fondamentale delle ricorrente (master theorem)

Data la relazione di ricorrenza
$$

T(n) = \begin{cases}
O(1) \quad se \; n\leq n_0 \\
\underbrace{\alpha T(\frac{n}{\beta})}_{chiamate\, ricorsive} \quad \underbrace{+O(f(n))}_{merge} \quad se \; n > n_0
\end{cases}
$$

con $f(n)$ non decrescente, $\alpha \geq 1$ e $\beta > 1$

Se esistono due costanti $\gamma > 0$ e $n_0^\prime$ tali che $\alpha f(\frac{n}{\beta}) = \gamma f(n)$ per ogni $n \geq n_0^\prime$ allora la relazione di ricorrenza ha le seguenti soluzioni:

1. $t(n) = O(f(n)) se \gamma < 1$
2. $T(n) = O(f(n) log_\beta n) $ se $\gamma = 1$
3. $t(n) = O(n^{log_\beta \ \alpha}$ se $\gamma > 1$

#### Analisi del MergeSort con il teorema fondamentale delle ricorrenze

- $\alpha = 2, \beta = 2, f(n) = n$ non decrescente

Proviamo a risolvere l'equazione in $\gamma$ e $n_0^ \prime$:

$$
\alpha f(\frac{n}{\beta}) = \gamma f(n) = 2f(\frac{n}{2}) = 2 * \frac{n}{2} = n
$$

Si ha che, $\alpha f(\frac{n}{\beta}) = n = \gamma \cdot f(n)$ per $\gamma = 1 \;e\; \forall n > n_0^\prime$

È dunque applicabile il secondo caso del teorema e la complessità è pertanto
$$
O(f(n)log_\beta \,n) = O(nlog_{\cancel{2}} n)
$$

### Ordinamento per distribuzione: QuickSort

```
void quick_sort(float v[], int sinistra, int destra){
   int pivot, rango;
   if (sinistra < destra){
      /* scegli pivot, ad esempio l'elemento a destra*/
      pivot = destra;
      rango = distribuzione(v, sinistra, pivotm destra);
      quick_sort(v,sinistra, rango -1);
      quick_sort(v, rango +1, destra);

   }
}
```

**distribuzione**
```
int distrubuzione(float v[], int sinistra, int pivot, int destra){
   if (pivot != destra)
      scambia(&v[pivot], &v[destra]);
   i = sinistra;
   j = destra - 1;
   while (i <= j){
      while ((i <= j) && (v[i] <= v[destra]))
         i++;
      while ((i <= j) && (v[i] >= v[destra]))
         j--;
      if (i< j){
         scambia (&v[i], &v[j]);
         i++; j--;
      }
   }
if (i != destra)
   scambia(&v[i], &v[destra]);

   return i;
}
```

#### quicksort:complessità

$$
T(n) = \begin{cases}
O(1) \quad se\; n \leq 1 \\
T(r) + T(n-(r + 1)) + O(n) se \; n > 1
\end{cases}
$$
- **caso peggiore** $r = 0$ e in tal caso $T(n) = O(n^2)$(il caso peggiore avviene se l'array è già ordinato in senso inverso e si sceglie il pivot più a destra)

Semplificando si ha:

$$
T(n) = \underbrace{T(0)}_{O(1)} + T (n-1) + O(n) = T(n-1) + O(n)
$$

e dunque 
$$
T(n) = \overbrace{T(n-1)}^{T(n-2)+c(n-1)} +cn = T(n-2) + c(n+(n-1)) =\dots = T(n-k) +c \sum_{i = 0}^{k} (n-i) = O(n^2)
$$

- caso migliore: $r = \frac{n}{2}$ e in tal caso $T(n) = 2T(\frac{n}{2})i O(n) = o(n\,log\;n)$
- anche in un caso molto sbilanciato $T(n) = T(\frac{9}{10}n)+ T(\frac{1}{10}n)+ O (n)$ è possibile dimostrare che $T(n) = O(n\,log\;n)$
- caso medio: è possibile provare che anche nel caso nedio la complessità è dell' ordine di $O(n\,log\;n)$
per mitigare la complessità del caso pessimo introduciamo un po' di **casualità**: scegliamo un valore casuale dell' array come pivot
- in questo modo il caso pessimo ha una probabilità infinitesima di accadere: si traterebbe di sbagliare tutte le scelte del pivot, con probabilità
$$
\frac{1}{n}\cdot \frac{1}{n-1}\cdot \dots \cdot \frac{1}{1} = \frac{1}{n!}
$$

#### Quickselect

Una variante dell' algoritmo consente di trovare l'elemento di rango $r \in 0,1,\cdots n-1$ in tempo medio/ottimo $O(n)$: ad esempio per trovare l'elemento mediano(ovvero di rango $r = \frac{n}{2}$)
```
float quick_select(float v[], int sinistra, int r, int destra){
   int pivot, rango;
   if (sinistra == destra)
      return v[sinistra];
   pivot = destra;
   rango = distribuzione (v, sinistra, pivot, destra);
   if(rango == r)
      return a[rango];
   if (rango > r)
      return quick_select(a,sinistra,r,rango-1);
   else 
      return quick_select(a, rango +1, r, destra);
}

```

##### Analisi di complessità del Quickselect

$$
t(n) = 
\begin{cases}
   O(1) \quad se \; n \leq 1 \\
   T(n-r-1) + O(n) se \; n > 1\\
\end{cases}
$$

Analogamente al `QuickSort`, il caso peggiore avviene quando $r = 0$ e la distribuzione dei valori minori e maggiori del pivot è completamente sbilanciata. Anche in tal caso, per espansione di $T(n-1)$
$$
T(n) = T(n-1) + c\cdot n = (t(n-2)+c \cdot (n-1)) + c\cdot n \\= ((T(n-3)+c\cdot (n-2))+c \cdot (n-1)) + c\cdot n = \dots \sum_{i = 0}^{n-1}c\;\cdot (n-1) = O(n^2)
$$

Tuttavia, nel caso ottimo in cui la distribuzione di valori divida l'array in due party uguali, l'espressione è la seguente:

$$
T(n) = T(\frac{n}{2}) + O(n)\text{ se } n>1
$$

pertanto applicando il teorema del maestro si ottiene: $\gamma = \frac{1}{2}< 1 $ e dunque $T(n) = O(n)$

Analogo risultato si ha anche nel caso più sfortunato in cui $T(n) = T(\frac{9}{10}n)+ O(n)$, perchè $\gamma = \frac{9}{10} <1 $ e dunque la complessità è la medesima.

Per evitare il caso pessimo (che ha, analogamente, probabilità molto piccola), è utile, anche in questo caso, la randomizzazione.

### Altri esempi di divide et impera

#### Moltiplicazione veloce di (grandi) interi

Vogliamo la rappresentazione e la manipolazione di numeri interi di dimensione arbitraria(oltre i limiti della rappresentazione interna binaria, tipicamente 64 bit)

- possiamo rappresentare i numeri con la loro sequenza di cifre, ad esempio in un array
- dobbiamo, però, definire gli algoritmi per le operazioni aritmetiche su di essi

**Ridefinizione delle operazioni**

**Somma**
$$

\begin{array}{r}
   & 2134 \\
+  & 3784 \\
\hline
   & 5918 \\
\end{array}
$$
Richiede tempo $O(max{n,m})$ con $n,m$ numero di cifre dei due numeri 
**Prodotto**
$$
\begin{array}{r}
   & 2134 \times 184 = \\
   & \phantom{0} \ 8536 \\
   & + 170720 \\
   & +213400 \\
\hline
   & 392656 \\
\end{array}

$$
Richiede $O(min(n,m)^2)$ con $n,m$ dimensioni dei due numeri

#### Prodotto di interi: limite inferiore alla complessità

**OSservazione**: il prodotto fra due numeri con $n$ cifre richiederà fino ad un massimo di $2n$ cifre per la sua rappresentazione

Questa osservazione è anche un limite inferiore alla complessità del problema del  calcolo del prodotto, infatti, qualunque algoritmo andremo a definire, sarà necessario quantomeno determinare il valore di ciascuna di queste cifre che sono $O(2n) = O(n)$.

Pertanto il limite inferiore di complessità del problema del calcolo del prodotto fra due numeri interi è $\Omega(n)$

**C'è spazio per dei miglioramenti rispetto alla complessità $O(n^2) dell'algoritmo classico

#### Moltiplicazione veloce di interi

Dati due numeri interi rappresentati con sequenze di $n$ cifre(eventualmente con degli $0$ a completamento di quello meno lungo), calcolarne il prodotto

Ogni numero intero $w$ può essere scritto cone $10^{\frac{n}{2}}\cdot w_s + w_d$ in cui le cifre sono partizionate in due metà
- supponiamo, per semplificare l'analisi, che $n$ sia pari, ma nel caso non lo fosse si può sempre aggiungere uno $0$ in testa al numero aumentandone le cifre

**Esempio**
$$
\lang 2,1,3,4\rang = 2134 = 10^2 \cdot 21 + 34 \text {e dunque  } w_s = \lang2,1\rang e w_d = \lang w_d\rang
$$

Dati due numeri $x$ e $y$ arbitrari di $n$ cifre, rappresentati attraverso la loro sequenza di cifre vale la seguente uguaglianza:

$$

x\cdot y = (10^{\frac{n}{2}}x_s+x_d)\cdot(10^{\frac{n}{2}}y_s+y_d) = 10^n \underbrace{x_s\cdot y_s}_{prodotto} + 10^{\frac{n}{2}}(\underbrace{x_s\cdot y_d}_{prodotto}+\underbrace{x_d\cdot y_s}_{prodotto})+ \underbrace{x_d \cdot y_d}_{prodotto}
$$

Possiamo applicare il paradigma **divide et impera** per la loro moltiplicazione:
- **Decomposizione**: se i due numeri $x$ e $y$ hanno almeno due cifre, dividerli come $x_s, x_d$ e $y_s, y_d$ aventi ciascuno metà delle cifre
- **ricorsione**: calcola ricorsivamente i prodotti $x_s \cdot y_s, x_s \cdot y_d, x_d \cdot y_s, x_d \cdot y_d$
- **ricombinazione**: combina i risultati attraverso l'uguaglianza
  - le operazioni di moltiplicazione per potenze di $10$ sono semplici spostamenti a sinistra nella sequenza, ovvero aggiunta di $0$ a destra
  
L'algoritmo esegue **quattro moltiplicazioni**(chiamate ricorsive) di numeri di $\frac{n}{2}$ cifre (a un costo $T(\frac{n}{2}$) e **tre somme** di  due numeri a $n$ cifre (a un costo O(n))

La moltiplicazione per $10^k$ è uno spostamento di cifre e riempimento con $0$ e costa $O(k)$, quindi al massimo $O(n)$ nel nostro caso

Il costo della decomposizione e ricombinazione è pertanto $O(n)$

L'equazione di complessità è dunque:

$$
T(n)= 
\begin{cases}
O(1) \quad \text{se }n \leq 1 \\
4T(\frac{n}{2})+ O(n) \quad \text{se } n > 1
\end{cases}
$$

Risolviamo l'equazione con il teorema del maestro:
$$
T(n)= 
\begin{cases}
O(1) \quad \text{se }n \leq 1 \\
4T(\frac{n}{2})+ O(n) \quad \text{se } n > 1
\end{cases}
$$

$\alpha = 4, \beta = 2, f(n) = n$, risolviamo l'equazione in $\gamma $ (e $n_0^{\prime}$)

$$
\alpha f(\frac{n}{\beta}) = \gamma f(n)\forall \; n > n_0^{\prime} \\
\text{ossia}\\
\underbrace{\cancel{4}}_2 \frac{\cancel{n}}{\cancel{2}} = \gamma \;\cancel{n}\; \forall \;n > 0
$$

ne deriva che il caso del teorem applicabile è il 3: $O(n^{log_2 4}) = O(n^2)$

**Non ci abbiamo guadagnato nulla**

#### Moltiplicazione veloce di interi

Osserviamo però che nell'uguaglianza:
$$
x \cdot y = 10^n x_s\cdot y_s + 10^{n/2}(x_s \cdot y_d + x_d \cdot y_s) + x_d \cdot y_d

$$

il valore del termine intermedio ($x_s \cdot y_d + x_d \cdot y_S$) può essere calcolato parendo dagli altri termini, specificatamente:

$$
x\cdot y = 10^m \underbrace{x_s \cdot y_s}_{\text{prototto}} + 10^{n/2}(\underbrace{x_s \cdot y_s}_{\text{già calcolato}}+ \underbrace{x_d \cdot y_d}_{\text{già calcolato}}+ \underbrace{((x_s -x_d)\cdot (y_s - y_d))}_{\text{prodotto}}+ \underbrace{x_d \cdot y_d}_{\text{prodotto}})
$$

Quindi il numero di prodotti (chiamate ricorsive) da calcolare diventa **tre**, mentre le somme (e sottrazioni) sono salite a **sei**

#### Moltiplicazione veloce di interi
 L'aggiunta di (un numero costante di) addizioni non ha effetti sull'equazione ricorsiva (il costo era $O(n)$ e rimane tale), tuttavia il fattore moltiplicativo nel numero di chiamate diminuisce:

$$
T(n) = 
\begin{cases}
   O(1) \quad \text{se }n \leq 1 \\
   3T(\frac{n}{2})+ O(n) \text{se } n > 1 \\
\end{cases}
$$


Risolvendo in $\gamma$ (e $n^{\prime}_0$) si ottiene $3\frac{\cancel{n}}{2}= \gamma \cancel{n} \forall n > 0 $ ovvero $\gamma = \frac{3}{2}$, il caso del teorema del maestro applicabile è sempre lo stesso, però: $O(n^{log_2 \;3}) = O(n^{1.585})$ che è più efficente di $O(n^2)$

l'algoritmo in questa forma è chiamato anche **algoritmo di karatsuba** 

### Algoritmi ricorsivi su alberi

Gli alberi (binari) sono strutture inerentemente ricorsive: sono strutturari in forma di nodi che inducano due **sottoalberi** radicati come figlio sinistro e destro del nodo stesso

Questa suddivisione è particolarmente adatta per un'approccio *divide et impera*:
- la **decomposizione** consiste nei due sottoalberi(il caso di base è l'albero vuoto)
- La **ricorsione** consiste nell'esecuzione in ciascuno dei due sottoalberi separatamente, ottenendo (al più) due risultati intermediù
- La **ricomposizione** consiste nella combinazione dei due risultati


Schema(in pseudocodice):
```
Decomponi(r):
if(r == NULL)
   return caso_base;
risultato_sx = Decomponi(r->sinistro);
risultato_dx = Decomponi(r-> destro);
return Ricomponi(risultato_sx, risultato_dx);
```

Complessità:$T(n) = \begin{cases}
   O(1) \quad \text{se }n = 0 \\
   T(s) + T(n-s-1) + O(1) \quad \text{se } n > 0
\end{cases} \text{con }s\text{ numero di nodi}$
del sottoalbero sinistro (e di conseguenza $n-s-1$ sono i nodi del sottoalbero destro)

#### Esempio: contare i nodi
```
int conda_nodi(nodi_albero* r){ // Decomponi
int nodi_sx, nodi_dx;
if (r == NULL)// caso base
   return 0;
nodi_sx = conta_nodi(r->sinistro); //Chiamata ricorsiva sx
nodi_dx = conta_nodi(r->destro);//chiamata ricorsiva dx
return nodi_sx + nodi_dx + 1;
}
```
#### Esempio: calcolo della profondità
Schema con parametro aggiuntivo, per accumulazione a partire dalla radice. L'altezza di un albero è il  numero massimo di archi (connessioni) dalla radice ad una foglia.

```
int altezza(nodo_albero* r, int a){ // decomponi
int altezza_sx, altezza_dx;
if(r == NULL)
   return a-1;//l'arco per arrivare oltre l'albero non va contato
altezza_sx = altezza(r->sinistro, a+1);
altezza_dx = altezza(r->destro, a+1);
return max(altezza_sx, altezza_sx);
}

 // Chiamata iniziale altezza (r, 0), con r radice dell'albero

```
#### Esempio: visita anticipata

Schema di elaborazione di tutti i nodi dell' albero:
```
void visita_anticipata(nodo_albero* r, void(*elabora)(nodo_albero*)){
   if (r == NULL)
   return;
   elabora(r);
   visita_anticipata(r->sinistro, elabora);
   visita_anticipata(r->destro, elabora);
}
```

`elabora(nodo_albero*)` è una funzione che verrà passata come argomento ed effettuerà qualche elaborazione sul contenuto di ciascun nodo(ad esempio potrebbe stampare o accumulare dopo qualche trasformazione in qualche variabile globale)

In C è possibile passare  delle funzioni a degli algoritmi generici (così come è la visita) per definire delle **meta**-strategie indipendenti dall'operazione

#### Esempio di funzione di elaborazione

```
void stampa_dato(nodo_albero* r){
   printf("%f", r->dato);
}

   // la funzione di visita che applica la stampa del dato a ciascun nodo
   //può essere invocata nel seguente modo:
   visita_anticipata(albero.radice, stampa_dato);
```

#### Visita simmetrica e posticipata

```
void visita_simmetrica(nodo_albero* r, void(*elabora)(nodo_albero*)){
   if (r == NULL)
   return;
   visita_simmetrica(r->sinistro, elabora);
   elabora(r);
   visita_simmetrica(r->destro, elabora);
}
```
---
```
void visita_posticipata(nodo_albero* r, void (*elabora)(nodo_albero)){
   if (r == NULL)
   return;

   visita_posticipata(r->sinistro, elabora);
   visita_posticipata(r->destro, elabora);
   elabora(r);
}
```

#### Algoritmi su alberi: complessità

La forma delle equazioni di complessità degli algoritmi ricorsivi su alberi è la seguente:
$$
T(n)= \begin{cases}
   O(1) \quad \text{se } n = 0 \\
   T(s) + T(n-s-1)+ O (1) \quad se n> 0\\
\end{cases}
$$

Con $s$ numero di nodi del sottoalbero sinistro.
È possibile dimostrare formalmente che $T(n) = O(n)$(una dimostrazione per induzione proposta nel testo lo fa dimostrando che $T(n) \leq 3cn$), tuttavia è sufficente osservare che ciascun nodo dell'albero viene considerato da questi algoritmi **una e una sola volta**, pertanto la complessità sarà proporzionale al numero di nodi dell'albero


## 10 - dizionari e le loro implementazioni

### Motivazioni

Supponiamo di avere i seguenti dati, relativi ai saldi di un insieme di conti correnti bancari:

```
# Numero_conto, Saldo
12345, +2314.25
2134, +127.23
90213, +235.12
5421, -25.62
```

Come li rappresentiamo in memoria se il mio obiettivo è effettuare l'aggiornamento del saldo di un determinato conto?


Una soluzione può essere  quella di utilizzaer  un array di `struct` in cui vengono caricati i dati dal file e poi su di esso viene effettuata la ricerca del conto da aggiornare:


```
# Numero_conto, Saldo
12345, +2314.25
2134, +127.23
90213, +235.12
5421, -25.62
```


```
typedef struct{
   int numero_conto;
   float saldo;
}conto_corrente;
conto_corrente conti[100];
```
Tralasciandoil tempo necssario per il caricamento del file in memoria, quale sarebbe la migliore strategia per realizzare l'operazione di ricerca del conto e di aggiornamento?

E quale sarebbe la complessità di questa operazione espressa in termini di $n$, quantità di conti?

### Dizionari

Struttura dati astratta che ci consente di rappresentare **collezioni di elementi indicizzabili**, ovvero delle **corrispondenze** fra un dato detto **chiave** e il **valore** ad essa associato.
Possono rappresentare:
- degli "array sparsi", con idici non necessariamente contiguim es. un array `a[3], a[5], a[8]` ma non gli altri
- delle corrispondenze con indici non int, es. un nome `["mario rossi"]`
- degli "insiemi" qualora il solo campo chiave sia significativo

Anche le sequenze lineari $a_0, a_1, \dots$ rappresentano delle corrispondenze, però:
- le chiavi sono vincolate **esattamente** agli interi $0,1,\dots,n-1$
- tutti gli elementi compresi fra $0$ e $n-1$ sono **obbligatoriamente presenti** nella corrispondenza

#### izionari: struttura del dato

Assumiamo che i dati siamo composti da elementi con campo `chiave` e un insieme di informazioni *satellite* (che dipendono dall'applicazione) che per semplicità supponiamo essere un dato di tipo `float`
- siamo interessati all' operazione di **ricerca** del dato corrispondente alla **chiave** e al reperimento delle relative informazioni satellite
- *il tipo di dato della chiave*, denotato con $U$, può essere arbitrario (`int`, stringhe, ecc.)

```
typedef struct {
   int chiave; 
   float dato;
}elemento_dizionario;
```
```
typedef struct{
   char* chiave;
   struct impiegato dato;
}elemento_dizionario;
```
#### dizionario: operazioni di base

Dato un  dizionario `d` sono  definite le seguenti operazioni:
- `ricerca(d, k)` cerca e restituisce un puntatore all' elemento `e` take che `e->chiave` $=k\in U$(restituisce `NULL` se non esiste)
- `successore(d, k)` restituisce l'elemento la cui chiave è immediatamente successiva al valore $k$ nell'ordinamento(l'elemento di chiave $k$ se essa non esiste)
- `intervallo(d ,k1 ,k2)` restituisce la sequenza di elementi le cui chiavei $k$ sono comprese in `k1` $\leq k \leq$`k2.
- `rango (d,k)` restituisce il numero di elementi la cui chiave viene prima di $k$ nell' ordinamento

#### implementazione con sequenze lineari

Come visto all'inizio, un dizionario può essere implementato attraverso sequenze lineari(liste, liste doppie o array dinamici) ,modificando opportunamente il tipo di dato memorizzato(usando`elemento_dizionario` invece di float)

È possibile, opzionalmente, mantenere gli elementi della sequenza **ordinati** per chiave, qualora fossero necessarie le operazioni aggiuntive
- Ciò migliora la complessità dell'operazione di ricerca solo nel caso dell' implementeazione con array, mentre con le listr non apporta nessun beneficio
- in ogni caso, però semplifica l'implementazione delle operazioni `predecessore()`, `successore()` e `intervallo()`


### Alberi binari di ricerca

Un **albero binario di ricerca**(ABR) è un albero bianrio che soddisfa la seguente proprietà:
- è un albero vuoto, oppure se `r` è la sua radice vale `r->sinistro->chiave` < `r->chiave` e `r->chiave` < `r->destro->chiave`
- la proprietà vale ricorsivamente per i sottoalberi radicati in `r->sinistro` e `r->destro`

**Assunzione**: un solo nodo con un data chiave

La struttura dell'albero è quella dettata dalla proprietà dell' ABR

Dove si trova la chiave con valore minimo dell' ABR? E quella con il valore massimo?
Nelle nostre analisi ignoreremo il dato, poichè l'informazione significativa per la ricerca è quella della chiave

![abr](img\abr.png)

#### visite su alberi binari di ricerca

Nel caso di un albero binario di ricerca, la visita `simmetrica` elabora gli elementi in ordine di chiave crescente(attenzione, sul libro è indicato scorrettamente `anticipata`)

```
int ordine; // uso una variabile globale
void stampa_ordine(nodo_albero* r){
   printf("%d, $d", ordine, r->chiave);
   ordine++;
}

void visita_simmetrica(nodo_albero* r, void(*elabora)(nodo_albero*)){
   if (r == NULL)
   return;
   visita_simmetrica(r->sinistro, elabora);
   elabora(r);
   visita_simmetrica(r->destro, elabora);
}

ordine = 1;
visita_simmetrica(albero.radice, stampa_ordine);
```

![abr2](img\abr2.png)

Risultato: ` (1, 3) (2, 8) (3, 9) (4, 10) (5, 12) (6, 17) (7, 20)`

#### ricerca negli alberi binari di ricerca

```
nodo_albero*  ricerca(nodo_albero* r, int chiave){
   if (r== NULL)
   return NULL;
   if (chiave == r->chiave)
   return r;
   else if (chiave < r->chiave)
      return ricerca(r->sinistro, chiave);
   else
    return ricerca(r->destro, chiave);

}
```

L'operazione di ricerca è guidata dalla struttura dell' albero: non è necessario Complessità $O(h)$ con $h$ altezza dell'albero(e dunque $O(log\;n)$se completo)

![abr3](img\abr3.png)

#### Inserimento negli alberi binari di ricerca

```
nodo_albero* inserisci(nodo_albero* r, int chiave, float dato){
   if (r == NULL)
      return crea_nodo_albero(chiave, dato);
   else if(chiave < r->chiave)
      r->sinistro = inserisci(r->sinistro, chiave, dato);
   else if(chiave > r->chiave)
      r->destro = inserisci(r->destro, chiave, dato);
   else
   r->dato = dato;
   return r;
}
```
Segue la struttura dell'albero e inserisce il nuovo nodo come foglio.L'assunzione è che vi sia un solo nodo con una data chiave, pertanto in caso sia già presente l'operazione aggiorna il dato.

Complessità $O(h)$ con $h$ altezza dell'albero

![abr4](img\abr4.png)

Per la struttura dell'operazione di inserimento (il nuovo nodo è sempre inserito come foglia)l'albero potrebbe risultare particolarmente sbilanciato (e dunque $h = O(n)$, annullando qualunque beneficio ad usare an albero invece di una sequenza) 


![abr5](img\abr5.png)

#### cancellazione negli alberi binari di ricerca
```
nodo_albero* cancella(nodo_albero* r, int chiave){
   if(r == NULL)
   return r ;
   if(r->chiave == chiave){
   if (r->destro == NULL)
      r = r->destro;
   else if(r-> destro == NULL)
      r = r->destro;
   else {
      w = minimo_sottoalbero(r->destro);
      r->dato = w->dato;
      r->destro = cancella(r->destro, w->chiave);
   }
   } else if(chiave < r->chiave)
   r->sinistro = cancella(r->sinistro, chiave);
   else
   r->destro = cancella(r->destro, chiave);
   return r;
}
```

```
nodo_albero* minimo_sottoalbero(nodo_albero* r){
   while(r->sinistro != NULL)
   r = r->sinistro;
   return r;
}
```

![abr 6](img\abr6.png)

Operazione immediata se operata su un nodo con un solo figlio(sostituisce il nodo con il figlio), più complessa nel caso di un nodo con entrambi i filgi. Complessità $O(h)$

### Alberi AVL

Si tratta di alberi **1-bilanciato**, |`altezza(r->sinistro)`-`altezza(r->destro)`|$\leq 1$

:bulb: **idea di base**: quando a seguito dell' inserimento l'albero si sbilancia di più do un livello, effettuare delle rotazioni per riequilibrarne l'altezza

![avl1](img\avl1.png)


Alberi AVL: rotazioni

Per le rotazione possono essere classificati 4 casi: Sinistro-Sinistro, Sinistro-Destro, Destro-Sinistro, Destro-Destro, $u$ è il nodo critico, ovvero il nodo al livello di profondità

#### AVL:cancellazione

È possibile trattare il caso della cancellazione in un AVL mantenendo l'altezza bilanciata, tuttavia l'algoritmo risultante è particolarmente complesso

Usiamo un' idea alternativa per la cancellazione: utilizzare la **lazy deletion**, ovvero marcare **logicamente** un nodo come cancellato(attraverso un flag booleano) invece di eliminarlo fisicamente dall'albero

- il nodo "cancellato", deve rimanere comunque nell'albero come guida per la ricerca

Si osservi che, un numero di nodi cancellati anche se pari a metà dei nodi dell'albero contribuisce al più di un livello(dunque un valore costante) all'altezza dell'albero stesso:possiamo scegliere tale valore come livello di soglia

Analogamente al caso degli array dinamici, quando il numero di nodi cancellati supera la metà dei nodi dell'albero, esso viene ricreato da zero includendo solamente i nodi non cancellati ed eleiminando l'albero originale

Il costo ammortizzato di tale operazione è pari a $O(log\;n)$
infatti, prima di effettuare l'operazione di creazione di un nuovo albero si sono effettuate $\frac{n}{2}$ cancellazioni sulle quali *spalmare* il costo dell'operazione
- la componente di costo relativo a questa operazione è la ricerca dell'elemento contenente la chiave da eliminare, avente costo $O(log\; n)$
 
L'operazione di copia dei nodi(non cancellati) dell'albero in un nuovo albero richiede tempo $O(n\,log\;n)$, pertanto, **ammortizzando** tale costo sulle $\frac{n}{2}$ operazioni di cancellazione otteniamo che il costo di un'operazione di cancellazione è pari a $\frac{O(n\,log\, n)}{n/2}$

### tabelle hash


Le funzioni **hash** (polpettone) soon delle funzioni con svariati utilizzi in informatica, ad esempio in crittografiad

- $h(m) = c$, è facile da calcolare ma è molto difficile calcolarne l'inversa $h^{-1}(c)$ per ricostruire il messaggio originale

Esempi:

- $h(k) \text{ mod } m$, mappa gli $n$ elementi $k \in \{e_1,e_2,\dots, e_n\}$ in $0,\dots, m-1$.
- $H (k) = k_0\, \oplus\dots\oplus k_{s-1}$ calcola lo XOR binario fra gli $s$ blocchi di bit(di pari lunghezza) di cui è composta la chiave $k$,mappando gli elementi in $=,\dots, |k_i|-1$ ne esistono di più sofisticate, appunto, per la crittografia(`md5`, `sha`)
#### Dizionari: implementazione con tabelle hash

le funzioni hash possono essere utillizzate per implementare un dizionario, in cui $n$ elementi del dizionario sono memorizzati in un array di $m$ elementi, ciascuno di essi alla posizione $h(k)$(detto**tabella hash**)

Ovviamente questo funziona se $n = O(n)$ e la funzione $h(k)$ è **perfetta**, ossia non genera alcuna collisione ($k \neq k^{\prime}$e $h(k) = h(k^{\prime})$)
- in tal caso, la complessità delle operazioni è $O(1)$, posto che indichiamo con un booleano la presenza o meno di un dato nella tabella

#### Dizionari: implementazione con tabelle hash con liste di trabocco

Nel caso generale ciò non si verifica, pertanto si utilizzano delle tabelle con **liste di trabocco**

Esempio con $h(k) =$`k % 5` e insieme di chiavi $\{3,13,4,1,9,7\}$


![hash1](img\hash1.png)

#### Dizionari: implementazioni con tabelle hash con liste di trabocco

```
elemento_dizionario* ricerca(tabella_hash* tabella, int chiave){
   int h = hash(chiave);
elemento_dizionario* p;
p = ricerca_in_lista(tabell[h], chiave);
if (p != NULL)
   return p->datp
else
return NULL;
}
```

```
void inserisci(tabella_hash* tabella, int chiave, float dato){
   if (ricerca(tabella, chiave) == NULL){
      h = hash(chiave);
      aggiungi_in_coda(tabella[h], chiave, dato);
   }
}
```

```
void cancella(tabella_hash* tabella, int chiave){
if(ricerca(tabella, chiave)!= NULL){
   h = hash(k);
   cancella_elemento_lista(tabella[h], chiave, dato);
}
}
```

La complessià delle operazioni è proporzionale alla lunghezza $l$ della lista, $O(l)$
- ovviamente nel caso peggiore la funzione *hash* calcola lo stesso indice per tutte (o quasi) le chiavi e dunque la lunghezza è $l = O(n)$ così come la complessità

In un caso non così patologico, tuttavia possiamo assumere che la funzione di *hash* distribuisca in modo uniforme le chiavi fra i vari indici della tabella, in tal caso la lunghezza media della lista sarà $l = O(\frac{n}{m})$

Indicando con $\alpha = \frac{n}{m}$ il cosiddetto **fattore di carico** della tabella hash, possiamo esprimere la complessità delle operazioni nella forma $O(1+\alpha)$, ovvero costante a meno del fattore di carico

#### Tabelle hash con indirizzamento aperto

Un'alternativa all'uso delle liste di trabocco consiste nel utilizzare una tabella con $m$ elementi e più funzioni di hash alternative: se la cella della tabella risulta già occupata, si proverà con un'altra funzione a calcolare una posizione alternativa.

Nel caso dell'**indirizzamento aperto** è data una *famiglia* di $m$ funzioni hash $h_i(k)$ che vengono provate(nell'ordine di $i$ crescente). Ciascuna di tali funzioni devono generare una permutazione degli indici.

**Esempi di famiglie di funzioni di hash**.

- $h_i(k) = (h^{\prime}(k) +i)\%m$ **scansione lineare**
- $h_i(k) = (h^{\prime}(k)+ ai^2 +bi +c)\%m$ **scansione quadratica**
- $h_i(k) = (h^{\prime}(k) +i \cdot h^{\prime \prime}(k))\%m$ **scansione basata su hash doppio**

:warning: A differenza dell' implementazione con liste di trabocco se la tabella è (quasi) piena non è possibile aggiungere un nuovo elemento.

**esempio**


![hash esempio](img\hashaperto.png)

#### tabelle hash con indirizzamento aperto: implementazione in C

```
elemento_dizionario* ricerca(tabella_hash* tabella, int chiave)
{
   for (int i = 0; i < m; i++){
      h = hash[i](chiave);
      if (tabella[h]== NULL)
      return NULL;
      if (tabella[h]->chiave == chiave) 
      return tabella[h];
   }
   return NULL;
}
```
```
void inserisci(tabella_hash* tabella, int chiave, float dato){
   elemento_dizionario*e;
   if(ricerca(tabella,chiave) == NULL){
      i = 0;
      e = crea_elemento(chiave, dato);
      do{
         h= hash[i](chiave);
         if(tabella[h] == NULL)
         tabella [h] = e;
         i++;
      }while(tabella[h] != e);
   }
}
```

#### Tabelle has con indirizzamento aperto: analisi

Nell' analisi della complessità ci concentriamo nella misurazione delle operazioni di accesso alla tabella, assumendo che il calcolo della funzione hash richieda tempo costante.

In generale, nel caso pessimo, tutte le operazioni richiedono tempo $O(m)$, necessario a provare tutte le $m$ funzioni di hash per trovare l'elemento cercato(eventualmente da eliminare) o determinare una cella vuota per l'inserimento.

Cerchiamo di fare un'analisi più accurata nel caso medio

Per ciò che riguarda il numero di accessi dell'operazione di ricerca e di cancellazione in media saranno necessari $\frac{n}{m}= \alpha$ operazioni di accesso, nell'ipotesi che per ogni chiave $k$, $h_i(k)$ sia una delle $m!$ permutazioni degli indici generata in modo casuale e uniforme

Per l'operazione di inserimento l'analisi è leggermente più complessa.

#### Tabelle has con indirizzamento aperto: analisi dell' inserimento

Esprimiamo la funzione di complessità come$T(n,m)$, numero di accessi alla tabella effettuati per trovare una cella vuota in una tabella di $m>n$ posizioni
$$
t(n,m)\begin{cases}
   0 \quad \text{se }n = 1 \\
   1 + T(n-1, m-1) \quad \text{se }n >0 \text{per un numero di volte pari a }\frac{n}{m}\\
   1 \quad se n> = \text{per un numero di volte pari a }\frac{m-n}{m}
\end{cases}
$$

Per $T(0,m)$, la tabella è vuota e l'operazione accede direttamente ad una cella disponibile.
In caso contrario, per $m-n$ volte su $m$ abbiamo un solo accesso quando la cella a cui si accede è disponibile, mentre per $n$ volte su $m$ la cella non sarà disponibile e dunque sarà necessario effettuare ulteriori $T(n-1, m-1)$ accessi(abbiamo escluso un elemento tra quelli possibili e proviamo una funzione hash in meno)

Possiamo esprimere la relazione con il valore atteso $T(n,m)$ nel caso $n>0$:

$$
\mathbb{E}[T(n,m)]= \frac{m-n}{n}\cdot 1 + \frac{n}{m}\cdot(1+t(n-1, m-1)) = 1+ \frac{n}{m}T(n-1, m-1)
$$

È facilmente dimostrabile per induzione su $m > n > 0$ che $T(n,m) \leq \frac{m}{m-n}$ da cui deriviamo
$$
T(n,m)\leq \frac{m}{m-n}= \frac{1}{1-\frac{n}{m}} = \frac{1}{1-\alpha}= O(1)

$$
Ovvero, il numero di accessi per l'inserimento risulta essere, in media, costante.

## 11 - algoritmi greedy

Gli algoritmo "**greedy**" o "**ingordi**" sono degli algoritmi iterativi che a ciascun passo, fra un insieme di scelte, scelgono sempre la **migliore** rispetto alla situazione corrente(**migliore localmente**)
- non è detto che questa porti a una soluzione **globalmente** migliore

Questi algoritmi, in generale, **costruiscono** una soluzione $s$ aggiungendone un frammento $a_i$ alla volta.

Il problema è, di solito, di **ottimizzazione**, del tipo $min_s\in f(s)$
- l'algoritmo è guidato da una funzione $h: A \rightarrow \mathbb{R}~{\geq 0}$ che consente di misurare l'**appetibilità** di ciascun frammento della soluzione e, di conseguenza, di ordinarli per valori crescenti(l'obiettivo dell'ottimizzazione è la minimizzazione)
- la funzione $h$ è detta **euristica**

### Algoritmi greedy

Uno schema dell'algoritmo **greedy** può essere il seguente


```
Greedy (A,h);
s= /*insieme_vuoto*/
/*Ordina gli elementi di A utilizzando il criterio di ottimalità h(a[i])*/
Ordina(A,h);
for(i = 0;i < n; i++)
   if(Unione(s, a[i])è una soluzione)
   s = Unione(s,a[i]);
   restituisci s come soluzione
```

#### Algoritmi greedy: dipendenza dalla soluzione

In alcuni casi, il criterio di ottimalità può cambiare durante la costruzione della soluzione, ad esempio, perchè dipende da degli elementi già inseriti nell' insieme. In altri termini la funzione euristica dipende anche dalla soluzione finora costruita$f: A \times S \rightarrow \mathbb{R}^{\geq 0}$

```
Greedy(A,h);
s = /*insieme vuoto*/
pq = CreaCodaPriorità();
for(i = 0; i < n; i++)
//inserisce l'elemento a[i]
//con valore di priorità pari alla
//stima dell'euristica a soluzione vuota
Enqueue(pq, h(a[i], {}), a[i]);

while(!Empty(pq)){
   frammento = First(pq);
   if(Unione(s,frammento) è una soluzione)
   s = Unione(s,frammento);
   for (f = /* tutti i frammenti per cui la priorità può essere variata*/)
   AggiornaPriorità(pq,h(f,s),f);
}
 // restituisci s come soluzione

```

È possibile adattare lo schema algoritmico per tenere conto, ad esempio memorizzando i frammenti della soluzione in una **coda di priorità**.

Il valore di priorità associato a ciascun frammento ancora in coda, se potenzialmente variato a seguito della nuova soluzione, dovrà essere modificato.

## Problema di selezione delle attività

È dato un insieme $S$ di possibili **attività**(produzioni, pratiche da sbrigare, lezioni da svolgere) che debbano essere eseguite su di una **risorsa** (macchinario, esecutore umano, aula). La risorsa può essere utilizzata solo per un'attività alla volta.

Ciascun attività $a \in S$ è definita attraverso due valori interi $a.start$e $a.finish$ che corrispondono agli istanti temporali in cui, qualora selezionata, inizia e termina.

Supponiamo che tali istanti siano degli interi..

Due attività $a$ e $b$ si dicono **compatibili** se non si sovrappongono, ossia $a.start\geq b.finish$ oppure $b.start \geq a.finish$

Il **problema di selezione delle attività** consiste nel selezionare, fra quelle disponibili, il **massimo** numero possibile di attività mutualmente compatibili.

**Esempio**

![attivita1](img\attivita1.png)

**Soluzioni**

![attivita2](img\attivita2.png)

Le soluzione al problema cono sottoinsiemi di $A$, pertanto il numero di possibili soluzioni al problema è $|\mathscr P(A)|= 2^{|A|}$. Ovviamente non tutte queste soluzioni sono valide, ma questo rende impraticabile la strategia "genera e verifica".

Con l'idea di utilizzare un approccio **greedy** andiamo a cercare una possibile euristica $h:A\rightarrow \mathbb R^{\geq 0}$ che induce un ordine delle attività con la speranza che possa essere quello ottimale.

Per ciascuna euristica cercheremo di costruire un controesempio, se esiste, relativamente alla sua ottimalità(ovvero un caso in cui se applicata non porta al risultato con il maggior numero di attività selezionate).

#### Euristica 1: minimo tempo di inizio :x:

$$
h(a)= a.start
$$

Questa euristica non è ottimale: si può costruire, infatti, il seguente controesempio:

![euristica1](img\euristica1.png)

Chiaramente, sarebbe preferibile  eseguire le quattro attività $1\{a,b,c,d\}$ che iniziano dopo piuttosto che la sola attività $\{e\}$

#### Euristica 2: intervallo più piccolo :x:

$$
h(a)= a-finish - a.start
$$
Anche questa euristica non è ottimale: si può costruire, infatti, il seguente controesempio:

![euristica2](img\euristica2.png)

 Chiaramente, sarebbe preferibile eseguire le attività $\{a,b\}$ sebbene siano più lunghe piuttosto che la sola attivita $\{e\}$

 #### Euristica 3: numero inferiore di conflitti :x:

$$
h(a) = |\{b:a.finish \geq b.start \land a.start\leq b.finish\}|
$$

Anche questa euristica non è ottimale: si può costruire, infatti, il seguente controesempio:

![euristica3](img\euristica3.png)

Chiaramente, sarebbe preferibile eseguirele attività $\{a,b,c,d\}$ anche se esse sono in conflitto con ben tre altre attività piuttosto che la sola attivita $\{f\}$

#### Euristica 4: minimo tempo di fine :white_check_mark:

$$
h(a) = a.finish
$$

![euristica4](img\euristica4.png)

Questa euristica sembra essere ottimale, ed infatti è possibile provarlo formalmente(la dimostrazione è per induzione sulla lunghezza dell'insieme di attività selezionate).

#### Selezione delle attività: esempio di esecuzione

![selattiv1](img\selattiv1.png)

Il primo elemento a essere inserito è $A_7$ perchè inizialmente nessun elemento è presente nella soluzione e dunque in conflitto con esso. Il prossimo candidato all'inserimento è $A_2$ che tuttavia è in conflitto con $A_7$ e deve essere scartato.

![selattiv2](img\selattiv2.png)

L'elemento preso in considerazione successivamente è $A_{12}$ che non è in conflitto con $A_7$ e quindi può essere inserito

![selattiv3](img\selattiv3.png)


Siamo giunti a considerare $A_6$ per l'inserimento: esso è in conflitto con $A_{12}$ e pertanto lo saltiamo così come $A_8, A_{11}, A_9, A_5 \text{e} A_1$ rispetto a $A_{12}$ L'attività $A_4$ invece non è in conflitto con nessuno dei membri dei $s$ per cui la possiamo inserire.

![selattiv4](img\selattiv4.png)

Tutti gli elementi sono in conflitto con $A_4$ oppure anche con $A_{12}$ per cui non verranno inclusi.

![selattiv5](img\selattiv5.png)

Il risultato è pertanto: $s: \{A_7,A_{12},A_4\}$

#### Selezione delle attività: osservazioni

In questo caso l'ordinamento fra le componenti delle soluzioni è **statico**: dipende solo dal valore `finish` dell'attività e non cambia con l'aggiunta di elementi alle soluzioni.

Tuttavia, alcune attività non sono inserite perchè **non compatibili**, esse vengono semplicemente ignorate.

Nel caso del problema considerato l'euristica è ottima, ma basta modificare il problema introducendo dei pesi $\omega_i$ per le attività (ad esempio dei profitti) e cercare di massimizzare il profitto complessivo delle attività selezionate $\sum a_i \in S\; \omega_i$ perchè questa euristica non sia più quella ottima in questo caso(il problema di **selezione delle attività pesate** non è risolubile esattamente attraverso un algoritmo greedy).

La complessità è $O(n^2)$ dovuta ai due cicli di enumerazione elementari e di verifica di compatibilità con gli altri elementi.

### Problema del partizionamento delle attività

Il problema del partizionamento delle attività è definito con gli stessi dati del problema di selezione, tuttavia la differenza è che sono a disposizione **più risorse** che possono ospitare / eseguire le attività (il limite superiore al numero di risorse è di una risorsa per ciascuna attività).

Potete pensare alle attività come a lezioni e alle risorse come aule in cui svolgerle.

Il problema richiede che **tutte** le attività vengano selezionate ed assegnate ad un **risorsa**, **minimizzando** il numero totale di risorse necessarie.

#### Partizionamento delle attività: esempio di soluzione

![Partizionamento1](img\Partizionamento1.png)

Il numero di risorse richieste da questa soluzione è 8 invece di 12(limite superiore).

**strategia greedy**

In questo caso l'algoritmo deve decidere non solo se includere o meno l'attività(tutte le attività devono essere incluse) ma anche su quale delle risorse l'attività corrente deve essere eseguita. In particolare deve decidere se l'attività può essere eseguita su di una risorsa esistente o, piuttosto, ne debba essere creata una nuova.

L'euristica ottima per la decisione, in questo caso, è quella che considera il tempo di inizio delle attività, in ordine crescente: $h(a) = a.start$. La scelta della risorsa da utilizzare, però può essere realizzata in modo efficente scegliendo sempre la prima disponibile(ossia quella che risulta libera da più tempo). Quindi, in questo caso abbiamo anche un'euristica per la scelta della risorsa $h^{\prime}(a,s) = min_{r\in \mathbb{R}}\{r.disponibile\leq a.start\}$ che invece è dinamica

**schema dell' algoritmo**

![Partizionamento2](img\Partizionamento1.png)

Dato il vettore delle attività ordinato per istante di inizio, scegli ciascuna attività e assegnala alla risorsa disponibile(ovvero che non ha attività in esecuzione incompatibili con l'attività scelta) che risulta libera da più tempo

**esempio**

![Partizionamento3](img\Partizionamento3.png)

L'attività $A_2$ può essere scelta e assegnata alla prima risorsa che viene creata ex novo (per uniformità, anche all'inizio non creiamo alcuna risorsa).

Di seguito può essere scelta l'attività $A_7$ che essendo in conflitto con $A_2$ dev'essere assegnata ad una nuova risorsa.

La prossima attività candidata è $A_{12}$ che verrà assegnata dalla risorsa libera da più tempo,$R_2$ mentre $A_{11}$ può trovare posto su $R_2$

![Partizionamento4](img\Partizionamento4.png)

La risorsa $A_5$ è in conflitto con le ultime attività di entrambe le risorse, pertanto è necessario creare una nuova risorsa $R_3$ per eseguirla

![Partizionamento5](img\Partizionamento5.png)

La risorsa $A_5$ è in conflitto con le ultime attività di entrambe le risorse, pertanto è necessario creare una nuova risorsa $R_3$ per eseguirla

![Partizionamento6](img\Partizionamento6.png)

Anche la risorsa $A_3$ richiede una nuova risorsa, e lo stesso dicasi per $A_3,A_8,A_9$ e $A_1$

![Partizionamento7](img\partizionamento7.png)

Infine, $A_6$ trova posto sulla risorsa $R_{12}$ (disponibile da più tempo rispetto a $R_1$),$a_{10}$ sulla risorsa $R_1$(unica disponibile) e $A_4$ sulla risorsa $R_5$ (disponibile da più tempo rispetto a $R_2$).

Anche in questo caso l'ordinamento fra le componenti delle soluzioni è **statico**: dipende solo dal valore `start` dell'attività e non cambia con l'aggiunta di elementi alle soluzioni.
Tuttavia, la scelta della risorsa, invece, è dinamica e dipende dalla risorsa che è disponibile da più tempo.

Altri esempi di euristiche che vengono aggiornate dinamicamente in base agli elementi delle soluzioni possono essere visti nel caso dei grafi oppure, nel caso delle codifiche.

Sebbene non sia stato dato il codice, la complessità è stimabile in $O(nr)$ con $r$ numero di risorse utilizzate nella soluzione, dovuta al fatto che a ciascun elemento devo cercare la risorsa al quale assegnarlo ($O(n^2)$ nel caso peggiore).

Se le risorse vengono mantenute in una coda di priorità minima ordinata per istante di fine dell' ultima attività il tempo diventa $O(n\;log\,r)$, ovvero $O(n\; log\,n)$ nel caso peggiore.\\\\\\\\\\\\