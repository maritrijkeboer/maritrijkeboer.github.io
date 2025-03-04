---
title: "Computational Musicology MR"
author: Marit Rijkeboer
output: 
  flexdashboard::flex_dashboard:
    storyboard: true
---
```{r setup, message = FALSE}
library(tidyverse)
source("compmus.R")
```
# Introduction
I created both songs on StableAudio.com
Links to an external site. after trying numerous AI generators. I tested almost every option on the Fairly Trained site, but only StableAudio.com
Links to an external site. worked well for me. To make the songs, I used various keywords to create a chill guitar vibe. Both are instrumental since I find AI vocals too robotic and can't sing myself, so I left out vocals. For song one, I used keywords like Post-Rock, Euphoric, and Sentimental (125 BPM). The second song features a 3/4 beat with Bright, Happy, and Surf vibes. Overall, I'm happy with the results and how natural they sound. 

---
# Visualisation

### track 1  
- **Approachability:** 0.493762344121933  
- **Arousal:** 4.817852020263672  
- **Danceability:** 0.1733139157295227  
- **Engagingness:** 0.6132141947746277  
- **Instrumentalness:** 0.5142947435379028  
- **Tempo:** 86  
- **Valence:** 4.824087142944336 

```{r}
"features/marit-r-1.json" |>                           # Change the track
  compmus_chroma(norm = "identity") |>                 # Change the norm
  ggplot(aes(x = time, y = pc, fill = value)) + 
  geom_raster() +
  scale_y_continuous(
    breaks = 0:11,
    minor_breaks = NULL,
    labels = c(
                "C", "C#|Db", "D", "D#|Eb",
                "E", "F", "F#|Gb", "G",
                "G#|Ab", "A", "A#|Bb", "B"
              )
  ) +
  scale_fill_viridis_c(guide = "none") +               # Change the colours?
  labs(x = "Time (s)", y = NULL, fill = NULL) +
  theme_classic() 
``` 

### track 2 
- **Approachability:** 0.8854424357414246  
- **Arousal:** 4.87969970703125  
- **Danceability:** 0.28600555658340454  
- **Engagingness:** 0.5910114645957947  
- **Instrumentalness:** 0.349807471036911  
- **Tempo:** 83  
- **Valence:** 5.514646530151367



```{r}
"features/marit-r-2.json" |>                           # Change the track
  compmus_chroma(norm = "identity") |>                 # Change the norm
  ggplot(aes(x = time, y = pc, fill = value)) + 
  geom_raster() +
  scale_y_continuous(
    breaks = 0:11,
    minor_breaks = NULL,
    labels = c(
                "C", "C#|Db", "D", "D#|Eb",
                "E", "F", "F#|Gb", "G",
                "G#|Ab", "A", "A#|Bb", "B"
              )
  ) +
  scale_fill_viridis_c(guide = "none") +               # Change the colours?
  labs(x = "Time (s)", y = NULL, fill = NULL) +
  theme_classic() 
```
