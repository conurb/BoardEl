---
layout: post
title: Gain dB - Pourquoi utiliser 20log pour la tension et l'intensité ?
---
# Gain dB - Pourquoi utilise-t-on 20log pour la tension et l'intensité ?

Avec cette histoire de filtres passe-bas et passe-haut, ce n'est pas un lièvre qui a été levé mais tout le terrier. J'y reviendrai plus tard le temps de mettre mes idées au clair mais, en étudiant les filtres, on utilise 20log pour déterminer le gain. 

Un dB mesure un accroissement entre 2 valeurs. Si on a 2 puissances P₁ et P₂, on utilise par exemple 10log(P₂/P₁) alors pourquoi utiliser 20log lorsqu'il s'agit de tension ou d'intensité ?

Pour comprendre, imaginons une résistance R et qu'on fasse varier la tension (on passe par exemple de U₁ à U₂).
En tension, d'après la loi d'Ohm, les 2 puissances correspondantes peuvent s'écrire :
```
$$P₁ = U₁^2/R$$
P₁ = U₁²/R
P₂ = U₂²/R
P₂/P₁ = U₂²/U₁² = (U₂/U₁)²

Le gain est :
10log(P₂/P₁) = 10log((U₂/U₁)²) = 2*10log(U₂/U₁) = 20log(U₂/U₁)
```

Prenons un exemple avec une résistance de 1Ω, U₁ à 3V et U₂ à 6V :
```
Calcul avec les tensions:
U₁ = 3V
U₂ = 6V
→ multiplication par 2
Gain: 20log(6/3) = 6,02 dB

Calcul avec les puissances:
P₁ = U₁²/R = 9W
P₂ = U₂²/R = 36W
→ multiplication par 4
Gain: 10log(36/9) = 6,02 dB
```

**Ainsi, qu'on raisonne en puissance ou en tension, l'accroissement en dB est le même**.

Donc, en puissance ou en énergie, on utilise 10log, en tension ou en intensité, on utilise 20log.
