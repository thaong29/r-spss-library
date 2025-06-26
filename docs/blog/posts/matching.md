---
title: Matching
date: 2025-06-25
authors:
  - thao-nguyen
summary: matching recap
tags:
  - SPSS
  - Statistics
---

## Einführung

Matching ist eine Methode zur Kontrolle von Confounding in Beobachtungsstudien, bei der Versuchspersonen aus verschiedenen Gruppen anhand bestimmter Kovariaten gepaart oder ausgewählt werden.

Ziel: Vergleichbarkeit zwischen Gruppen erhöhen (z. B. Behandlungs- vs. Kontrollgruppe), um kausale Effekte besser abschätzen zu können.

Typische Anwendung: In retrospektiven Kohortenstudien oder Fall-Kontroll-Studien.

<!-- more -->

---

## Arten des Matchings

### 1. **Exact Matching**
- Beobachtungen werden nur gepaart, wenn alle Matching-Variablen exakt übereinstimmen.
- Vorteil: Sehr genaue Kontrolle.
- Nachteil: Viele Beobachtungen bleiben ungematcht → Verlust von Daten.

### 2. **Propensity Score Matching (PSM)**
- Berechnet für jede Person die Wahrscheinlichkeit, einer Gruppe (z. B. Behandlung) zugeordnet zu werden, basierend auf Kovariaten.
- Danach werden Individuen mit ähnlichem Score gematcht (z. B. nearest neighbor).
- Vorteil: Flexibler und breiter anwendbar.
- Tools: R (`MatchIt`, `twang`), SPSS (via Extension Bundles oder manuell mit PS-Berechnung).

### 3. **Mahalanobis Matching**
- Abstand zweier Beobachtungen wird basierend auf Kovariaten und ihrer Korrelation berechnet.
- Meist in Kombination mit Propensity Score verwendet.

---

