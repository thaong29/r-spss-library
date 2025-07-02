---
title: forestplots mit R für Hazarad Ratios
date: 2025-06-22
authors:
  - thao-nguyen
draft: true
summary: forestplot
tags:
  - SPSS
  - Statistik
---

```r 
# data labels + significance 
data <- data %>%
  mutate(
    varname = factor(varname, levels = rev(varname)),  #sonst sortiert ggplot2 coord_flip() die y-achse alphabetisch
    signif_label = ifelse(`p-value` < 0.05, "significant", "Not significant"),
         `HR [95% CI]` = sprintf("%.2f [%.2f – %.2f]", `Hazard Ratio`, conf.low, conf.high))
data$signif_label <- as.factor(data$signif_label)
#data$` ` <- paste(rep(" ", 20), collapse = " ")



# datatable
table_data <- data.frame(
  `HR [95% CI]`= data$`HR [95% CI]`,
  Cutpoint = data$cutpoint,
  `p-value` = data$`p-value`
)
colnames(table_data) <- c("HR [95% CI]", "Cutpoint", "p-value")  

table_grob <- tableGrob(table_data, rows = NULL, theme = ttheme_minimal(), heights = unit(c(rep(0.633,42)), "cm"))

# forestplot
plot <- ggplot(data, aes(x = varname,
                         y = `Hazard Ratio`,
                         ymin = conf.low, ymax = conf.high)) +
  geom_pointrange(aes(color = signif_label), size = 0.5) +
  geom_hline(yintercept = 1, linetype = "dashed", color = "grey40") +
  coord_flip() +
  theme_bw() +
  labs(title = " ",
       x = NULL, y = " ",
       color = "Significance") +
  theme(
    panel.grid = element_blank(),

    axis.ticks.y = element_blank(),
    axis.text = element_text(size = 10),
    axis.title = element_text(size = 12),
    plot.title = element_text(hjust = 0.5),
    legend.position = "top"
  ) +
  scale_color_manual(values = c("significant" = "red", "Not significant" = "black"))

plot_grob <- ggplotGrob(plot)

main_title <- textGrob("Hazard Ratios [95% CI] ", gp = gpar(fontsize = 14, fontface = "bold"))

grid.arrange(
  plot_grob,
  table_grob,
  ncol = 2,
  widths = c(1, 0.5),
  top = main_title
)

```