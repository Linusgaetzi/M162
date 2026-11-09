# Tag 1
---
## Heute gemacht
---

### Merkmalstypen

| Merkmal | Typ | Begründung |
|---|---|---|
| Haarfarbe | häufbar | mehrere Farben möglich |
| Gewicht | stetig | wird genau gemessen |
| Strecke | stetig | wird genau gemessen |
| Hobby | häufbar | mehrere gleichzeitig möglich |
| Geschlecht | diskret | einzelne feste Kategorien |
| Zeitintervall | stetig | wird genau gemessen |
| Berufsausbildung | häufbar | mehrere gleichzeitig möglich |
| Teilnehmeranzahl | diskret | wird ganzzahlig gezählt |
| Wasserpegel | stetig | wird genau gemessen |

---

### Skalatypen

| Merkmal | Skala | Begründung |
|---|---|---|
| Zeitdauer | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Geschlecht | Nominalskala | keine natürliche Reihenfolge |
| Kontonummer | Nominalskala | Zahl nur Name |
| Zufriedenheit (Skala 1–5) | Ordinalskala | Reihenfolge, ungleiche Abstände |
| Streckenlänge | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Haarfarbe | Nominalskala | keine natürliche Reihenfolge |
| Telefonnummer | Nominalskala | Zahl nur Name |
| Militär-Dienstrang | Ordinalskala | klare Rangfolge vorhanden |
| Wassertiefe | Kardinalskala (metrisch) | messbar, gleiche Abstände |
| Präferenzrangfolge | Ordinalskala | Rangfolge ohne Abstände |
| Geschmacksrichtung | Nominalskala | keine natürliche Reihenfolge |

---

## Merkmale und Skalen

### 1. Merkmalstypen

### Häufbares Merkmal
Eine Person oder ein Objekt kann **mehrere Ausprägungen gleichzeitig** haben. Die Prozente können deshalb zusammen mehr als 100 % ergeben.

**Beispiele:** Hobby, Berufsausbildung, Haarfarbe, gesprochene Sprachen

### Diskretes Merkmal
Es gibt nur **einzelne, abzählbare Werte**, nichts dazwischen. Man **zählt** etwas.

**Beispiele:** Teilnehmeranzahl, Anzahl Geschwister, Augenzahl beim Würfeln, Geschlecht

### Stetiges Merkmal
In einem Bereich ist **jeder beliebige Wert** möglich, auch alle Zwischenwerte. Man **misst** etwas.

**Beispiele:** Gewicht, Strecke, Zeitintervall, Wasserpegel

### 2. Skalentypen

### Nominalskala
Die Werte sind **nur Namen bzw. Kategorien**. Es gibt **keine Reihenfolge**, man kann nur sagen: gleich oder verschieden.

**Beispiele:** Geschlecht, Haarfarbe, Geschmacksrichtung, Telefonnummer, Kontonummer

### Ordinalskala
Die Werte haben eine **Reihenfolge**, aber die **Abstände sind nicht gleich gross** bzw. nicht bekannt. Man kann sagen: besser oder schlechter, höher oder tiefer.

**Beispiele:** Militär-Dienstrang, Zufriedenheit 1–5, Präferenzrangfolge, Kleidergrösse S/M/L

### Kardinalskala (metrische Skala)
Die Werte sind **echte Zahlen mit gleichen Abständen**. Man kann damit rechnen, also Differenzen und Durchschnitte bilden. Es gibt zwei Unterarten:

---

## Die drei Datenarten

| Tätigkeit | Unstrukturierte Daten | Wenig strukturierte Daten | Strukturierte Daten |
|---|---|---|---|
| **Beispiele** | Fliesstext, Bilder, Videos, Word-Dokumente | JSON, XML, E-Mails, einfache Excel-Listen | Datenbanktabellen (SQL) |
| **Initialisieren** | **sehr einfach** – kein Datenmodell nötig, einfach Datei anlegen | **einfach** – nur grobe Struktur (Tags, Schlüssel), kein festes Schema | **sehr schwierig** – Datenmodell planen, Tabellen, Datentypen, Beziehungen festlegen |
| **Erfassen** | **sehr einfach** – frei eingeben, keine Regeln | **einfach** – grobe Struktur einhalten, aber flexibel | **mittelschwierig** – feste Datentypen, Pflichtfelder und Format einhalten |
| **Mutieren** | **mittelschwierig** – Stelle muss gesucht werden, keine Felder | **einfach** – über Schlüssel/Tags auffindbar | **sehr einfach** – gezielt per ID ändern (UPDATE) |
| **Löschen** | **mittelschwierig** – einzelne Infos schwer zu finden, nur ganze Datei einfach | **einfach** – Elemente über Schlüssel entfernbar | **einfach** – gezielt per ID (DELETE), Beziehungen beachten |
| **Auswerten** | **sehr schwierig** – keine Felder, nur Volltextsuche oder manuell lesen | **mittelschwierig** – teilweise filterbar, Struktur nicht einheitlich | **sehr einfach** – mit SQL suchen, filtern, sortieren, gruppieren |
