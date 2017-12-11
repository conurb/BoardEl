---
layout: post
title: Filtre RC - Fréquence de coupure
---

Ce post fait quelque part echo au précédent.

## Fréquence de coupure

Reprenons le cas de notre filtre RC passe-bas.

Par convention, la [fréquence de coupure][1] de notre filtre est définie à la fréquence pour laquelle on a une atténuation de 3 dB. On lit ça et là que cela représente une tension de sortie de 70.7% de la tension d'entrée (sans vraiment plus d'explication).

On lit également que pour une tension d'entrée ```Ue```, on aura une tension de sortie ```Us``` comme suit : ```Us = Ue/√2```

On retrouve bien une tension de sortie de 70.7% de notre tension d'entrée.

Pour un noob qui découvre l'électronique et les dB, tout ça n'est pas vraiment très explicite.

## D'où sort ce √2 ?

Je n'ai pas trouvé la réponse (finalement si! cf nb²) mais je suppose que ça vient d'un petit détour par la notion de puissance. En puissance, une atténuation de 3dB représente une diminution de 50% de la puissance initiale (en tension, ce serait une atténuation de 6dB qui représenterait une diminution de 50%).

Suivant la loi d'Ohm, la puissance peut se représenter par : ```P = U²/R```

Dans ce cadre, si on veut le double de puissance, il faut bien multiplier la tension par √2 (```2P = (√2U)²/R```). Évidemment, diviser la tension par √2 revient à diviser la puissance par 2.

Ok, on va admettre que ce √2 vient de là car c'est la meilleure explication que je peux m'en donner.

Ceci étant, c'est assez curieux car une meilleure réponse mathématique me semblerait être ```Us = Ue*10⁻³′²⁰```
dans la mesure où une atténuation de 3dB en terme de puissance n'est pas **exactement** une division par 2 de la puissance (10⁻³′¹⁰ = 0.5012); pour une tension, je ne cerne pas vraiment l'intérêt de re-passer par la notion de puissance (ce qui induit une approximation somme toute inutile bien qu'on s'en tape royalement).

Je fais aussi peut-être une erreur de raisonnement, personne est à l'abris.

nb¹:
Pour donner un exemple, en tant que bon gros noob, j'ai un moment envisagé que ce √2 ait un rapport avec les octaves. Après tout, puisque certains expriment la pente d'atténuation d'un [diagramme de Bode][3] en dB/octave plutôt qu'en dB/décade et que des octaves sont des doublements de fréquence, √2 aurait pu trouver sa place quelque part dans le monde des octaves ^^

nb²:
Au moment de linker '[fréquence de coupure][2]' vers l'article de wikimespieds, je me dis que ce serait bien de le lire (gros blaireau inside qui aurait sans doute dû commencer par là). Et là... :
> La puissance étant proportionnelle au carré de l'amplitude, l'amplitude du signal de sortie est atténuée de √(1/2) (≈ 0,707). 

C'est donc bien l'explication que je m'en suis donnée.

[1]: https://fr.wikipedia.org/wiki/Fr%C3%A9quence_de_coupure
[2]: https://fr.wikipedia.org/wiki/Fr%C3%A9quence_de_coupure#La_moitié_de_la_puissance
[3]: https://fr.wikipedia.org/wiki/Diagramme_de_Bode
