
# 🐍 Probleme cu Tupluri în Python
### (Procesare, sortare, filtrare și analiză de date – nivel mediu spre complex)

---

## 1️⃣ Sortare după al doilea element
Ai o listă de tupluri `(nume, notă)`. Sorteaz-o după notă, crescător.

**Input:**
```python
elevi = [("Ana", 10), ("Ion", 8), ("Maria", 9)]
rez = sorted(elevi, key=lambda x: x[1])
print(rez)
```

**Output:**
```python
[('Ion', 8), ('Maria', 9), ('Ana', 10)]
```

---

## 2️⃣ Sortare descrescătoare după al doilea element
Aceeași listă, dar sortată descrescător după notă.

**Input:**
```python
rez = sorted(elevi, key=lambda x: x[1], reverse=True)
print(rez)
```

**Output:**
```python
[('Ana', 10), ('Maria', 9), ('Ion', 8)]
```

---

## 3️⃣ Filtrare după condiție numerică
Afișează doar elevii cu nota peste 8.

**Input:**
```python
elevi = [("Ana", 10), ("Ion", 8), ("Maria", 9)]
rez = [e for e in elevi if e[1] > 8]
print(rez)
```

**Output:**
```python
[('Ana', 10), ('Maria', 9)]
```

---

## 4️⃣ Căutare într-o listă de tupluri
Verifică dacă un elev există în listă după nume.

**Input:**
```python
elevi = [("Ana", 10), ("Ion", 8), ("Maria", 9)]
nume = "Ion"
exista = any(e[0] == nume for e in elevi)
print(exista)
```

**Output:**
```python
True
```

---

## 5️⃣ Calcularea mediei notelor
Calculează media notelor dintr-o listă de tupluri `(nume, notă)`.

**Input:**
```python
elevi = [("Ana", 10), ("Ion", 8), ("Maria", 9)]
media = sum(e[1] for e in elevi) / len(elevi)
print(media)
```

**Output:**
```python
9.0
```

---

## 6️⃣ Afișarea elevului cu cea mai mare notă
Folosește `max()` cu un `key` pentru a găsi elevul cu nota maximă.

**Input:**
```python
elevi = [("Ana", 10), ("Ion", 8), ("Maria", 9)]
top = max(elevi, key=lambda x: x[1])
print(top)
```

**Output:**
```python
('Ana', 10)
```

---

## 7️⃣ Afișarea elevului cu cea mai mică notă
Similar, dar cu `min()`.

**Input:**
```python
low = min(elevi, key=lambda x: x[1])
print(low)
```

**Output:**
```python
('Ion', 8)
```

---

## 8️⃣ Eliminarea tuplurilor duplicate
Elimină tuplurile identice dintr-o listă.

**Input:**
```python
note = [("Ana", 10), ("Ion", 8), ("Ana", 10)]
rez = list(set(note))
print(rez)
```

**Output:**
```python
[('Ion', 8), ('Ana', 10)]
```

---

## 9️⃣ Sortare după lungimea numelui
Sortează elevii după lungimea numelui.

**Input:**
```python
rez = sorted(elevi, key=lambda x: len(x[0]))
print(rez)
```

**Output:**
```python
[('Ion', 8), ('Ana', 10), ('Maria', 9)]
```

---

## 🔟 Inversarea perechilor (nume, notă)
Creează o nouă listă cu tupluri inversate `(notă, nume)`.

**Input:**
```python
inversate = [(n, m) for m, n in elevi]
print(inversate)
```

**Output:**
```python
[(10, 'Ana'), (8, 'Ion'), (9, 'Maria')]
```

---

## 1️⃣1️⃣ Calculul sumei notelor pare
Suma notelor care sunt pare.

**Input:**
```python
suma_pare = sum(n for _, n in elevi if n % 2 == 0)
print(suma_pare)
```

**Output:**
```python
18
```

---

## 1️⃣2️⃣ Sortare după ultima cifră a notei
Sortează tuplurile după ultima cifră a notei.

**Input:**
```python
rez = sorted(elevi, key=lambda x: x[1] % 10)
print(rez)
```

**Output:**
```python
[('Ion', 8), ('Maria', 9), ('Ana', 10)]
```

---

## 1️⃣3️⃣ Filtrare pe bază de inițială
Afișează doar elevii al căror nume începe cu „A”.

**Input:**
```python
rez = [e for e in elevi if e[0].startswith("A")]
print(rez)
```

**Output:**
```python
[('Ana', 10)]
```

---

## 1️⃣4️⃣ Concatenarea a două liste de tupluri
Combină două liste de tupluri într-una singură.

**Input:**
```python
a = [("Ana", 10)]
b = [("Ion", 9), ("Maria", 8)]
rez = a + b
print(rez)
```

**Output:**
```python
[('Ana', 10), ('Ion', 9), ('Maria', 8)]
```

---

## 1️⃣5️⃣ Calcularea diferenței între note maxime și minime
Determină diferența între nota maximă și minimă.

**Input:**
```python
max_nota = max(e[1] for e in elevi)
min_nota = min(e[1] for e in elevi)
print(max_nota - min_nota)
```

**Output:**
```python
2
```

---

## 1️⃣6️⃣ Sortare dublă (după notă, apoi nume)
Sortează mai întâi după notă, apoi alfabetic.

**Input:**
```python
rez = sorted(elevi, key=lambda x: (x[1], x[0]))
print(rez)
```

**Output:**
```python
[('Ion', 8), ('Maria', 9), ('Ana', 10)]
```

---

## 1️⃣7️⃣ Crearea de tupluri din fișier text
Fișierul `note.txt` conține:
```
Ana 10
Ion 8
Maria 9
```
Citește fișierul și creează o listă de tupluri.

**Input:**
```python
with open("note.txt") as f:
    elevi = [(l.split()[0], int(l.split()[1])) for l in f]
print(elevi)
```

**Output:**
```python
[('Ana', 10), ('Ion', 8), ('Maria', 9)]
```

---

## 1️⃣8️⃣ Transformarea unei liste de șiruri în tupluri
Listează și transformă datele în tupluri `(nume, nota)`.

**Input:**
```python
linii = ["Ana 10", "Ion 8", "Maria 9"]
rez = [tuple([p[0], int(p[1])]) for p in (line.split() for line in linii)]
print(rez)
```

**Output:**
```python
[('Ana', 10), ('Ion', 8), ('Maria', 9)]
```

---

## 1️⃣9️⃣ Suma notelor tuturor elevilor din tupluri
Adună toate notele dintr-un tuplu de tupluri.

**Input:**
```python
note = ((10, 9), (8, 7), (9, 10))
suma = sum(sum(t) for t in note)
print(suma)
```

**Output:**
```python
53
```

---

## 2️⃣0️⃣ Sortare după media notelor din tuplu
Fie o listă de tupluri `(nume, (nota1, nota2))`. Calculează media și sortează crescător.

**Input:**
```python
elevi = [("Ana", (10, 9)), ("Ion", (8, 7)), ("Maria", (9, 10))]
rez = sorted(elevi, key=lambda x: sum(x[1]) / len(x[1]))
print(rez)
```

**Output:**
```python
[('Ion', (8, 7)), ('Maria', (9, 10)), ('Ana', (10, 9))]
```
