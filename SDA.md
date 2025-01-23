# Riassunto di SDA

## indice
- [01 - Organizzazione della memoria, chiamate di funzioni, ricorsione](#01---organizzazione-della-memoria-chiamate-di-funzioni-ricorsione)
   - [L'organizzazione della memoria](#lorganizzazione-della-memoria)
   - [Record di attivazione](#record-di-attivazione)
   - [La ricorsione](#la-ricorsione)
- [02 - Trattabilità e complessità computazionale](#02-trattabilità-e-complessità-computazionale)
   - [Problemi decidibili ed indecidibili](#problemi-decidibili-e-indecidibili)
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

### Record di attivazione
   Ogni funzione crea un suo spazio di memorizzazione specifico nello stack chiamato **record di attivazione**.
   Esso include tutte le variabili locali, i parametri ed i valori di ritorno della funzione.

   E' come una scatola chiusa, la funzione può fare tutto chiò che vuole senza interferire con l'ambiente di altre funzioni.

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
n. f(n-1) & se\quad n >0

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
| $n$   | 0 | 1 | 2 | 3 | 4 | 5 | 6  | 7  | 8  | 9  | 10 | 11  |
|-------|---|---|---|---|---|---|----|----|----|----|----|-----|
| $F_n$ | 1 | 1 | 2 | 3 | 5 | 8 | 13 | 21 | 34 | 55 | 89 | 144 |

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

#### complessità
alcuni problemi, nonostante decidibili, possono richiedere un tempo di risoluzione notevole, per esempio il problema delle **torri di Hanoi**
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
