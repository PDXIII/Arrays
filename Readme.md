# Tag 9 - Javascript Arrays

## **Lernziele**  
🔹 **Grundverständnis von Arrays**: Was sind Arrays, und wofür werden sie verwendet?  
🔹 **Erstellung und Initialisierung**: Wie werden Arrays in JavaScript definiert?  
🔹 **Zugriff und Manipulation**: Wie kann man Werte auslesen, verändern oder hinzufügen?  
🔹 **Arbeiten mit mehrdimensionalen Arrays**  
🔹 **Arrays aus Objekten verwenden**  
🔹 **Effiziente Nutzung und Methoden für Arrays** (`push()`, `pop()`, `map()`, `filter()`, `forEach()`, Vergleich `for` vs. `forEach`)  

---

## **🔹 Stunde 1: Einführung in Arrays (60 Min)**  

### **1. Was ist ein Array?**  

Ein **Array** ist eine **Datenstruktur**, die mehrere Werte speichert. **Jeder Wert hat einen Index**.

📌 **Beispiel für ein Array:**  

```js
let zahlen = [10, 20, 30, 40, 50];
console.log(zahlen); // [10, 20, 30, 40, 50]
```

🔹 **Warum Arrays?**  

✅ Speichern mehrere Werte unter einer Variablen.  
✅ Einfacher Zugriff durch **Indexnummern**.  
✅ Perfekt für Listen, Tabellen oder gesammelte Daten.

📌 **Übungen:**  

1️⃣ Erstelle ein Array mit 5 Städten und gib es in der Konsole aus.  
**Lösung:**  

```js
let staedte = ["Berlin", "Hamburg", "München", "Köln", "Frankfurt"];
console.log(staedte);
```

2️⃣ Erstelle ein Array mit den Namen von 3 Tieren.  
**Lösung:**  

```js
let tiere = ["Hund", "Katze", "Elefant"];
console.log(tiere);
```

### **📌 Heterogene Arrays (gemischte Datentypen in einem Array)**  
In JavaScript **müssen die Elemente eines Arrays nicht vom gleichen Datentyp sein**.  
Man kann Zahlen, Strings, Objekte und sogar Funktionen in einem Array mischen.

📌 **Beispiel für ein heterogenes Array:**  

```js
let gemischt = [42, "Hallo", true, { name: "Anna" }, [1, 2, 3], function() { return "Ich bin eine Funktion"; }];

console.log(gemischt[0]); // 42 (Zahl)
console.log(gemischt[1]); // "Hallo" (String)
console.log(gemischt[3].name); // "Anna" (Eigenschaft eines Objekts)
console.log(gemischt[4][1]); // 2 (Zugriff auf ein verschachteltes Array)
console.log(gemischt[5]()); // "Ich bin eine Funktion" (Funktion wird aufgerufen)
```

🔹 **Warum ist das nützlich?**  

✅ Man kann **komplexe Datenstrukturen** mit unterschiedlichen Elementen in einem einzigen Array speichern.  
✅ Perfekt für **Daten, die verschiedene Typen kombinieren** (z. B. Benutzerinfos mit Name, Alter, und Präferenzen).  

📌 **Übungen:**  

1️⃣ Erstelle ein heterogenes Array mit mindestens **drei verschiedenen Datentypen**.  

**Lösung:**  

```js
let datenMix = ["JavaScript", 2025, false, { sprache: "Deutsch" }];
console.log(datenMix);
```

2️⃣ Füge eine **Funktion** zu einem Array hinzu und rufe sie auf.  

**Lösung:**  

```js
let arr = ["Text", 99, function() { return "Ich bin eine Funktion im Array!"; }];
console.log(arr[2]()); // Aufruf der Funktion
```

---

## **🔹 Stunde 2: Erstellung & Manipulation von Arrays (60 Min)**  

### **1. Deklaration und Initialisierung von Arrays**  

```js
let zahlen = [1, 2, 3, 4, 5]; // Direkt mit Werten
let leerArray = []; // Leeres Array
let leerArray2 = new Array(3); // Array mit 3 leeren Plätzen
```

📌 **Übungen:**  

1️⃣ Erstelle ein leeres Array und füge nachträglich 3 Werte hinzu.  

**Lösung:**  

```js
let meineListe = [];
meineListe.push("Apfel", "Banane", "Kirsche");
console.log(meineListe);
```

2️⃣ Erstelle ein Array mit 3 Lieblingsfilmen und gib es aus.  

**Lösung:**  

```js
let filme = ["Inception", "Interstellar", "The Dark Knight"];
console.log(filme);
```

---

### **2. Zugriff auf Array-Elemente**  

```js
let farben = ["Rot", "Grün", "Blau"];
console.log(farben[0]); // "Rot"
console.log(farben[1]); // "Grün"
```

📌 **Übungen:**  

1️⃣ Greife auf das dritte Element deines Film-Arrays zu.  

**Lösung:**  

```js
console.log(filme[2]); // "The Dark Knight"
```

2️⃣ Ändere das zweite Element deines Städte-Arrays und gib es erneut aus.  

**Lösung:**  

```js
staedte[1] = "Düsseldorf";
console.log(staedte);
```

---

### **3. Manipulation von Array-Elementen**  

```js
let zahlen = [5, 10, 15];
zahlen[1] = 20;
console.log(zahlen); // [5, 20, 15]
```

📌 **Übungen:**  

1️⃣ Ändere das erste Element deines Tier-Arrays.  

**Lösung:**  

```js
tiere[0] = "Löwe";
console.log(tiere);
```

2️⃣ Ersetze das letzte Element deines Städte-Arrays durch eine neue Stadt.  

**Lösung:**  

```js
staedte[staedte.length - 1] = "Stuttgart";
console.log(staedte);
```

---

### **4. Methoden zum Ändern von Arrays**  

#### **Hinzufügen und Entfernen von Elementen**

```js
let namen = ["Anna", "Ben"];
namen.push("Chris"); // Am Ende hinzufügen
namen.unshift("Zoe"); // Am Anfang hinzufügen
namen.pop(); // Letztes Element entfernen
namen.shift(); // Erstes Element entfernen
console.log(namen);
```

📌 **Übungen:**  

1️⃣ Füge ein Element an dein Lieblingsessen-Array hinzu und entferne das erste Element.  

**Lösung:**  

```js
let essen = ["Pizza", "Burger", "Sushi"];
essen.push("Pasta");
essen.shift();
console.log(essen);
```

2️⃣ Erstelle ein Array mit 3 Zahlen, entferne die letzte Zahl und füge eine neue hinzu.  

**Lösung:**  

```js
let zahlen = [3, 6, 9];
zahlen.pop();
zahlen.push(12);
console.log(zahlen);
```

---

## **🔹 Stunde 3: Zweidimensionale Arrays & Iteration (60 Min)**  

### **1. Einführung in zweidimensionale Arrays**  

```js
let matrix = [
  [1, 2],
  [3, 4],
  [5, 6]
];

console.log(matrix[0][1]); // 2 (erste Reihe, zweite Spalte)
console.log(matrix[2][0]); // 5 (dritte Reihe, erste Spalte)
```

#### Der Bierkasten

Ein Bierkasten mit 4 Sixpacks mit jeweils 6 Flaschen soll ausgepackt werden. Wir nehmen uns den ersten Sixpack und packen Flasche für Flasche aus. Danach folgt der nächste Sixpack, und wir packen wieder Flasche für Flasche aus, usw.

```js
let bierkasten = [[1, 2, 3, 4, 5, 6], [7, 8, 9, 10, 11, 12], [13, 14, 15, 16, 17, 18], [19, 20, 21, 22, 23, 24] ];

        for (let sixpack = 0; sixpack < bierkasten.length; sixpack++) { 
            console.log("sixpack: ", sixpack);
            for (let flasche = 0; flasche < bierkasten[sixpack].length; flasche++) {
                console.log("flasche: ", bierkasten[sixpack][flasche]);
            }
        }
```

📌 **Übungen:**  

1️⃣ Erstelle ein zweidimensionales Array mit Namen & Alter von 3 Personen.  

**Lösung:**  

```js
let personen = [
  ["Alice", 25],
  ["Bob", 30],
  ["Charlie", 35]
];
console.log(personen);
```

---

## **🔹 Stunde 4: Arrays aus Objekten & Methoden (60 Min)**  

### **1. Arrays aus Objekten – Gemüseabteilung**  

```js
let gemuese = [
  { name: "Tomate", preis: 1.99, artikelnummer: 1001, kurzbeschreibung: "Saftige Tomaten" },
  { name: "Gurke", preis: 0.99, artikelnummer: 1002, kurzbeschreibung: "Knackige Gurken" },
  { name: "Paprika", preis: 2.49, artikelnummer: 1003, kurzbeschreibung: "Bunte Paprika" }
];
```

📌 **Übungen:**  

1️⃣ Greife auf den Preis und die Kurzbeschreibung der dritten Gemüseart zu.  

**Lösung:**  

```js
console.log(gemuese[2].preis);
console.log(gemuese[2].kurzbeschreibung);
```

---

## **📌 Zusammenfassung**  
✅ **Arrays speichern mehrere Werte unter einer Variablen.**  
✅ **Zugriff erfolgt über Indexnummern.**  
✅ **Mehrdimensionale Arrays ermöglichen Tabellen & komplexe Datenstrukturen.**  
✅ **Arrays aus Objekten sind nützlich für strukturierte Daten.**  
✅ **`forEach()` ist eine kompakte Alternative zur `for`-Schleife.**  

---

