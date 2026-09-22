# Array

Haan bilkul! Array (अरे) Computer Science aur Programming ki sabse basic aur important data structure hai.

Aasan bhasha mein samjhein toh: Array ek hi type ke data elements ka ek ordered collection hota hai, jo memory mein ek ke baad ek (contiguous memory) store hota hai.

## Real-Life Example: Dabba / Locker System

Maan lijiye aapke paas ek aisa box/medicine tray hai jisme 5 dabbe ek line mein jude hue hain:

```plaintext
+---+---+---+---+---+
|10 |20 |30 |40 |50 |  <-- Inme rakhi hui values (Data)
+---+---+---+---+---+
  0   1   2   3   4    <-- Index (Dabbe ka number)
```

- **Size (Mahaatv) / Fixed Length:** Isme total 5 dabbe hain, toh iska size 5 hai.
- **Index (Pata / Address):** Har dabbe ka ek fixed number hota hai jise Index kehte hain. Programming mein counting humesha 0 se shuru hoti hai.
  - Pehla element (10) $\rightarrow$ Index 0 par hai.
  - Dusra element (20) $\rightarrow$ Index 1 par hai.
  - Aakhri element (50) $\rightarrow$ Index 4 par hai.

## Array Ki Mukhya Khasiyat (Key Features)

- **Same Data Type:** Array mein saare elements ek hi type ke hote hain (jaise saare Integers 10, 20, 30 ya saare Strings "Rahul", "Amit").
- **Contiguous Memory:** Iske saare elements RAM/Memory mein ek ke baad ek (lagatar) space lete hain.
- **Direct Access:** Aap kisi bhi element ko uske Index number se direct access/fetch kar sakte hain. Jaise: `arr[2]` likhne par seedhe 30 mil jayega.

## Array Operations (Aam Taur Par Hone Wale Kam)

| Operation | Matlab | Time Complexity |
|---|---|---|
| Access | Index se element dekhna (`arr[1]`) | $O(1)$ (Fastest - Fast) |
| Update | Nayi value set karna (`arr[1] = 99`) | $O(1)$ (Fastest - Fast) |
| Search | Kisi value ko dhundhna | $O(n)$ (Linear Search) |
| Insertion | Naya element beech/shuru mein jodna | $O(n)$ (Shifting lagti hai) |
| Deletion | Element ko hatana | $O(n)$ (Shifting lagti hai) |

## Array Ke Fayde aur Nuksan (Pros & Cons)

**Fayde (Advantages):**
- **Tez Access:** Index pata ho toh bina kisi delay ke direct data mil jata hai.
- **Simple:** Samjhna aur code karna bohot aasan hai.

**Nuksan (Disadvantages):**
- **Fixed Size:** Ek baar size declare kar diya toh runtime par usko badhana ya ghatana mushkil hota hai (static arrays mein).
- **Insertion/Deletion Slow:** Naya element beech mein daalne ya hatane par baaki saare elements ko aage-peeche shift karna padta hai.
