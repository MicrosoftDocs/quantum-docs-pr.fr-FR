---
title: Modèles Quantum pour systèmes électroniques | Microsoft Docs
description: Modèles Quantum pour les systèmes informatisés documents conceptuels
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantummodels
ms.openlocfilehash: 45d134333c8a3c8937d206cb0a4a9cc6101a85df
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/26/2019
ms.locfileid: "73184149"
---
# <a name="quantum-models-for-electronic-systems"></a>Modèles Quantum pour systèmes électroniques

Pour simuler des systèmes électroniques, nous devons commencer par spécifier le lieu de la version Hamilton, qui se trouve dans la procédure de quantification canonique décrite ci-dessus.
Plus précisément, pour $N _e $ Electron avec un pointa $p _i $ (en trois dimensions) et en masse $m les vecteurs de _e $ et de position $x _i $ avec les noyaux avec des frais $Z le _K e $ aux positions $y _K $, l’opérateur de Hamilton lit \begin{Equation} \hat{H} = \sum\_{i = 1} ^ {N @no_ _t_1_ e} \frac{\hat{p}\_i ^ 2} {2M\_e} + \frac{1}{2}\sum\_{i\ne j} \frac{e ^ 2} {| \hat{x}\_i-\hat{x}\_j |}-\sum\_{i , k} \frac{Z\_ke ^ 2} {| \hat{x}\_i-{y}\_k |} + \frac{1}{2} \sum_{k\ne k'} \frac{Z\_kZ\_{k'} e ^ 2} {| y\_k-y\_k' |}. \label{EQ : Ham} \end{Equation} les opérateurs de minuteur $ \hat{p}\_i ^ 2 $ peuvent être affichés dans l’espace réel en tant qu’opérateurs laplacien, c’est-à-dire $ \hat{p}\_i ^ 2 =-\partial\_{x\_i} ^ 2-\partial\_{y\_i} ^ 2-\partial\_{z\_i} ^ 2 $.
Ici, nous avons simplifié l’hypothèse que les noyaux étaient au repos pour la molécule.
C’est ce que l’on appelle la approximation Oppenheimer et elle tend à être valide pour le spectre d’énergie de faible énergie de $ \hat{H} $, car la masse d’électrons est d’environ 1/1836 $ la masse d’une protons.
Cet opérateur de ce sein est facile à trouver en écrivant l’énergie pour un système de $N\_e $ Electron et en appliquant le processus de quantification canonique décrit dans [Quantum Dynamics](xref:microsoft.quantum.chemistry.concepts.quantumdynamics).

Pour construire la représentation de matrice unitaire pour $e ^ {-i\hat {H} t} $, nous devons représenter l’opérateur $ \hat{H} $ en tant que matrice.
Pour cela, nous devons choisir un système de coordonnées ou une base pour représenter le problème dans.
Par exemple, si $ \psi_j $ est un ensemble de fonctions de base orthogonales pour le $N _e $ Electron, nous pouvons définir la matrice

\begin{Equation} H\_{i, j} = \int\_{-\infty} ^ \infty\int\_{-\infty} ^ \infty \Psi ^ {\*}\_i (x\_1) \hat{H} \Psi\_j (x\_2) \dd ^ 3x\_1 \dd ^ 3\_2. \ label {EQ : discreteHam} \end{Equation}

En principe, l’opérateur $ \hat{H} $ est illimité et n’agit pas sur un espace dimensionnel fini, la matrice avec des éléments $H\_\{i, j\}$ ci-dessus.
Cela signifie que les erreurs sont provoquées par le choix d’un trop petit ensemble de base ; Toutefois, le choix d’une base importante peut compliquer la simulation de la dynamique chimique.
Pour cette raison, le choix d’une base qui peut représenter le problème de façon concise est essentiel pour résoudre le problème de structure électronique.

Il existe de nombreuses bases qui peuvent être utilisées et le choix d’une bonne base pour s’adapter au problème est la grande partie de l’art de la chimie de Quantum.
Les jeux de base les plus simples sont peut-être des Slaters (arrêt) qui sont des solutions (orthogonales) à l’équation Schrödinger (c’est-à-dire Eigenfunctions de $ \hat{H} $) pour les atomes de type hydrogène.
D’autres jeux de base, tels que les vagues planes ou les orbites en temps réel, peuvent être utilisés et, pour plus de détails, nous recherchons le lecteur curieux sur la théorie de la [structure électronique moléculaire](https://onlinelibrary.wiley.com/doi/book/10.1002/9781119019572) du texte standard par Helgaker.

Alors que les États utilisés dans le modèle ci-dessus peuvent paraître arbitraires, le mécanisme Quantum place des restrictions sur les États qui peuvent être trouvés par nature.
En particulier, tous les États de Quantum électroniques valides doivent être anti-symétriques sous l’échange d’étiquettes d’électrons.
Autrement dit, si $ \Psi (X_1, X_2) $ étaient la fonction Wave pour l’état de Quantum conjoint de deux électrons, nous devons avoir ce $ $ \Psi (X_1, X_2) =-\Psi (X_2, X_1).
$ $ Le principe d’exclusion Pauli qui interdit à deux électrons de se trouver dans le même État Quantum est, de manière fascinante, une conséquence directe de cette loi qui peut être Intuit du fait que si nous échangerons deux électrons situés à la même position $ \Psi (X_1, X_1) \mapsto \Psi ( X_1, X_1) \ne-\Psi (X_1, X_1) $ sauf $ \Psi (X_1, X_1) = 0 $.
Par conséquent, les États initiaux doivent être choisis pour respecter cette propriété anti-symétrie et, à leur tour, n’ont jamais deux électrons dans le même État en même temps.
Cela est essentiel pour la structure électronique, car elle interdit que plusieurs électrons ne soient dans le même État et permet à son tour aux ordinateurs quantiques d’utiliser un bit Quantum unique pour stocker le nombre d’électrons dans un État Quantum donné.

Bien qu’il soit possible de simuler un mécanisme quantique sur un ordinateur quantique en discrétisation ces États, la plupart des travaux dans le domaine eschewed cette approche, car elle nécessite de nombreux qubits pour stocker les États et nécessite une procédure de préparation d’État complexe pour préparer un état initial anti-symétrique.
Heureusement, ces problèmes peuvent être Sidestepped en consultant le problème de simulation d’une perspective différente.