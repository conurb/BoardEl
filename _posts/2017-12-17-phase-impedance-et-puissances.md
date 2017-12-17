---
layout: post
title: Phase, impédance et puissances
---

J'ai eu beaucoup de mal à cerner le réel impact de la phase. Le déclic s'est fait à la lecture de [cet article de wikipédia][1].

Petit débriefing sur ce que j'ai compris. Je rappelle que je suis un gros noob en matière d'électronique (et d'électricité), je ne prétends pas détenir la vérité sur ce qui suit, il s'agit juste de la représentation que je m'en fais.

## La puissance

```P = UI```

### Cas d'une résistance

![R POWER][11]

Imaginons une résistance toute seule dans un circuit. Il n'y a pas de décalage de phase entre la tension et l'intensité au niveau d'une résistance. Les courbes respectives de la tension et de l'intensité coupent l'axe des abscisses en même temps. La tension et l'intensité ont ainsi tout le temps le même signe puisqu'en phase. Le résultat est une sinusoïde de la puissance qui est tout le temps positive (```P=UI```).

Il y a bien génération de puissance et, pour une résistance, la dissipation de la puissance générée se manifeste sous forme de chaleur (effet Joule).

### Cas d'une bobine

![L POWER][12]

Imaginons un circuit avec une bobine seule. La phase est alors décalée de 90° et la tension devance l'intensité. Lorsque la tension et l'intensité sont de même signe, la puissance est positive mais lorsque la tension et l'intensité sont de signes opposés, on obtient une puissance équivalente négative. Au final, cela signifie que la puissance est tour à tour consommée et retournée à la source.

Autrement dit, on ne génère pas de puissance utile, 'utile' au sens utilisable sous forme de puissance mécanique, de lumière, de dissipation de chaleur, etc... Il y a bien **consommation de courant** (intensité) mais pas pour ce qui nous intéresse généralement, c'est à dire produire de la puissance utile permettant d'effectuer un travail.

À noter que le raisonnement serait à peu près le même avec un condensateur sinon que, pour ce qui concerne le déphasage, c'est l'intensité qui devancerait la tension.

### Cas d'une bobine avec une résistance

Avec une bobine et une résistance en série dans un circuit, le courant étant partout le même, on sent bien qu'une partie du courant ne sera pas utilisé à des fins de puissance utile. Même si le courant et la tension sont toujours en phase pour la résistance, il n'en est pas de même pour la bobine. Globalement, notre circuit utilise plus de courant (intensité) qu'il n'est nécessaire pour produire de la puissance utile.

### Petite synthèse

Avec ```P=UI```, on peut déjà s'étonner d'obtenir comme résultat parfois une puissance 'utile' et parfois une puissance 'inutile' suivant le type de dipôle utilisé (résistance vs bobine ou condensateur).

C'est là qu'intervient l'article de wikipédia : les termes 'utile' et 'inutile' étant mes propres termes, on va les remplacer par les termes utilisés par les électriciens et/ou électroniciens.

Ce que j'appelais jusqu'à maintenant la puissance 'utile' est en fait **la puissance active** et ce que j'appelais la puissance 'inutile' est en fait **la puissance réactive**. Alors que nous donne donc ```P=UI``` ? c'est **la puissance apparente**, une somme au sens pythagoricien du terme des 2 autres puissances.

## L'impédance

À la vue de ce qui précède, il semblerait que si on calcue la puissance (```P=UI```), une résistance va nous répondre en puissance active alors qu'une bobine ou un condensateur vont nous donner une puissance réactive. D'où cela vient-il ? cela vient de la façon dont s'oppose un dipôle au passage d'un courant alternatif (sinusoïdal), c'est ce qu'on appelle [l'impédance][2].

Pour résumer, l'impédance est au courant alternatif (AC) ce que la résistance est au courant continu (DC). Le petit nom de l'impédance étant ```Z```, on a par exemple la loi d'Ohm qui devient ```U = ZI``` au lieu de ```U = RI```.

Et pour bien prendre conscience que la notion d'impédance est le pendant de la résistance en DC, l'impédance s'exprime également en ohm (Ω).

Pour prendre un premier contact avec la notion d'impédance sans mathématique, il faut aller voir sur la chaine youtube de Thonain : [L'impédance][3].

De notre côté, passons par les mathématiques, non par pur plaisir mais parce que ça permet de bien mieux comprendre. Mathématiquement, l'impédance est un nombre complexe : ```Z = R + jX```. La partie réelle ```R``` est ce qu'on connait déjà en courant continu, c'est purement de la résistivité, rien de nouveau. La partie imaginaire ```X``` est ce qu'on appelle la réactance.

Pour comprendre ce qui suit, on a juste besoin de se rappeler d'une caractéristique très simple des nombres complexes. Il faut imaginer un cercle dans le plan complexe (comme un cercle trigonométrique). Lorsqu'on multiplie par ```j```, on effectue une rotation de +90° sur ce cercle et lorsqu'on multiplie par ```-j```, on effectue une rotation de -90° (hum... vous la sentez venir notre histoire de déphasage de 90° ? ^^).

### L'impédance d'une résistance

Pour une résistance, c'est très simple, il n'y a pas de partie imaginaire, donc ```Z = R```. SAILAFAITE™ ! \o/

### L'impédance d'une bobine

Pour un premier contact avec l'impédance d'une bobine sans aspect mathématique, il faut aller voir [la vidéo de Thonain][6] sur le sujet.

Pour une bobine, il n'y a pas de partie réelle, c'est un imaginaire pur : ```Z = jωL```. ```L``` est la caractéristique de la bobine, elle s'exprime en [henry][4]. Quant à ```ω```, c'est la pulsation (ou la vitesse angulaire) exprimée en radians/s; elle correspond à 2πf, c'est à dire 2π fois la fréquence.

Pour faire un parallèle avec la vidéo de Thonain, si on ne regarde que la partie imaginaire de l'impédance d'une bobine (```ωL```), c'est ce qu'on appelle la réactance (la partie ```X``` de ```Z```, cf plus haut dans la définition de l'impédance). Pour une bobine, on parle de réactance inductive. On voit très bien que la réactance d'une bobine est proportionnelle à la fréquence. En d'autres termes, plus la fréquence sera élevée, plus la bobine s'opposera ou résistera au courant. On peut voir ça comme une résistance variable dont la valeur en ohm (Ω) changerait en fonction de la fréquence. Plus la fréquence est élevée, plus sa résistance en Ω augmente. Le mot 'réactance' prend tout son sens.

Que fait-on de notre ami ```j``` ? et bien, comme dit précédemment, mathématiquement, cela fait prendre un angle de +90° à notre impédance. On doit pouvoir dire que la réactance devient une impédance avec un angle de 90°. La loi d'Ohm nous dit que ```I = U/Z```, donc, quel que soit l'angle de phase de la tension ```U```, le fait de la diviser par une impédance avec un angle de +90° nous donne une intensité (courant) avec un déphasage de -90° par rapport à la tension (rappel pour ceux qui ont oublié: lorsqu'on divise un complexe par un complexe, les angles se soustraient donc imaginons une tension avec un angle de phase de 0, 0 - 90° = -90°).

### L'impédance d'un condensateur

Il n'y a pas non plus de partie réelle, l'impédance d'un condensateur est ```Z = -j/ωC```. ```C``` est la caractéristique du condensateur, elle s'exprime en [farad][7].

Si on ne se préoccupe que de la partie imaginaire, ce qu'on appelle la réactance capacitive pour un condensateur (```1/ωC```), on voit bien qu'elle est inversement proportionnelle à la fréquence. Plus la fréquence est faible, plus la résistance ou son opposition au courant est forte.

Concernant ```j```, rotation de -90° de l'impédance, donc déphasage de +90° du courant par rapport à la tension.

#### Gros aparté
En électricité, je me rends compte qu'il est très difficile de savoir quoi provoque quoi. C'est un peu perpétuellement l'histoire de l'oeuf et de la poule. La loi d'Ohm ```U = ZI``` qui est une loi que je qualifierais d'équation instantanée n'aide absolument pas à différencier la cause de la conséquence. Dans le cas d'une bobine, ma sensation 'mathématique' sur le sujet est que c'est la tension qui détermine le courant. À contrario, pour un condensateur, j'aurais tendance à penser que c'est le courant qui détermine la tension. Mathématiquement, l'intuition que j'ai (ou plutôt que je m'en fais), c'est qu'une intégrale est plus que souvent la cause et la dérivée une conséquence et si je regarde ```U = L dI/dt``` pour une bobine ou ```I = C dU/dt``` pour un condensateur, c'est ce que j'en tire comme conclusions personnelles.
Elles n'engagent que moi.

L'électricité/électronique est un domaine de l'invisible, les mathématiques sont parfaites pour se donner une idée de ce qui s'y passe mais ça ne reste qu'un outil pour tenter de donner une interprétation du réel. Sincèrement, comment expliquer rationnellement cette notion de déphasage sans mathématique ? comment expliquer ce déphasage de π/2 ? après tout, pourquoi ce ne serait pas π/3 ou 5/4 ou que sais-je encore ?


## Les différentes puissances

L'impédance, suivant le dipôle (composant), déphase ou non le courant par rapport à la tension. On peut voir mathématiquement que c'est la partie imaginaire qui provoque ce déphasage. Il n'y a donc rien d'étonnant d'affecter un type de puissance à chaque partie. On peut voir cela comme une puissance réelle (puissance active basée sur la partie réelle du complexe), une puissance imaginaire (puissance réactive basée sur la partie imaginaire du complexe) et une puissance totale (puissance apparente, qu'on peut voir comme la somme).

Ainsi une bobine ou un condensateur ne génère aucune puissance active mais uniquement de la puissance réactive alors que ce sera l'inverse pour une résistance. La puissance d'un circuit composé de ces types de composants aura bien évidemment une partie de puissance active et une partie de puissance réactive.

Évidemment, pour un circuit, si on cherche de la puissance active, celle qu'on recherche généralement, on va faire la chasse à la partie imaginaire (puissance réactive) consommatrice inutile de courant, ce qui correspond à chercher à maximiser le fameux cos(φ).

### Puissance active

La partie réelle est alors la puissance active, c'est celle qui nous intéresse réellement (sans jeu de mot). On peut l'exprimer en fonction de R et donne des [watts][8].

```
P = RI²
```

### Puissance réactive

La partie imaginaire représente la puissance réactive générée par les inductances et capacitances (bobine et condensateur). Elle se base donc sur X (la réactance), s'exprime en volt-ampère-réactif (VAR) et s'appelle Q.

```
Q = XI²
```

### Puissance apparente

C'est la puissance qui représente la somme (au sens pythagoricien du terme) des 2 autres puissances. Elle se base donc sur Z (l'impédance), s'exprime en volt-ampère (VA) et s'appelle S.

```
S = ZI²
```

Si on prend un multimètre, qu'on mesure la tension et l'intensité et qu'on calcule la puissance (UI), c'est cette puissance apparente qu'on obtient et non la puissance active.

nb₁: toutes les valeurs X, Z, I sont les modules des différents complexes, ce sont donc des scalaires (mode pythagore ON). Pour le dire simplement, ce sont des nombres.

Ces différentes puissances forment un triangle dans le plan complexe dont on peut voir une illustration sur la page wikipédia (au même titre que l'impédance est également un triangle dans le plan complexe).

## Facteur de puissance : cosinus φ

[Le facteur de puissance][9] est le fameux cos(φ) où φ est l'angle de notre triangle des puissances entre la puissance apparente et la puissance active. C'est le ratio de la puissance utile (puissance active) sur la puissance totale (puissance apparente) (```P/S```).

On comprendra aisément que le but du jeu est d'obtenir un cos(φ) le plus proche possible de 1 afin de minimiser l'utilisation du courant pour de la puissance réactive. Mathématiquement, la chasse à la partie imaginaire est ouverte.

Pour finir, un [petit dessin animé][10] d'un autre âge sur le sujet ;)


[1]: https://fr.wikipedia.org/wiki/Puissance_en_r%C3%A9gime_alternatif
[2]: https://fr.wikipedia.org/wiki/Imp%C3%A9dance_(%C3%A9lectricit%C3%A9)
[3]: https://www.youtube.com/watch?v=kg4QY2DTKuY
[4]: https://fr.wikipedia.org/wiki/Henry_(unit%C3%A9)
[5]: https://www.youtube.com/watch?v=7a2kpCB8U0I
[6]: https://www.youtube.com/watch?v=7a2kpCB8U0I
[7]: https://fr.wikipedia.org/wiki/Farad
[8]: https://fr.wikipedia.org/wiki/Watt
[9]: https://fr.wikipedia.org/wiki/Facteur_de_puissance
[10]: https://www.youtube.com/watch?v=IURKavCBUkE
[11]: https://conurb.github.io/BoardEl/assets/img/rpower.png "R Power"
[12]: https://conurb.github.io/BoardEl/assets/img/lpower.png "L Power"
