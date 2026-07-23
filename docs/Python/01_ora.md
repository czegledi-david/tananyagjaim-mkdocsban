# 1. Óra

## Bevezető

A Python egy népszerű, magas szintű programozási nyelv, melyet széles körben használnak webfejlesztésre, adatelemzésre, mesterséges intelligenciához és szkriptek írására. Könnyen olvasható szintaxisának köszönhetően kezdők számára is ideális választás.

## Ismerkedés a Visual Studio Code fejlesztő környezettel

A Visual Studio Code (röviden VS Code) egy ingyenes, nyílt forráskódú kódszerkesztő, melyet a Microsoft fejleszt. Számos programozási nyelvet támogat, így a Pythont is.

**Fontosabb funkciók:**

*   Szintaxiskiemelés
*   Intelligens kódkiegészítés (IntelliSense)
*   Beépített terminál
*   Bővítmények (kiterjesztések) kezelése

## Egyszerű python script létrehozása és futtatása

1.  Nyissuk meg a VS Code-ot.
2.  Hozzunk létre egy új fájlt (File -> New File).
3.  Mentsük el a fájlt `.py` kiterjesztéssel (pl. `elso.py`).
4.  Írjuk be a következőt: `print("Hello Világ!")`
5.  A futtatáshoz nyissunk egy terminált (Terminal -> New Terminal), és írjuk be a `python elso.py` parancsot.

## Változók bevezetése

A változók olyan "tárolók", melyekben adatokat (értékeket) tárolhatunk.

### Változó deklarálása és értékadása

Pythonban a változókat nem kell külön deklarálni (típusukat megadni). A változó létrejön, amint értéket adunk neki az egyenlőségjel (`=`) segítségével.

```python
x = 5
nev = "Kovács János"
```

### Típusok

A leggyakoribb adattípusok Pythonban:

| Típus | Név | Leírás | Példa |
| :--- | :--- | :--- | :--- |
| Egész szám | `int` | Egész számok, pozitív és negatív. | `x = 10` |
| Tört szám | `float` | Tizedes törtek. A tizedesjel a pont (`.`). | `pi = 3.14` |
| Szöveg | `str` | Karakterláncok. Idézőjelek ("") vagy aposztrófok ('') közé írjuk. | `nev = "Béla"` |
| Logikai | `bool` | Csak két értéket vehet fel: `True` (Igaz) vagy `False` (Hamis). | `kesz_van = True` |

### Változó értékének kiíratása: `print`

A `print()` függvény segítségével tudunk adatokat kiíratni a képernyőre.

```python
x = 10
print(x)
print("Az eredmény:", x)
```

## Dinamikus típuskezelés

Pythonban a változók típusa dinamikus, ami azt jelenti, hogy futás közben is megváltozhat az értékadás alapján.

```python
x = 5       # x egy egész szám (int)
x = "Alma"  # x most már egy szöveg (str)
```

## Típusok átalakítása (Casting)

A különböző típusok között átalakításokat végezhetünk beépített függvények segítségével.

*   `int()`: Egész számmá alakít.
*   `float()`: Tört számmá alakít.
*   `str()`: Szöveggé alakít.

```python
szam_szoveg = "10"
szam = int(szam_szoveg)  # A szövegből egész szám lesz
```

## Matematikai műveletek

| Művelet | Operátor | Példa |
| :--- | :---: | :--- |
| Összeadás | `+` | `3 + 2` -> 5 |
| Kivonás | `-` | `3 - 2` -> 1 |
| Szorzás | `*` | `3 * 2` -> 6 |
| Osztás | `/` | `3 / 2` -> 1.5 |
| Egész osztás | `//` | `3 // 2` -> 1 |
| Maradék | `%` | `3 % 2` -> 1 |
| Hatványozás | `**` | `3 ** 2` -> 9 |

### Kerekítés

A beépített `round()` függvénnyel kerekíthetünk.

```python
print(round(3.14159, 2))  # Eredmény: 3.14
```

### A `math` modul használata

Bonyolultabb matematikai számításokhoz a `math` modult használjuk. Ezt a fájl elején importálni kell: `import math`

**Néhány fontos függvény a math modulból:**

| Függvény | Leírás | Példa | Eredmény |
| :--- | :--- | :--- | :--- |
| `math.sqrt(x)` | Gyökvonás | `math.sqrt(16)` | 4.0 |
| `math.pow(x, y)` | x az y-adik hatványon | `math.pow(2, 3)` | 8.0 |
| `math.log10(x)` | 10-es alapú logaritmus | `math.log10(100)` | 2.0 |
| `math.log(x)` | Természetes alapú logaritmus | `math.log(math.e)` | 1.0 |
| `math.exp(x)` | e az x-edik hatványon | `math.exp(1)` | 2.718... |
| `math.sin(x)` | Szinusz (radiánban) | `math.sin(math.pi/2)` | 1.0 |
| `math.cos(x)` | Koszinusz (radiánban) | `math.cos(0)` | 1.0 |
| `math.tan(x)` | Tangens (radiánban) | `math.tan(math.pi/4)` | 1.0 |
| `math.fabs(x)` | Abszolút érték | `math.fabs(-5)` | 5.0 |
| `math.ceil(x)` | Felfelé kerekítés | `math.ceil(3.1)` | 4 |
| `math.floor(x)` | Lefelé kerekítés | `math.floor(3.9)` | 3 |