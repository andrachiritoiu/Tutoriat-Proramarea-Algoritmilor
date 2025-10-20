# Programarea Algoritmilor – Tutoriat 1


## 1. Introducere în Python
 Ce este Python?

Limbaj interpretat, multi-paradigmă (procedural, orientat obiect, funcțional).


### *Instalare*

🔗 [Python.org – Download](https://www.python.org/downloads/)


## 2. Tipuri de date fundamentale
| Tip de date | Clasă internă | Exemple | Descriere |
|--------------|----------------|-----------|------------|
| `NoneType` | `NoneType` | `None` | absența unei valori sau inițializarea unui parametru al unei funcții cu o valoare implicită |
| `int` | `int` | `5`, `0b101`, `0x1F` | numere întregi |
| `float` | `float` | `3.14`, `-2.5e3` | numere reale |
| `complex` | `complex` | `2+3j` | numere complexe |
| `bool` | `bool` | `True`, `False` | valori logice |
| `str` | `str` | `'text'`, `"abc"` | șiruri de caractere |
| `list` | `list` | `[1, 2, 3]` | secvență mutabilă |
| `tuple` | `tuple` | `(1, 2, 3)` | secvență imutabilă |
| `set` | `set` | `{1, 2, 3}` | mulțime fără duplicate |
| `dict` | `dict` | `{"a": 1, "b": 2}` | perechi cheie: valoare |



### **Tipuri**:

-Tipul NoneType 

-Tipuri numerice: int, float, complex

-Tipul boolean

-Tipuri secvențiale: șiruri de caractere, liste, tupluri

-Tipuri mulțime: set, frozenset

-Tablouri asociative: dict

## 3. Variabile și conversii

Python nu cere declararea tipului – tipul este determinat dinamic (care poate fi modificat ulterior).

Poți folosi funcțiile type() și id() pentru a inspecta o variabilă.

```python
a = 10
b = "10"
print(type(a), type(b))  # <class 'int'> <class 'str'>
print(int(b) + 5)        # conversie string -> int
```



## 4. Afișare și citire

### *Afișare*
```python
print("Salut", "Python", sep=" | ", end="!!!\n")
#print("Tutoariat")
```



### f-strings (format modern)
```python
nume = "Ana"
varsta = 20
print(f"{nume} are {varsta} ani.")
```



### *Citire*
```python
x= input("x= ")  //valoarea cititită este întodeauna un șir de caractere
```

   ! Pentru a transforma șirurile de caractere citite în valori de alte tipuri primitive se 
folosesc funcțiile de conversie int(șir), float(șir), complex(șir) sau bool(șir).

```python
n = int(input("Introdu un număr: "))
print(f"Pătratul lui {n} este {n**2}")
```


## 5. Operatorii principali
### -Aritmetici

* `+` : Adunare
* `-` : Scădere
* `*` : Înmulțire
* `/` : Împărțire (rezultat real/float)
* `//` : Împărțire întreagă (rezultat întreg)
* `%` : Modulo (restul împărțirii)
* `**` : Exponențiere (ridicare la putere)

```python
a, b = 7, 2
print(a / b, a // b, a % b, a ** b)
```

### -Relaționali

* `<` : Mai mic decât
* `<=` : Mai mic sau egal cu
* `>` : Mai mare decât
* `>=` : Mai mare sau egal cu
* `==` : **Egalitate** (Verifică dacă **valorile** sunt egale)
* `!=` : Diferit de
* `is` : **Identitate** (Testează dacă două variabile/expresii sunt identice)
* `is not` : Identitate negativă (Testează dacă două variabile/expresii **nu** sunt identice)
* `in` : **Apartenență** (Verifică dacă o valoare există într-o secvență)
* `not in` : Apartenență negativă (Verifică dacă o valoare nu există într-o secvență)

```python
# Verificarea prezenței într-o Listă
numere = [1, 2, 3]
print(3 in numere)      # True
print(5 not in numere)  # True

# Verificarea prezenței într-un Șir de Caractere (String)
cuvant = "Python"
print("y" in cuvant)    # True
print("oana" not in cuvant) # True
```

### -Logici

* `not` (Negație logică). Inversează valoarea booleană (schimbă `True` în `False` și invers).
* `and` (Conjuncție logică). Returnează `True` doar dacă **ambele** condiții sunt `True`.
* `or` (Disjuncție logică). Returnează `True` dacă **cel puțin una** dintre condiții este `True`.

```python
x = 0
print(not x)  # True (0 e considerat False)
```

### -Pe biți

| Operator | Descriere | Explicație |
| :------: | :-------: | :---------------: |
| `~` | **NOT pe biți** | Inversează toți biții (0 devine 1, 1 devine 0). Rezultatul folosește complementul față de doi (va fi negativ). |
| `&` | **AND pe biți** | Setează bitul la 1 dacă **ambii biți** corespunzători sunt 1. |
| `\|` | **OR pe biți**  | Setează bitul la 1 dacă **cel puțin unul** dintre biții corespunzători este 1. |
| `^` | **XOR pe biți** | Setează bitul la 1 dacă biții corespunzători sunt **diferiți**. |
| `<<` | **Deplasare la stânga** | Decalează biții spre stânga cu $n$ poziții (echivalent cu înmulțirea cu $2^n$). |
| `>>` | **Deplasare la dreapta** | Decalează biții spre dreapta cu $n$ poziții (echivalent cu împărțirea la $2^n$ și rotunjire în jos). |


```python
# Reprezentarea binară (pe 4 biți):
# 5  este: 0101
# 3  este: 0011

# 1. AND pe biți (&)
# 0101 & 0011 = 0001 (1 zecimal)
print(f"5 & 3 = {5 & 3}")

# 2. OR pe biți (|)
# 0101 | 0011 = 0111 (7 zecimal)
print(f"5 | 3 = {5 | 3}")

# 3. XOR pe biți (^)
# 0101 ^ 0011 = 0110 (6 zecimal)
print(f"5 ^ 3 = {5 ^ 3}")

# 4. Deplasare la stânga (<<)
# 5 << 1 (0101 decalat cu 1) = 1010 (10 zecimal)
print(f"5 << 1 = {5 << 1}")
```

### Operatorul condițional

*valoare_daca_true if conditie else valoare_daca_false*

```python
# Exemplu: Testarea parității unui număr
x = 7

# Dacă restul împărțirii lui x la 2 este 0, este "par". Altfel, este "impar".
rezultat = "par" if x % 2 == 0 else "impar"
```


## 6. Instrucțiuni de control
### -Atribuire

```python
x = 5
x += 3
a, b = 1, 2
a, b = b, a  # interschimbare
```

### -Condiționale (if, elif, else)

```python
x = int(input("x = "))
if x < 0:
    print("Negativ")
elif x == 0:
    print("Zero")
else:
    print("Pozitiv")
```


### -Repetiții (while, for)

### *Buclă while*

```python
n = 123
s = 0
while n > 0:
    s += n % 10
    n //= 10
print("Suma cifrelor =", s)
```


### *Buclă for*

### -Range personalizat

```python
for i in range(2, 10, 2):  # start=2, stop=10, pas=2 - strat inclusiv, stop exclusiv
    print(i)
```

```python
# 1. Iterare cu range() - start, stop, step
print("Numere de la 5 la 1 (descrescător):")
for i in range(5, 0, -1):
    print(i, end=" ")
# Output: 5 4 3 2 1

# 2. Iterare prin elementele unei liste
lista_culori = ["roșu", "verde", "albastru"]
print("\n\nCulorile sunt:")
for culoare in lista_culori:
    print(f"- {culoare}")

# 3. Iterare prin Dicționar (Chei și Valori)
note = {"Mate": 9, "Info": 10}
print("\nNotele:")
for materie, nota in note.items():
    print(f"La {materie}: {nota}")
```


## Alte instrucțiuni utile

continue → sare peste iterația curentă

break → oprește complet bucla

else → se execută doar dacă bucla s-a terminat natural

pass → “placeholder” fără acțiune ( nu are niciun efect în program )

```python
for i in range(10):
    if i == 3:
        continue
    if i == 8:
        break
    print(i)
else:
    print("Bucla s-a terminat normal.")
```

# 7.SIRURI DE CARACTERE  (str)

 Un șir de caractere este o secvență de caractere indexată de la 0, stocată ca un obiect de tipul clasei str.

 'șir' sau "șir" - **O singură linie** (caracterele newline sunt ignorate)

 ```python
sir_1 = "Acesta este, de fapt,\nun sir scris\npe o singură linie!"

print(sir_1)
```

 '''șir''' sau """șir""" - **Mai multe linii** (caracterele newline nu sunt ignorate).
 
 ```python
sir_2 = """Acesta este
un sir scris
pe mai multe linii!"""

print(sir_2)
```


### *!Proprietatea Vitală: Imutabilitatea* 
Șirurile de caractere sunt imutabile. Aceasta înseamnă că:

-Valoarea unui obiect de tip str nu mai poate fi modificată după crearea sa.

-Nicio metodă din clasa str nu modifică șirul curent; în schimb, metodele creează și returnează un nou șir care conține rezultatul prelucrării.

```python
#Dacă vrei să transformi un șir în litere mari, trebuie să modifici referința variabilei
s = "test"
s.upper() # Metoda creează șirul "TEST", dar variabila s rămâne neschimbată
print(s)  # Output: test

# Corect: Reatribuirea noii referințe
s = s.upper() # s primește acum referința noului șir "TEST" 
print(s)  # Output: TEST
```


### Accesarea și Secționarea (Slicing) String-urilor

Șirurile de caractere sunt secvențe indexate de la **0** și sunt parcurse folosind indici sau intervale (slice-uri).

| Sintaxă | Descriere | Exemplu (`s = "Python"`) | Rezultat |
| :---: | :---: | :---: | :---: |
| `s[i]` | Acces prin **indice pozitiv** (de la 0). | `s[0]` | `'P'` |
| `s[-i]` | Acces prin **indice negativ** (de la -1, de la sfârșit). | `s[-1]` | `'n'` |
| `s[st:dr]` | **Slice** de la `st` (inclusiv) până la `dr` (**exclusiv**). | `s[1:4]` | `"yth"` |
| `s[:dr]` | De la început până la `dr` (**exclusiv**). | `s[:2]` | `"Py"` |
| `s[st:]` | De la `st` (inclusiv) până la sfârșit. | `s[3:]` | `"hon"` |
| `s[::pas]` | **Slice cu pas**. | `s[::-1]` | `"nohtyP"` |


##  Funcții și expresii utile  
| Funcție | Descriere | Exemplu |
|----------|------------|----------|
| `len()` | lungimea unei secvențe | `len("abc") → 3` |
| `sum()` | suma elementelor numerice | `sum([1, 2, 3]) → 6` |
| `max()`, `min()` | maxim / minim | `max(4, 2, 7)` |
| `abs()` | valoare absolută | `abs(-5)` |
| `round()` | rotunjire | `round(3.14159, 2)` |
| `sorted()` | sortare | `sorted([3, 1, 2]) → [1, 2, 3]` |
| `type()`, `isinstance()` | verificare tip | `isinstance(3, int)` |


## 8. Probleme 

1️⃣ Paritate
```python
n = int(input("n = "))
print("Par" if n % 2 == 0 else "Impar")
```


2️⃣ Maximul dintre 3 numere
```python
a, b, c = map(int, input("a b c = ").split())
print("Maximul este", max(a, b, c))
```


3️⃣ Factorial
```python
n = int(input("n = "))
f = 1
for i in range(1, n + 1):
    f *= i
print(f"{n}! = {f}")
```


4️⃣ Număr prim
```python
n = int(input("n = "))
for d in range(2, n // 2 + 1):
    if n % d == 0:
        print("Nu e prim")
        break
else:
    print("Este prim")
```


5️⃣ Suma numerelor pozitive până la 0
```python
s = 0
while True:
    x = int(input("x = "))
    if x == 0:
        break
    s += x
print("Suma =", s)
```
