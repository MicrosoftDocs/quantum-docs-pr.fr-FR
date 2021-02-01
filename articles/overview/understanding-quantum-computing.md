---
title: Fonctionnement de l’informatique quantique
description: Que sont les ordinateurs quantiques et comment utilisent-ils les principes de la mécanique quantique ?
author: bradben
ms.author: v-benbra
ms.date: 5/5/2020
ms.topic: overview
uid: microsoft.quantum.overview.understanding
no-loc:
- Q#
- $$v
ms.openlocfilehash: c6c6249fd56c6fb65550c81ffee902eca555b0cd
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855104"
---
# <a name="understanding-quantum-computing"></a>Fonctionnement de l’informatique quantique

L’informatique quantique utilise les principes de la mécanique quantique pour traiter les informations. C’est la raison pour laquelle l’informatique quantique nécessite une approche différente de l’informatique classique. L’une des différences est le processeur qui équipe les ordinateurs quantiques. Là où les ordinateurs classiques utilisent des puces de silicium connues, les ordinateurs quantiques utilisent des systèmes quantiques (systèmes dans lesquels nous pouvons contrôler les propriétés et comportements uniques de la mécanique quantique) tels que les atomes, les ions, les photons ou les électrons. Tandis que les ordinateurs classiques utilisent des valeurs haute et basse basées sur la logique binaire, respectivement 1 et 0, les ordinateurs quantiques utilisent leurs propriétés quantiques pour représenter les bits qui peuvent être préparés dans différentes superpositions quantiques de 1 et 0.  

Le matériel quantique se comporte selon les lois de la mécanique quantique, en appliquant des concepts tels que le calcul probabiliste, la superposition et l’intrication. Ces concepts sont à la base des algorithmes quantiques qui exploitent la puissance de l’informatique quantique pour résoudre des problèmes complexes. Cet article décrit quelques-uns des concepts fondamentaux de la mécanique quantique sur laquelle repose l’informatique quantique.

## <a name="a-birds-eye-view-of-quantum-mechanics"></a>Vue d’ensemble de la mécanique quantique

La mécanique quantique, également appelée théorie quantique, est une branche de la physique qui étudie les particules aux niveaux atomique et subatomique. Toutefois, un grand nombre des lois de la mécanique que vous tenez pour acquises ne s’appliquent pas au niveau quantique. La superposition, la mesure quantique et l’intrication sont trois phénomènes qui sont au cœur de l’informatique quantique.  

### <a name="superposition-vs-binary-computing"></a>Superposition et informatique binaire

Imaginez que vous êtes en train de faire de l’exercice dans votre salon. Vous vous tournez entièrement vers la gauche, puis entièrement vers la droite. À présent, vous essayez de vous tourner vers la gauche et vers la droite en même temps. C’est impossible à faire, à moins de vous couper en deux !  Vous ne pouvez évidemment pas être dans ces deux états simultanément : être face au côté gauche et face au côté droit au même moment.

En revanche, si vous étiez une particule quantique, vous pourriez avoir une certaine probabilité d’être *face au côté gauche* ET une certaine probabilité d’être *face au côté droit* grâce à un phénomène connu sous le nom de **superposition** (ou **cohérence**).

Une particule quantique telle qu’un électron a ses propres propriétés « face au côté gauche ou face au côté droit », par exemple le **spin**, qui correspond à une position vers le haut ou vers le bas ou, pour reprendre des termes de l’informatique binaire classique, à une valeur 1 ou 0. Quand une particule quantique est dans un état de superposition, elle peut avoir une combinaison linéaire d’états possibles infinis entre 1 et 0, mais vous ne savez pas dans quel état elle est tant que vous ne l’avez pas examiné réellement, ce qui conduit au phénomène suivant, la **mesure quantique**.

### <a name="quantum-measurement"></a>Mesure quantique

À présent, supposons qu’un de vos amis arrive chez vous et souhaite vous prendre en photo pendant vos exercices. Il est presque certain que la photo qu’il prendra de vous sera floue et que sur cette photo, vous ne serez pas entièrement tourné vers la gauche ni vers la droite.

Mais si vous étiez une particule quantique, un phénomène intéressant se produirait. Indépendamment de votre position au moment de la prise de la photo, vous seriez toujours entièrement tourné vers la gauche ou vers la droite sur la photo. Il n’y aurait pas de position intermédiaire.

Cela est dû au fait que l’action consistant à observer ou à mesurer une particule quantique **réduit** l’état de superposition (c’est ce qu’on appelle aussi la **décohérence**) et que la particule prend un état binaire classique de 1 ou 0.

Cet état binaire nous est utile, car en informatique, vous pouvez faire beaucoup de choses avec les valeurs 1 et 0. Cependant, une fois qu’une particule quantique a été mesurée et réduite, elle reste toujours dans ce même état (exactement comme votre photo), à la valeur 1 ou 0. Mais comme vous le verrez plus tard, en informatique quantique, certaines opérations peuvent « réinitialiser » une particule à un état de superposition afin de rendre possible son utilisation dans d’autres calculs quantiques.

### <a name="entanglement"></a>Intrication

Le phénomène le plus intéressant de la mécanique quantique est peut-être l’**intrication**, qui peut lier deux particules quantiques ou plus entre elles. Quand plusieurs particules sont intriquées, elles forment un système unique où l’état quantique d’une particule ne peut pas être représenté indépendamment de l’état quantique des autres particules. En d’autres termes, quand vous appliquez une opération ou un processus à une particule, cela se fait en corrélation avec les autres particules.

En plus de cette interdépendance, les particules sont capables de conserver ce lien même si une très grande distance, jusqu’à des années-lumière, les sépare. Les effets de la mesure quantique s’appliquent également aux particules intriquées : quand une particule est mesurée et réduite, l’autre particule est réduite également. Du fait de la corrélation entre les qubits intriqués, la mesure de l’état d’un qubit fournit aussi des informations sur l’état de l’autre qubit. Cette propriété particulière est très utile dans le domaine de l’informatique quantique.

### <a name="qubits-and-probability"></a>Qubits et probabilité

Les ordinateurs classiques stockent et traitent les informations en bits, qui peuvent avoir l’état 1 ou 0, mais jamais les deux à la fois. En informatique quantique, l’équivalent est le **qubit**, qui représente l’état d’une particule quantique. Avec le phénomène de superposition, un qubit peut avoir la valeur 1, la valeur 0 ou toute autre valeur intermédiaire. Selon sa configuration, un qubit a une certaine *probabilité* d’être réduit à 1 ou à 0. La probabilité de réduction d’un qubit dans un sens ou l’autre est déterminée par l’**interférence quantique**.

Vous vous souvenez de l’ami qui vous prenait en photo ? Supposons que son appareil photo comporte des filtres spéciaux appelés filtres d’*interférence*. Si votre ami sélectionne le filtre *70/30* avant de commencer à prendre des photos, sur 70 % des photos, vous serez tourné vers la gauche et sur 30 % d’entre elles, vous serez tourné vers la droite. En effet, le filtre perturbe l’état normal de l’appareil photo pour influencer la probabilité de son comportement.

De la même façon, l’interférence quantique change l’état d’un qubit en vue d’influencer la probabilité d’obtenir un résultat donné pendant la mesure. Cet état probabiliste donne toute la mesure de la puissance de l’informatique quantique.

Par exemple, avec deux bits dans un ordinateur classique, chaque bit pouvant stocker 1 ou 0, vous pouvez stocker quatre valeurs possibles (**00**, **01**, **10** et **11**), mais uniquement l’une de ces valeurs à la fois. Avec deux qubits en superposition, chaque qubit peut être 1 ou 0 ou *les deux*, ce qui vous permet de représenter les mêmes quatre valeurs simultanément. Avec trois qubits, vous pouvez donc représenter huit valeurs, avec quatre qubits, 16 valeurs, et ainsi de suite.

## <a name="summary"></a>Résumé

Ces concepts ne sont qu’une introduction à la mécanique quantique, mais ils sont essentiels à connaître pour comprendre l’informatique quantique.

- **Superposition** : capacité des particules quantiques à avoir une combinaison de tous les états possibles.
- **Mesure quantique** : action consistant à observer une particule quantique en superposition et à obtenir comme résultat l’un des états possibles.
- **Intrication** : capacité des particules quantiques à corréler leurs résultats de mesure entre elles.
- **Qubit** : unité de base de l’information en informatique quantique. Un qubit représente une particule quantique en superposition de tous les états possibles.
- **Interférence** : comportement intrinsèque d’un qubit dû à la superposition visant à influencer la probabilité de sa réduction dans un sens ou l’autre.

## <a name="next-steps"></a>Étapes suivantes

[Ordinateurs quantiques et simulateurs quantiques](xref:microsoft.quantum.overview.simulators)
