Lo **studio di funzione integrale** è un argomento comune negli esami di Analisi 1. Si tratta di analizzare una funzione definita come un integrale, del tipo:

\[
f(x) = \int_{a(x)}^{b(x)} g(t) \, dt
\]

dove \( g(t) \) è una funzione nota e \( a(x) \) e \( b(x) \) sono funzioni che dipendono da \( x \). Lo studio di funzione integrale richiede di applicare i concetti di analisi matematica (limiti, derivate, integrali) per determinare le proprietà della funzione \( f(x) \).

Ecco una **guida passo-passo** per affrontare uno studio di funzione integrale:

---

### **1. Determinare il Dominio della Funzione \( f(x) \)**
Il dominio di \( f(x) \) è l'insieme dei valori di \( x \) per cui l'integrale è definito. Per determinarlo:
- Verifica se \( g(t) \) è definita e integrabile nell'intervallo \([a(x), b(x)]\).
- Controlla se \( a(x) \) e \( b(x) \) sono ben definite per ogni \( x \).
- Se l'integrale è improprio (ad esempio, se uno degli estremi è infinito), studia la convergenza dell'integrale.

**Esempio:**
Se \( f(x) = \int_{0}^{x} \frac{1}{\sqrt{t}} \, dt \), il dominio è \( x \geq 0 \) perché \( \frac{1}{\sqrt{t}} \) è definita solo per \( t > 0 \).

---

### **2. Studiare la Parità della Funzione**
Determina se \( f(x) \) è pari, dispari o nessuna delle due:
- **Funzione pari:** \( f(-x) = f(x) \).
- **Funzione dispari:** \( f(-x) = -f(x) \).

**Esempio:**
Se \( f(x) = \int_{-x}^{x} t^2 \, dt \), allora \( f(-x) = f(x) \), quindi \( f(x) \) è pari.

---

### **3. Calcolare i Limiti agli Estremi del Dominio**
Calcola i limiti di \( f(x) \) quando \( x \) tende agli estremi del dominio. Questo ti aiuta a capire il comportamento della funzione all'infinito o in punti critici.

**Esempio:**
Se \( f(x) = \int_{0}^{x} e^{-t^2} \, dt \), calcola:
\[
\lim_{x \to +\infty} f(x) = \int_{0}^{+\infty} e^{-t^2} \, dt = \frac{\sqrt{\pi}}{2}
\]

---

### **4. Calcolare la Derivata di \( f(x) \)**
Usa il **Teorema Fondamentale del Calcolo Integrale** per trovare la derivata di \( f(x) \):
\[
f'(x) = g(b(x)) \cdot b'(x) - g(a(x)) \cdot a'(x)
\]
Se \( a(x) \) è costante, il termine corrispondente si annulla.

**Esempio:**
Se \( f(x) = \int_{0}^{x} \sin(t^2) \, dt \), allora:
\[
f'(x) = \sin(x^2)
\]

---

### **5. Studiare la Monotonia di \( f(x) \)**
Analizza il segno della derivata \( f'(x) \) per determinare dove \( f(x) \) è crescente o decrescente:
- Se \( f'(x) > 0 \), \( f(x) \) è crescente.
- Se \( f'(x) < 0 \), \( f(x) \) è decrescente.

**Esempio:**
Se \( f(x) = \int_{0}^{x} e^{-t} \, dt \), allora \( f'(x) = e^{-x} > 0 \), quindi \( f(x) \) è sempre crescente.

---

### **6. Calcolare la Derivata Seconda e Studiare la Concavità**
Calcola \( f''(x) \) derivando \( f'(x) \). Poi studia il segno di \( f''(x) \) per determinare la concavità:
- Se \( f''(x) > 0 \), \( f(x) \) è convessa.
- Se \( f''(x) < 0 \), \( f(x) \) è concava.

**Esempio:**
Se \( f(x) = \int_{0}^{x} \sin(t) \, dt \), allora:
\[
f'(x) = \sin(x), \quad f''(x) = \cos(x)
\]
La concavità dipende dal segno di \( \cos(x) \).

---

### **7. Trovare la Retta Tangente (se richiesto)**
Se devi trovare la retta tangente al grafico di \( f(x) \) in un punto \( x_0 \), usa la formula:
\[
y = f(x_0) + f'(x_0)(x - x_0)
\]

**Esempio:**
Se \( f(x) = \int_{0}^{x} e^{-t^2} \, dt \) e \( x_0 = 0 \), allora:
\[
f(0) = 0, \quad f'(0) = e^{-0^2} = 1
\]
La retta tangente è:
\[
y = 0 + 1 \cdot (x - 0) \implies y = x
\]

---

### **8. Disegnare il Grafico della Funzione**
Usa le informazioni raccolte (dominio, limiti, monotonia, concavità) per disegnare un grafico approssimativo di \( f(x) \).

---

### **Esempio Completo**

Considera la funzione:
\[
f(x) = \int_{0}^{x} \frac{1}{1 + t^2} \, dt
\]

1. **Dominio:** \( \mathbb{R} \) perché \( \frac{1}{1 + t^2} \) è definita e integrabile per ogni \( t \).
2. **Parità:** \( f(-x) = \int_{0}^{-x} \frac{1}{1 + t^2} \, dt = -\int_{0}^{x} \frac{1}{1 + t^2} \, dt = -f(x) \), quindi \( f(x) \) è dispari.
3. **Limiti:**
   \[
   \lim_{x \to +\infty} f(x) = \int_{0}^{+\infty} \frac{1}{1 + t^2} \, dt = \frac{\pi}{2}
   \]
   \[
   \lim_{x \to -\infty} f(x) = -\frac{\pi}{2}
   \]
4. **Derivata:**
   \[
   f'(x) = \frac{1}{1 + x^2} > 0 \quad \forall x \in \mathbb{R}
   \]
   Quindi \( f(x) \) è sempre crescente.
5. **Concavità:**
   \[
   f''(x) = -\frac{2x}{(1 + x^2)^2}
   \]
   - Se \( x > 0 \), \( f''(x) < 0 \) (concava).
   - Se \( x < 0 \), \( f''(x) > 0 \) (convessa).
6. **Grafico:** La funzione è crescente, dispari, con asintoti orizzontali a \( y = \frac{\pi}{2} \) e \( y = -\frac{\pi}{2} \).

---

### **Conclusione**
Seguendo questi passaggi, puoi affrontare qualsiasi studio di funzione integrale in modo sistematico e completo. Ricorda di applicare il Teorema Fondamentale del Calcolo Integrale per calcolare le derivate e di analizzare attentamente il dominio e i limiti della funzione. Buono studio! 😊
