---
title: Interaktive Visualisierung mit R und ggplotly am Beispiel des Iris-Datensatz
date: 2025-06-26
authors:
  - thao-nguyen
summary: interaktive Plots
tags:
    - R
    - ggplot2
    - plotly
---

Mit Plotly werden Grafiken interaktiv: Zoomen, Verschieben und detaillierte Infos per Hover der Daten werden ermöglicht.

<iframe src="/blog/posts/r/ggplotly/mein_plot.html" width="100%" height="400px" frameborder="0"></iframe>

<!-- more -->

## Setup

Wir verwenden den `iris`-Datensatz und visualisieren eine Hauptkomponentenanalyse (PCA) mit **Plotly** für Interaktivität.

```r
# Notwendige Pakete laden
pacman::p_load(datasets, ggplot2, plotly)

# Daten vorbereiten
data(iris)
iris_data <- iris[, 1:4]  
# PCA durchführen
pca <- prcomp(iris_data, scale. = TRUE)
# als Data Frame
pca_df <- data.frame(pca$x, Species = iris$Species)

# ggplot - Objekt abspeichern
p <- ggplot(pca_df, aes(x = PC1, y = PC2, color = Species)) +
  geom_point(size = 3, alpha = 0.8) +
  labs(title = "PCA der Iris-Daten", x = "Hauptkomponente 1", y = "Hauptkomponente 2") +
  theme_minimal()

# hier mit ggplotly p aufrufen - das erstellt den interaktiven Plot
ggplotly(p)

```
