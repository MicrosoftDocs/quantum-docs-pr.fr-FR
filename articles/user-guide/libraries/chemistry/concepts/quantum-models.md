---
title: Modèles Quantum pour systèmes électroniques
description: Découvrez comment les systèmes électroniques moléculaires sont simulés à l’aide de la modélisation quantique.
author: bradben
ms.author: v-benbra
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
no-loc:
- Q#
- $$v
ms.openlocfilehash: 4ff3d11bfd4dae5489fc4b7efe4da4ccda00882f
ms.sourcegitcommit: 9b0d1ffc8752334bd6145457a826505cc31fa27a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90833919"
---
# <a name="quantum-models-for-electronic-systems"></a>Modèles Quantum pour systèmes électroniques

Pour simuler des systèmes électroniques, nous devons commencer par spécifier le lieu de la version Hamilton, qui se trouve dans la procédure de quantification canonique décrite ci-dessus.
Plus précisément, pour $N _e $ Electron avec un instant $p _i $ (en trois dimensions) et une $m de masse _e $ et des vecteurs de position $x _i $ avec des noyaux avec des frais $Z _k e $ aux positions $y _K $, l’opérateur de niveau Hamilton lit \begin{Equation} \hat{H} = \sum \_ {i = 1} ^ {N \_ e} \frac{\hat{p} \_ i ^ 2} {2M \_ e} + \frac {1} {2} \sum \_ {i\ne j} \frac{e ^ 2} {| \hat{x} \_ i-\hat{x} \_ j |}-\sum \_ {i, k} \frac{Z \_ ke ^ 2} {| \hat{x} \_ i-{y} \_ k |} + \frac {1} {2} \ sum_ {k\ne k'} \frac{Z \_ kZ \_ {k'} e ^ 2} {| y \_ k-y \_ k' |}. \label{EQ : Ham} \end{Equation} le moment où les opérateurs $ \hat{p} \_ i ^ 2 $ peuvent être affichés dans l’espace réel en tant qu’opérateurs laplacien, c’est-à-dire $ \hat{p} \_ i ^ 2 =-\partial \_ {x \_ i} ^ 2-\partial \_ {y \_ } ^ 2-\partial \_ {z \_ i} ^ 2 $.
Ici, nous avons simplifié l’hypothèse que les noyaux étaient au repos pour la molécule.
C’est ce que l’on appelle la approximation Oppenheimer et elle tend à être valide pour le spectre d’énergie de faible énergie de $ \hat{H} $, car la masse d’électrons est d’environ 1/1836 $ la masse d’une protons.
Cet opérateur de conception peut être facilement trouvé en écrivant l’énergie pour un système de $N \_ e $ Electron et en appliquant le processus de quantification canonique décrit dans [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Pour construire la représentation de matrice unitaire pour $e ^ {-i\hat {H} t} $, nous devons représenter l’opérateur $ \hat{H} $ en tant que matrice.
Pour cela, nous devons choisir un système de coordonnées ou une base pour représenter le problème dans.
Par exemple, si $ \ psi_j $ est un ensemble de fonctions de base orthogonales pour l' $N _e $ Electron, nous pouvons définir la matrice

\begin{Equation} H \_ {i, j} = \int \_ {-\infty} ^ \infty\int \_ {-\infty} ^ \infty \Psi ^ { \* } \_ i (x \_ 1) \hat{H} \Psi \_ j (x \_ 2) \dd ^ 3x \_ 1 \dd ^ 3x \_ 2. \ label {EQ : discreteHam} \end{Equation}

En principe, l’opérateur $ \hat{H} $ est illimité et n’agit pas sur un espace dimensionnel fini, la matrice avec les éléments $H \_ \{ i, j \} $ ci-dessus.
Cela signifie que les erreurs sont provoquées par le choix d’un trop petit ensemble de base ; Toutefois, le choix d’une base importante peut compliquer la simulation de la dynamique chimique.
Pour cette raison, le choix d’une base qui peut représenter le problème de façon concise est essentiel pour résoudre le problème de structure électronique.

Il existe de nombreuses bases qui peuvent être utilisées et le choix d’une bonne base pour s’adapter au problème est la grande partie de l’art de la chimie de Quantum.
Les jeux de base les plus simples sont peut-être des Slaters (arrêt) qui sont des solutions (orthogonales) à l’équation Schrödinger (c’est-à-dire Eigenfunctions de $ \hat{H} $) pour les atomes de type hydrogène.
D’autres jeux de base, tels que les vagues planes ou les orbites en temps réel, peuvent être utilisés et, pour plus de détails, nous recherchons le lecteur curieux sur la théorie de la [structure électronique moléculaire](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) du texte standard par Helgaker.

Alors que les États utilisés dans le modèle ci-dessus peuvent paraître arbitraires, le mécanisme Quantum place des restrictions sur les États qui peuvent être trouvés par nature.
En particulier, tous les États de Quantum électroniques valides doivent être anti-symétriques sous l’échange d’étiquettes d’électrons.
Autrement dit, si $ \Psi (x_1, x_2) $ étaient la fonction Wave pour l’État Quantum conjoint de deux électrons, nous devons avoir le $ $ \Psi (x_1, x_2) =-\Psi (x_2, x_1).
$ $ Le principe d’exclusion Pauli qui interdit à deux électrons de se trouver dans le même État Quantum est, de manière fascinante, une conséquence directe de cette loi qui peut être Intuit du fait que si nous échangerons deux électrons situés à la même position $ \Psi (x_1, x_1) \mapsto \Psi (x_1, x_1) \ne-\Psi (x_1, x_1) $ sauf $ \Psi , x_1) = 0 $.
Par conséquent, les États initiaux doivent être choisis pour respecter cette propriété anti-symétrie et, à leur tour, n’ont jamais deux électrons dans le même État en même temps.
Cela est essentiel pour la structure électronique, car elle interdit que plusieurs électrons ne soient dans le même État et permet à son tour aux ordinateurs quantiques d’utiliser un bit Quantum unique pour stocker le nombre d’électrons dans un État Quantum donné.

Bien qu’il soit possible de simuler un mécanisme quantique sur un ordinateur quantique en initialisant ces États, la plupart des travaux dans le domaine eschewed cette approche, car elle nécessite de nombreux qubits pour stocker les États et nécessite une procédure de préparation d’État complexe pour préparer un état initial anti-symétrique.
Heureusement, ces problèmes peuvent être Sidestepped en consultant le problème de simulation d’une perspective différente.
