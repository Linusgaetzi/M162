# Tag 2

# Wichtige Zahlensysteme in der Informatik

## Binär (BIN)
- Auch Zweiersystem oder Dualsystem
- Der Mikroprozessor arbeitet mit binären Zahlen
- Basis 2, Zeichen: 0, 1
- Beispiel: 0110'1011B
- Kennzeichnung mit B

## Dezimal (DEZ)
- Zehnersystem, das übliche System aus dem Alltag
- Basis 10, Zeichen: 0 bis 9
- Beispiel: 2025D
- Kennzeichnung mit D

## Hexadezimal (HEX)
- Sechzehnersystem, stellt Bitkombinationen platzsparend dar
- Verwendung: Speicheradressen, MAC-Adressen, IPv6-Adressen
- Basis 16, Zeichen: 0 bis 9 und A bis F (A = 10, B = 11, C = 12, D = 13, E = 14, F = 15)
- Beispiel: FF3CH oder 0xFF3C
- Kennzeichnung mit H oder in Programmiersprachen mit 0x

## Zusammenhang
- Eine Hex-Ziffer entspricht 4 Bit
- Beispiele: 1111B = FH, 9H = 1001B

---

## Aufgaben zur Zahlenumwandlung (Unsigned)

**1. Wandle die Dezimalzahl 27 in sein binäres "Unsigned" Äquivalent um.**

0001'1011

**2. Welchem Dezimalwert entspricht unsigned 1001'0011B?**

147

**3. Welchem hexadezimalen Wert entspricht unsigned 1011'0111B?**

B7

**4. Das letzte Oktet einer IP-Adresse lautet in Hexadezimal 3D. Welchem Binärwert entspricht dies?**

0011'1101

## Aufgaben zur Zahlenumwandlung (Signed)

**1. Wandle die Dezimalzahl 27 in sein binäres 8-Bit "Signed" Äquivalent um.**

0001'1011

(27 ist positiv, also gleich wie bei Unsigned. Das erste Bit ist 0.)

**2. Welchem Dezimalwert entspricht signed 1001'0011B?**

-109

(Das erste Bit ist 1, also ist die Zahl negativ. Alle Bits umkehren: 0110'1100B, dann 1 addieren: 0110'1101B = 109. Mit Minuszeichen ergibt das -109.)

# Datentypen

Beim Erstellen einer Variable (Programm, Tabellenkalkulation, Datenbank) muss man einen Datentyp wählen. Man unterscheidet numerische und alphanumerische Typen.

## Numerisch

**INTEGER (signed int)**
- Ganze Zahlen mit Vorzeichen
- Beispiel: -2, -1, 0, 1, 2
- Java: Integer = 32 Bit, Long = 64 Bit

**INTEGER (unsigned int)**
- Ganze positive Zahlen ohne Vorzeichen
- Beispiel: 0, 1, 2

**FLOAT**
- Fliesskommazahlen
- Beispiel: -2.1426
- Aufbau (32 Bit): 1 Bit Vorzeichen, 23 Bit Mantisse, 8 Bit Exponent, Basis 2
- Java: Float = 32 Bit, Double = 64 Bit

**BOOLEAN**
- Logischer Datentyp
- Beispiel: true, false

## Alphanumerisch

**CHARACTER (char)**
- Ein einzelnes Textzeichen
- Beispiel: A, b, 1, ?, +

Weitere Typen (Aufzählungstyp, Pointer usw.) sind in Modul 162 nicht relevant.

## Zusammengesetzt

**STRING, VARCHAR**
- Eine Textzeile, also eine Reihe von Zeichen (Array of Character)
- Beispiel: "Hello World!"

# Aufgaben zu Datentypen und Wertebereich

**1. Welchen Wertebereich (Dezimal) umfasst ein fiktiver 16Bit-Datentyp unsigned Integer?**

0 bis 65'535

**2. Welchen Wertebereich (Dezimal) umfasst ein fiktiver 16Bit-Datentyp signed Integer?**

-32'768 bis +32'767

**3. Wieviele Zeichen sind beim 8-Bit Datentyp Character möglich?**

256 Zeichen (2^8)

**4. Bestimmen Sie die minimale Anzahl Bits, die erforderlich sind, um Werte von 0D bis 999'999D zu speichern.**

20 Bit (2^19 = 524'288 ist zu wenig, 2^20 = 1'048'576 reicht)

**5. Bestimmen Sie die minimale Anzahl Bits, die erforderlich sind, um Werte von -999D bis +999D zu speichern.**

11 Bit (1'999 Werte, 2^10 = 1'024 ist zu wenig, 2^11 = 2'048 reicht)

**6. Eine Variable kann Werte von 0 bis 999 speichern und wird mit 16 Bit gespeichert. Bestimmen Sie die Redundanz.**

6 Bit (nötig wären 10 Bit, gespeichert werden 16 Bit)

**7. Normalisiere die Binärzahl 101101B.**

1,01101B × 2^5

**8. Eine Fliesskommazahl float vom Typ IEEE-754 Single Precision (32 Bit) enthält den Wert 300'000'000. Anschliessend wird der Wert um 1 erhöht (Inkrementiert). Welcher Wert wird gespeichert? Begründe deine Antwort.**

300'000'000 (bleibt gleich). Bei dieser Grösse kann der Float nur in 32er-Schritten zählen, weil die Mantisse nur 23 Bit hat. 300'000'001 ist nicht darstellbar und wird auf 300'000'000 gerundet.

**9. Eine Kundenkartei enthält bei jedem der 100'000 Kundeneinträge den Vermerk «Kundenkarte vorhanden» als Boolean. Wie gross ist der theoretisch minimale und wie gross der reale Speicherbedarf, wenn ein Boolean mit einem Byte gespeichert wird?**

Theoretisch: 100'000 Bit = 12'500 Byte (ca. 12,5 KB)
Real: 100'000 Byte (ca. 100 KB)


**10. Eine Datenbank enthält 5 Millionen Datensätze. Das Attribut «Wochentag» wird als INTEGER (4 Byte) gespeichert. Tatsächlich kommen nur die Werte 1 bis 7 vor. Diskutiere in deiner Gruppe, ob dieser Datentyp zweckmässig ist.**

Nein. Mit 4 Byte sind es 20 MB. Für die Werte 1 bis 7 reichen 3 Bit, in der Praxis 1 Byte (z. B. TINYINT), das wären nur 5 MB. Ein kleinerer Datentyp spart 15 MB und macht Abfragen etwas schneller.

# Alphanumerische Codes

## Auftrag 1 

- Nein, die Umlaute sind nicht korrekt dargestellt.
- <img width="566" height="168" alt="image" src="https://github.com/user-attachments/assets/c5fd5b9e-488d-467b-9149-74b21f021050" />

## Auftrag 2

- Ja, die Umlaute sind korrekt dargestellt
<img width="590" height="178" alt="image" src="https://github.com/user-attachments/assets/b8772660-7355-47bf-a82f-bb30e5c89cc8" />
- Der Html Code ist:
<img width="664" height="284" alt="image" src="https://github.com/user-attachments/assets/52f938b4-2f2e-4b01-a17c-21fdb89f8312" />
<img width="604" height="266" alt="image" src="https://github.com/user-attachments/assets/e3cefda9-50f5-4f32-8754-5203a367f3e6" />


