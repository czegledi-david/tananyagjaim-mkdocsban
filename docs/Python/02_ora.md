# 2. Óra: Adatbekérés és vezérlési szerkezetek

## 1. Változó beolvasása: `input()`

A múlt órán fix értékeket adtunk a változóknak. Most megtanuljuk, hogyan kérhetünk be adatot a felhasználótól a billentyűzeten keresztül. Erre való az `input()` függvény.

```python
nev = input("Kérlek, add meg a neved: ")
print(f"Üdvözöllek, {nev}!")
```

!!! warning "A leggyakoribb hiba: Az input mindig szöveg!"
    Az `input()` függvény **kivétel nélkül mindig szöveget (stringet) ad vissza**. Ha számokat kérünk be, és utána számolni akarunk velük, azonnal át kell alakítanunk (konvertálnunk) őket az előző órán tanult módon!

**Példa a helyes számbekérésre:**
```python
szuletes_eve_szoveg = input("Melyik évben születtél? ")
szuletes_eve = int(szuletes_eve_szoveg)  # Átalakítás egész számmá

# VAGY egy lépésben (ez a profibb és gyakoribb megoldás):
eletkor = int(input("Hány éves vagy? "))
```

---

## 2. Műveletek kiértékelésének sorrendje

A Pythonban a matematikai műveletek kiértékelése a hagyományos matematikai szabályokat (precedencia) követi. 

1. **Zárójelek `()`**: Mindig a legmagasabb prioritásúak. Amit zárójelbe teszünk, az hajtódik végre először.
2. **Hatványozás `**`**
3. **Szorzás `*`, Osztás `/`, Egész osztás `//`, Maradékos osztás `%`**
4. **Összeadás `+`, Kivonás `-`**

```python
eredmeny_1 = 10 + 5 * 2   # Eredmény: 20 (a szorzás erősebb)
eredmeny_2 = (10 + 5) * 2 # Eredmény: 30 (a zárójel miatt az összeadás fut le előbb)
```

---

## 3. Logikai és összehasonlító műveletek

Ahhoz, hogy a programunk döntéseket tudjon hozni, fel kell tennünk kérdéseket. Például: *Nagyobb ez a szám, mint 10? Egyenlő a jelszó az elvárttal?* Ezeknek az összehasonlításoknak az eredménye mindig egy logikai érték: **`True`** (Igaz) vagy **`False`** (Hamis).

### Összehasonlító operátorok
* `==` : Egyenlő (Figyelem: Két egyenlőségjel! Az egy db `=` az értékadás jele!)
* `!=` : Nem egyenlő
* `<`  : Kisebb
* `>`  : Nagyobb
* `<=` : Kisebb vagy egyenlő
* `>=` : Nagyobb vagy egyenlő

### Logikai operátorok (Feltételek összekapcsolása)
Ha több feltételt akarunk egyszerre vizsgálni, ezeket használjuk:
* **`and` (ÉS)**: Csak akkor `True`, ha **minden** feltétel igaz.
* **`or` (VAGY)**: Akkor `True`, ha **legalább az egyik** feltétel igaz.
* **`not` (NEM)**: Megfordítja a logikai értéket (igazból hamis, hamisból igaz lesz).

```python
kor = 20
jogositvany = True

# Van jogosítványa ÉS elmúlt 18 éves?
vezethet = (kor >= 18) and jogositvany  # Eredmény: True
```

---

## 4. Elágazások (Vezérlési szerkezetek)

Az elágazásokkal (feltételes utasításokkal) érhetjük el, hogy a programunk bizonyos kódblokkokat csak akkor futtasson le, ha egy feltétel teljesül.

### Az `if` szerkezet (`if`, `elif`, `else`)

!!! warning "A behúzás (Indentation) kritikus!"
    A Python nem használ kapcsos zárójeleket `{}` a blokkok jelölésére, mint a C# vagy a Java. Helyette **kötelezően 4 szóközzel beljebb (behúzva)** kell írni azt a kódot, ami az `if`-hez tartozik! A feltétel után mindig **kettőspont `:`** áll.

```python
pontszam = int(input("Hány pontot értél el a vizsgán? "))

if pontszam >= 80:
    print("Gratulálok, kiváló eredmény!")
    print("Jeles (5)")
elif pontszam >= 60:
    print("Szép munka, átmentél.")
    print("Közepes (3)")
else:
    print("Sajnos ez most nem sikerült.")
    print("Elégtelen (1)")

print("Ez a sor már mindenképpen lefut, mert nincs behúzva.")
```

---

### A `match-case` szerkezet (Python 3.10+)

Ha egyetlen változó konkrét értékeit akarjuk vizsgálni (például egy menüpont kiválasztásánál), a sok `elif` helyett sokkal elegánsabb a `match-case` használata.

```python
parancs = input("Mit szeretnél csinálni? (inditas/leallitas/ujrainditas): ")

match parancs:
    case "inditas":
        print("A rendszer indul...")
    case "leallitas":
        print("A rendszer leáll...")
    case "ujrainditas":
        print("A rendszer újraindul...")
    case _:
        # A '_' (alsóvonal) a default eset, ami akkor fut le, ha semmi más nem egyezett.
        print("Ismeretlen parancs! Kérlek a megadott opciók közül válassz.")
```
