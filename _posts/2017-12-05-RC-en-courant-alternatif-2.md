---
layout: post
title: RC - Résistance et condensateur (courant alternatif) - 2
---
# Résistance et condensateur (courant alternatif) - 2

Je me suis rendu compte que [Thonain][1] avait fait [une autre vidéo][2] juste avant celle que j'ai utilisée pour tester quelques calculs.
C'est exactement le même montage : 1 résistance (même valeur), 1 condensateur (même valeur).
Mais, dans ce montage, le condensateur est avant la résistance et il prend la tension aux bornes du condensateur.

Compte tenu de ces 2 vidéos, se pose à moi une question.

#### L'ordre des composants a-t-il une importance ?

Thonain précise dans la 2ème vidéo "*on va cette fois mettre le condensateur en premier et la résistance en second*" comme si cela avait une importance. Me voilà perplexe car, d'après ce que j'avais compris et les calculs effectués, l'ordre des composants dans ce circuit en série n'a dans ce cas strictement aucune importance.

Bon... en tant que noob total, j'étais réellement dubitatif devant tout ça. Pourquoi diable faire 2 vidéos puisqu'on pourrait avoir tous ces résultats avec une seule vidéo où on fait les 2 mesures (1 mesure aux bornes de la résistance et 1 mesure aux bornes du condensateur) ? 

Au bout d'un moment, le déclic se fait sur la subtilité qu'il faut comprendre :
- **Il faut imaginer un circuit secondaire qui serait matérialisé par l'oscilloscope**.
- Si ce circuit imaginaire part des bornes du condensateur, on obtient un filtre passe-bas.
- Si ce circuit imaginaire part des bornes de la résistance, on obtient un filtre passe-haut.

Après recherche, ceci correspond alors à ce type de schéma :

![filtres][3]





[1]: https://www.youtube.com/playlist?list=PLu-QLFNiuxva1LY5CyBa7UJBZkIh5bi_G
[2]: https://www.youtube.com/watch?v=E1-M3a2ZbUk
[3]: /assets/img/filtres-pb-ph.png "Filtres"
