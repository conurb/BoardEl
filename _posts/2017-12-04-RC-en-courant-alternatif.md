---
layout: post
title: RC - Résistance et condensateur (courant alternatif)
---

# Résistance et condensateur (courant alternatif)

Quelques calculs basés sur la vidéo de [Tronik Aventur n°135][1] - Filtre passe haut pour les nuls

N'ayant pas de matériel, j'utilise cette vidéo pour tenter de comprendre et contrôler quelques concepts appris.

```
Données fiables :
C 100 nF
R 1 kΩ
```

```
Données approximatives :
 30 Hz ≃ 0V
120 Hz ≃ < 0.25V
380 Hz ≃ entre 0.75V et 0.88V
530 Hz ≃ 1V
20 KHz ≃ entre 2.75V et 3V
```

Selon [ce topic][2], la tension de la sortie audio doit être de 3V [RMS][2] P-P. C'est à peu près ce qui est constaté dans la vidéo à 20 KHz (fréquence la plus élevée). On assume la phase à 0 suivant l'écran du Generator (à 2:58).

Pour une fréquence donnée, on doit avoir :
- la même pulsation ω pour tout le circuit
- différentes phases φ
- différentes amplitudes (la tension)

```
rappel sur un complexe en notation polaire :
ex: 4 ∠ 33°
partie réelle     = 4 cos 33°
partie imaginaire = 4 sin 33°
```

```
notes sur l'impédance :
Z = R + jX
R = résistance (partie réelle)
X = réactance (partie imaginaire)
```

Dans le circuit :
- La résistance joue donc son rôle de résistance (partie réelle).
- Le condensateur joue le rôle de réactance (partie imaginaire).

```
Rappels :
La pulsation ω est 2πf (nb de radians/s, c'est la vitesse angulaire).
L'impédance d'un condensateur est 1/jωC (ou -j/ωC).
La réactance du condensateur à 380 Hz est par exemple de 1/(2π*380*10⁻⁷) = 4188,288 Ω
```

Résultats trouvés :
```
                       |     impédance totale      |
  f    | réactance     |   (1000 - j*réactance)    |         I
 30 Hz | 53 051,6477 Ω | 53 061,0716 Ω ∠ -88,920°  |  56,539 μA ∠ 88,920°
120 Hz | 13 262,9119 Ω | 13 300,5576 Ω ∠ -85,688°  | 225,549 μA ∠ 85,688°
380 Hz |  4 188,2880 Ω |  4 306,0140 Ω ∠ -76,571°  | 696,700 μA ∠ 76,571°
530 Hz |  3 002,9234 Ω |  3 165,0512 Ω ∠ -71,582°  | 947,852 μA ∠ 71,582°
20 KHz |     79,5775 Ω |  1 003,1613 Ω ∠ -4,550°   |   2,991 mA ∠ 4,550°

Tension aux bornes de la résistance
 30 Hz | 0,057 V ∠ 88,920°
120 Hz | 0,226 V ∠ 85,688°
380 Hz | 0,697 V ∠ 76,571°
530 Hz | 0,948 V ∠ 71,582°
20 KHz | 2,991 V ∠ 4,550°
```



À part pour 380 Hz et compte tenu des marges d'erreur des composants, ces résultats concordent avec ceux lus à l'oscilloscope.

*On note que la tension aux bornes de la résistance a le même angle de phase que le courant (le courant et le voltage sont en phase
au niveau de la résistance). Ce doit être tout le temps le cas (incidence de l'abscence de partie imaginaire).*

Qu'en est-il aux bornes du condensateur ?
```
Tension aux bornes du condensateur
 30 Hz | 2,992 V ∠ -1,08°
120 Hz | 2,991 V ∠ -4,312°
380 Hz | 2,918 V ∠ -13,429°
530 Hz | 2,846 V ∠ -18,418°
20 KHz | 0,238 V ∠ -85,45°
```

*La tension aux bornes du condensateur est toujours déphasée de 90° par rapport au courant. Pour un condensateur, la tension est en retard de 90° sur le courant.*


[1]: https://www.youtube.com/watch?v=tEaAYzol4ZM
[2]: https://electronics.stackexchange.com/questions/37926/what-is-the-typical-max-voltage-out-of-a-pc-speaker-jack
[3]: https://fr.wikipedia.org/wiki/Valeur_efficace
