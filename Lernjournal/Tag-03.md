# Tag 3 

# Zeichenkodierung: ASCII, ANSI, Unicode, UTF-8, UTF-16, UTF-32
 
## Grundidee
 
Ein Computer kann nur Zahlen speichern. Damit er Text speichern kann, braucht es eine Tabelle, die jedem Zeichen eine Zahl gibt. Dabei muss man zwei Dinge unterscheiden:
 
- **Zeichensatz:** Welche Zeichen gibt es, und welche Nummer hat jedes Zeichen? Beispiele: ASCII, Unicode.
- **Kodierung:** Wie wird diese Nummer als Bytes gespeichert? Beispiele: UTF-8, UTF-16, UTF-32.
Bei ASCII und ANSI ist beides dasselbe. Bei Unicode ist es getrennt.
 
## ASCII
 
- Entstanden **1963**, nutzt **7 Bit** und hat damit **128 Zeichen** (0–127).
- 0–31 sind Steuerzeichen, zum Beispiel 10 = Zeilenumbruch (LF) und 13 = Wagenrücklauf (CR).
- 32 ist das Leerzeichen, 48–57 sind die Ziffern 0–9, 65–90 die Buchstaben A–Z und 97–122 die Buchstaben a–z.
- Beispiel: **A = 65** (hexadezimal 41)
- **Problem:** ASCII kennt nur Englisch. Umlaute wie ä, ö, ü oder das €-Zeichen fehlen.
## ANSI
 
- Unter Windows heisst so die **Codepage**, in Westeuropa **Windows-1252**. Sehr ähnlich ist **ISO-8859-1** (Latin-1).
- ANSI nutzt **8 Bit** und hat damit **256 Zeichen**. Die Zeichen 0–127 sind gleich wie bei ASCII. Die Zeichen 128–255 sind je nach Land verschieden, in Westeuropa zum Beispiel ä, ö, ü und €.
- **Problem:** Die gleichen Bytes geben je nach Codepage andere Zeichen. Ein Text aus Russland sieht auf einem Schweizer PC darum falsch aus.
- Der Name ist eigentlich falsch: Windows-1252 ist nie ein offizieller ANSI-Standard geworden. Der Begriff hat sich aber gehalten.
## Unicode
 
- **Ein einziger Zeichensatz für alle Schriften der Welt**, inklusive Emojis.
- Jedes Zeichen hat eine feste Nummer, den **Codepoint**. Man schreibt ihn als `U+` und eine hexadezimale Zahl:
  - `U+0041` = A
  - `U+00E4` = ä
  - `U+20AC` = €
  - `U+1F600` = 😀
- Es gibt Platz für über **1,1 Millionen** Codepoints. Vergeben sind im Moment über 150 000.
- Unicode legt **nur die Nummern fest**, nicht, wie sie gespeichert werden. Dafür gibt es die Kodierungen UTF-8, UTF-16 und UTF-32 (UTF = Unicode Transformation Format).
## UTF-8
 
- Ein Zeichen braucht **1 bis 4 Byte**, je nach Zeichen.
- Die Zeichen 0–127 brauchen genau 1 Byte und sind **gleich wie bei ASCII**. Ein ASCII-Text ist also automatisch auch gültiges UTF-8.
- Umlaute brauchen 2 Byte, das €-Zeichen 3 Byte und Emojis 4 Byte.
- **Einsatz:** Web, JSON, XML, Linux und macOS, Quellcode, Git. Heute ist UTF-8 der Standard.
## UTF-16
 
- Ein Zeichen braucht **2 oder 4 Byte**. Die meisten Zeichen brauchen 2 Byte. Emojis und seltene Zeichen brauchen 4 Byte (sogenannte Surrogate-Paare).
- **Nicht kompatibel mit ASCII**, weil auch „A“ schon 2 Byte braucht.
- Die **Byte-Reihenfolge** spielt eine Rolle: Little Endian (LE) oder Big Endian (BE). Darum steht am Anfang der Datei oft ein **BOM** (Byte Order Mark): `FF FE` für LE oder `FE FF` für BE.
- **Einsatz:** intern in Windows, Java, JavaScript und C#/.NET
## UTF-32
 
- Jedes Zeichen braucht **immer genau 4 Byte**.
- Vorteil: Das ist sehr einfach, denn die gespeicherte Zahl ist direkt der Codepoint.
- Nachteil: UTF-32 verschwendet viel Platz. Ein „A“ braucht 4 Byte statt 1.
- **Einsatz:** selten, höchstens intern in Programmen. Für Dateien oder im Web nutzt man es praktisch nie.
## Vergleich
 
So werden die Zeichen gespeichert (in Hex, bei UTF-16 und UTF-32 in Big Endian):
 
| Zeichen | ASCII      | ANSI (1252) | UTF-8         | UTF-16        | UTF-32        |
|---------|------------|-------------|---------------|---------------|---------------|
| A       | `41`       | `41`        | `41`          | `00 41`       | `00 00 00 41` |
| ä       | geht nicht | `E4`        | `C3 A4`       | `00 E4`       | `00 00 00 E4` |
| €       | geht nicht | `80`        | `E2 82 AC`    | `20 AC`       | `00 00 20 AC` |
| 😀      | geht nicht | geht nicht  | `F0 9F 98 80` | `D8 3D DE 00` | `00 01 F6 00` |
 
|                        | ASCII | ANSI  | UTF-8        | UTF-16        | UTF-32       |
|------------------------|-------|-------|--------------|---------------|--------------|
| Bit / Byte pro Zeichen | 7 Bit | 8 Bit | 1–4 Byte     | 2 oder 4 Byte | 4 Byte       |
| Anzahl Zeichen         | 128   | 256   | ganz Unicode | ganz Unicode  | ganz Unicode |
| Kompatibel mit ASCII   | –     | ja    | ja           | nein          | nein         |
 
## Typisches Problem: Zeichensalat
 
Wenn ein Text mit einer anderen Kodierung gelesen wird, als er gespeichert wurde, gibt es falsche Zeichen:
 
- **UTF-8 als ANSI gelesen:** Aus „ä“ wird **„Ã¤“**, weil die zwei Bytes `C3 A4` als zwei einzelne Zeichen gelesen werden.
- **ANSI als UTF-8 gelesen:** Aus „ä“ wird **„�“**, weil das Byte `E4` allein kein gültiges UTF-8 ist.
## Zusammenfassung
 
- **ASCII:** 128 Zeichen, nur Englisch
- **ANSI:** 256 Zeichen, aber jedes Land hat eine andere Codepage
- **Unicode:** eine Nummer für jedes Zeichen der Welt
- **UTF-8, UTF-16, UTF-32:** drei Arten, diese Nummern zu speichern. UTF-8 ist heute der Standard.

# Datenstrukturen – Übersicht
 
## 1. Hashmap / Hashtabelle
**Prinzip:** Schlüssel → Wert. Eine Hashfunktion bestimmt das Fach.
**Beispiel:** Garderobe: Nummer 42 → direkt zu Haken 42.
 
```
hash("Lena") = 3  →  [0: Tim] [1] [2] [3: Lena]
```
✅ sehr schnelles Suchen ❌ keine Sortierung
 
## 2. Binärer Suchbaum
**Prinzip:** Max. 2 Kinder pro Knoten. Links kleiner, rechts grösser.
**Beispiel:** Zahlenraten mit „höher / tiefer“.
 
```
      8
     / \
    3   10
   / \
  1   6
```
✅ schnelles Suchen ❌ ohne Balance wird er zur Kette
 
## 3. Linked List / Verkettete Liste
**Prinzip:** Jeder Knoten zeigt auf den nächsten.
**Beispiel:** Schnitzeljagd.
 
```
[A]──→[B]──→[C]──→ null
```
✅ schnelles Einfügen/Löschen ❌ langsames Suchen
 
## 4. Stack / Stapelspeicher (LIFO)
**Prinzip:** Oben rein, oben raus.
**Beispiel:** Tellerstapel, Ctrl+Z.
 
```
[C] ← zuerst raus
[B]
[A]
```
✅ letztes Element sofort ❌ kein Zugriff auf die Mitte
 
## 5. Heap
**Prinzip:** Baum, Eltern immer grösser (Max-Heap) oder kleiner (Min-Heap) als Kinder.
**Beispiel:** Chef steht immer oben.
 
```
     50
    /  \
  30    40
```
✅ Grösstes/Kleinstes sofort ❌ beliebig suchen
 
## 6. PriorityQueue / Vorrangwarteschlange
**Prinzip:** Wichtigstes zuerst raus. Meist mit Heap gebaut.
**Beispiel:** Notaufnahme im Spital.
 
```
Rein: Finger(2), Herzinfarkt(10), Beinbruch(6)
Raus: Herzinfarkt → Beinbruch → Finger
```
 
## 7. Queue / Warteschlange (FIFO)
**Prinzip:** Hinten rein, vorne raus.
**Beispiel:** Kassenschlange, Drucker.
 
```
raus ← [A] [B] [C] ← rein
```
✅ Reihenfolge bleibt ❌ kein Zugriff auf die Mitte
 
## Merksätze
- **Stack** = Tellerstapel, **Queue** = Kassenschlange
- **Heap** = das Wie, **PriorityQueue** = das Was
- **Suchbaum:** links < rechts, **Heap:** oben > unten
