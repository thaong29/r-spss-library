---
title: t-Tests mit SPSS
date: 2025-06-24
authors:
  - thao-nguyen
summary: "Vergleich zweier Gruppen mit t-Tests in SPSS: Unabhängige und gepaarte Stichproben."
tags:
  - SPSS
  - Statistik
  - t-Test
  - Vergleich
---

Der *t-Test* ist eine der am häufigsten verwendeten Methoden zum Vergleich von Mittelwerten zwischen zwei Gruppen. In SPSS lassen sich sowohl **t-Tests für unabhängige Stichproben** als auch **t-Tests für verbundene Stichproben** (gepaarte t-Tests) einfach über die Benutzeroberfläche durchführen.

Diese Anleitung zeigt Schritt für Schritt, wie man beide Testarten in SPSS ausführt.

<figure markdown="span">
  ![cover](assets/t-test/t-test.png){ width="600" }
  <figcaption>Quelle: Investopedia</figcaption>
</figure>

<!-- more -->

## Vergleich zweier Gruppen in SPSS: t-Tests

Verwende t-Tests, wenn du prüfen möchtest, ob sich die **Mittelwerte zweier Gruppen signifikant unterscheiden**.

---

### 1. t-Test für unabhängige Stichproben

Verwende diesen Test, wenn du **zwei verschiedene Gruppen** vergleichst, z. B. Behandlung A vs. Behandlung B.

**Beispiel:**  
Unterscheidet sich der systolische Blutdruck zwischen Patienten, die mit Medikament A behandelt wurden, und denen, die Medikament B erhielten?

**Vorgehen:**
- Menü: `Analysieren` → `Mittelwerte vergleichen` → `T-Test bei unabhängigen Stichproben`
- Verschiebe deine **abhängige Variable** (z. B. Blutdruck) in *Testvariable(n)*
- Verschiebe deine **Gruppenvariable** (z. B. Therapiegruppe) in *Gruppierungsvariable*
- Klicke auf `Gruppen definieren` → Gib die beiden Gruppenwerte an (z. B. 1 = A, 2 = B)
- Klicke auf `OK`



**Die Ausgabe enthält:**
- Gruppenmittelwerte und Standardabweichungen
- Levene-Test zur Varianzgleichheit
- t-Wert, Freiheitsgrade und p-Wert

**Interpretationstipp:**
- Verwende **Varianzen nicht gleich angenommen**, wenn der Levene-Test signifikant ist (*p < 0,05*)
- Ist der p-Wert des t-Tests kleiner als 0,05, liegt ein signifikanter Unterschied vor

---

### 2. t-Test für verbundene Stichproben (gepaarte Stichproben)

Verwende diesen Test, wenn du **zwei Messwerte derselben Personen** vergleichst, z. B. vor und nach einer Behandlung.

**Beispiel:**  
Ändert sich der Lebensqualitätswert vor und nach einer Intervention?

**Vorgehen:**
- Menü: `Analysieren` → `Mittelwerte vergleichen` → `T-Test bei verbundenen Stichproben`
- Wähle zwei verbundene Variablen aus (z. B. `QoL_Vorher` und `QoL_Nachher`)
- Klicke auf `OK`



**Die Ausgabe enthält:**
- Mittelwertdifferenz zwischen den Zeitpunkten
- t-Wert, Freiheitsgrade und p-Wert

**Interpretationstipp:**
- Ein **signifikanter p-Wert (< 0,05)** zeigt, dass sich die Variable über die Zeit verändert hat

---

### 3. Voraussetzungen und Alternativen

**Voraussetzungen:**
- Abhängige Variable metrisch (Intervall- oder Verhältnisskala)
- Annähernd normalverteilte Daten (besonders bei kleinen Stichproben)
- t-Test für unabhängige Stichproben: Gruppen sind unabhängig
- t-Test für verbundene Stichproben: Messwerte stammen von denselben Personen

**Wenn Voraussetzungen verletzt sind:**
- Verwende **Mann-Whitney-U-Test** (für unabhängige Stichproben)
- Verwende **Wilcoxon-Vorzeichen-Rang-Test** (für verbundene Stichproben)

---

### 4. Ergebnisse berichten

**Beispiel (unabhängiger t-Test):**

> Der mittlere systolische Blutdruck war in Gruppe A signifikant höher (M = 130,5, SD = 12,3) als in Gruppe B (M = 124,8, SD = 11,7), *t*(100) = 2,45, *p* = 0,016.

**Beispiel (gepaarter t-Test):**

> Die Lebensqualitätswerte stiegen nach der Behandlung signifikant an (Vorher: M = 55,2, SD = 8,1; Nachher: M = 62,4, SD = 7,5), *t*(49) = −4,68, *p* < 0,001.

---
