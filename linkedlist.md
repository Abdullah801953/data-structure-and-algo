# Linked List

Linked List bhi ek linear data structure hai, lekin ye Array se kaafi alag tarike se kaam karti hai.

Array mein saare elements memory mein ek ke baad ek (contiguous) store hote hain, lekin Linked List mein elements memory mein kahi bhi scattered (bikhre hue) ho sakte hain. Ye sabhi elements aapas mein Pointers (Links) ki madad se jude hote hain.

## Real-Life Example: Treasure Hunt Ya Train Ke Dabba

Linked List ko aap ek Treasure Hunt game ya Train ke dabbo ki tarah samajh sakte hain:

- Train ka har dabba (Node) agle mehmaan/dabbe se ek coupling (link/pointer) ke zariye juda hota hai.
- Ek dabbe ko pata hota hai ki uske aage kaun sa dabba hai.

```
[Head] -> [ Data | Next ] -> [ Data | Next ] -> [ Data | NULL ]
            (Node 1)           (Node 2)           (Node 3)
```

## Linked List Ka Structure (Node Kya Hota Hai?)

Linked List ka sabse chota hissa hota hai **Node**. Har Node ke do parts hote hain:

- **Data:** Isme aapka main value store hota hai (jaise 10, 20, "Amit").
- **Next (Pointer/Address):** Isme agle Node ka memory address store hota hai.
- **Head:** Pehle Node ko Head kehte hain. Yahi se list ki shuruat hoti hai.
- **NULL / None:** Aakhri Node ka Next pointer NULL par point karta hai, jiska matlab hai ki list yahan khatam ho gayi.

## Linked List Ke Types (Prakar)

- **Singly Linked List:** Har node bas agle node ka pata (address) rakhta hai (Ek taraf jaane wala rasta).
- **Doubly Linked List:** Har node ke paas pichle (Previous) aur agle (Next) dono nodes ka pata hota hai (Dono taraf move kar sakte hain).
- **Circular Linked List:** Aakhri node ka Next pointer NULL hone ki bajaye wapas Pehle (Head) node ko point karta hai (Ek circle ban jata hai).

## Array vs Linked List (Mukhya Antar)

| Difference | Array | Linked List |
|---|---|---|
| Memory Allocation | Contiguous (Ek ke baad ek) | Dynamic (Kahi bhi bikhra hua) |
| Size | Fixed (Pehle se fix hota hai) | Dynamic (Kabhi bhi bada/chota kar sakte hain) |
| Access Time | O(1) - Direct Indexing (`arr[2]`) | O(n) - Head se shuru karke traverse karna padta hai |
| Insertion/Deletion | O(n) - Elements ko shift karna padta hai | O(1) - Bas pointers change karne hote hain (Fast) |

## Advantages aur Disadvantages

**Fayde (Pros):**
- **Dynamic Size:** Size ki koi limit nahi hoti, runtime par kitne bhi nodes add ya delete kar sakte hain.
- **Fast Insertion/Deletion:** Element add/remove karne ke liye baaki elements ko shift nahi karna padta.

**Nuksan (Cons):**
- **Extra Memory:** Data ke sath-sath Pointer (address) store karne ke liye extra memory lagti hai.
- **No Direct Access:** Aap direct 3rd node par nahi jaa sakte; aapko pehle 1st aur 2nd node se hokar guzarna padega.

---

# 1. Singly Linked List

Singly Linked List sabse basic form hai. Isme har node sirf aage wale (next) node ka address/pointer rakhta hai.

Isme aap sirf aage ki taraf (forward direction) travel kar sakte hain, pichhe wapas nahi aa sakte.

```
[Head] -> [ Data | Next ] -> [ Data | Next ] -> [ Data | NULL ]
            (Node 1)           (Node 2)           (Node 3)
```

**Node Structure:** `[ Data | Next Pointer ]`

- **Aakhri Node (Tail):** Iska Next pointer NULL par point karta hai, jo dikhata hai ki list khatam ho gayi hai.
- **Example Use Case:** Undo functionality ki jagah normal playlist, jahan gaane bas aage chalte hain.

---

# 2. Doubly Linked List

Doubly Linked List mein har node ke paas do pointers hote hain: ek Next (agle node ka address) aur ek Previous (pichle node ka address).

Isme aap aage (forward) aur pichhe (backward) dono directions mein travel kar sakte hain.

```
         |                       |                       |
         v                       v                       v
[NULL] <- [ Prev | Data | Next ] <-> [ Prev | Data | Next ] <-> [ Prev | Data | Next ] -> [NULL]
               (Node 1)                   (Node 2)                   (Node 3)
```

**Node Structure:** `[ Prev Pointer | Data | Next Pointer ]`

- **Pehla aur Aakhri Node:** Pehle node ka Prev pointer NULL hota hai, aur aakhri node ka Next pointer NULL hota hai.
- **Example Use Case:** Web Browser ki Back aur Forward buttons, Music Player jahan Previous Song aur Next Song dono par ja sakte hain.

---

# 3. Circular Linked List

Circular Linked List mein koyi bhi node NULL par point nahi karta. Isme aakhri node ka Next pointer wapas pehle (Head) node ko point karta hai, jisse ek bandh circle (loop) ban jata hai.

Ye do tarah ki ho sakti hai:

- **Singly Circular:** Sirf aage badh sakte hain, aur aakhri node wapas pehle par le aata hai.
- **Doubly Circular:** Dono taraf travel kar sakte hain, aur pehla-aakhri node aapas mein jude hote hain.

```
          |                                                       |
          v                                                       |
[Head] -> [ Data | Next ] -> [ Data | Next ] -> [ Data | Next ] -+
            (Node 1)           (Node 2)           (Node 3)
```

- **Node Structure:** Standard Singly ya Doubly node jaisa hi hota hai.
- **Khas Baat:** End indicator (NULL) nahi hota, isliye traversal kabhi rukta nahi jab tak aap khud logic na lagayein.
- **Example Use Case:** Multiplayer Games (Turn-by-turn chance, jaise Ludo mein Player 1 → 2 → 3 → 4 → 1), OS Task Scheduling (Round Robin algorithm).

## Direct Comparison (Mukhya Antar)

| Feature | Singly Linked List | Doubly Linked List | Circular Linked List |
|---|---|---|---|
| Pointers per Node | 1 (Next) | 2 (Prev, Next) | 1 ya 2 (khalis loop mein) |
| Direction | Sirf Forward | Forward & Backward | Continuous Loop (Round) |
| Last Node Pointer | NULL | NULL | Points to Head Node |
| Memory Consumption | Kam | Zyada (Extra pointer ke karan) | Medium/Same as Singly |
| Implementation | Sabse Aasan | Thoda Complex | Careful Loop Handling chahiye |