---
title: Plusieurs qubits
description: Découvrez comment effectuer des opérations sur au moins deux qubits.
author: QuantumWriter
uid: microsoft.quantum.concepts.multiple-qubits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- $
- $
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 1ac235bef473efa82b096cae4159e2c724ba7c0e
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269488"
---
# <a name="multiple-qubits"></a>Plusieurs qubits

Alors que les portes à qubit unique possèdent des fonctionnalités de type « compteur », telles que la possibilité d’être dans plus d’un État à un moment donné, si tout ce que nous avions sur un ordinateur quantique étaient des portes à qubit unique, nous aurions un appareil avec une puissance de calcul qui serait de la même façon, même si une calculatrice ne permet pas de créer un superordinateur classique.
La véritable puissance de quantum computing devient évidente au fur et à mesure que nous augmentons le nombre de qubits.
Cette puissance se produit, en partie, car la dimension de l’espace vectoriel des vecteurs d’état de Quantum augmente de façon exponentielle avec le nombre de qubits.
Cela signifie que si un seul qubit peut être modélisé de manière triviale, la simulation d’un calcul Quantum 50-qubit entraînerait sans doute les limites des superordinateurs existants.
L’amélioration de la taille du calcul par un seul qubit supplémentaire *double* la mémoire requise pour stocker l’État et *double* à peu près le temps de calcul.
Cette multiplication rapide de la puissance de calcul est la raison pour laquelle un ordinateur quantique avec un nombre relativement faible de qubits peut largement dépasser les superordinateurs les plus puissants actuels, demain et au-delà de certaines tâches de calcul.

Pourquoi est-ce que nous avons une croissance exponentielle pour les vecteurs d’État Quantum ?  L’objectif de cette section est de passer en revue les règles utilisées pour créer des États qubit à partir d’États qubit, ainsi que de discuter des opérations de la porte que nous devons inclure dans notre jeu de portes pour former un ordinateur Quantum qubit universel.
Ces outils sont absolument nécessaires pour comprendre les jeux de portes couramment utilisés dans le code Q #, ainsi que pour obtenir des informations sur la raison pour laquelle les effets quantiques tels que l’enchevêtrement ou l’interférence rendent quantum computing plus puissant que l’informatique classique.

## <a name="representing-two-qubits"></a>Représentant deux qubits
La principale différence entre les États à un et deux qubit est que les États de deux qubit sont à quatre dimensions plutôt qu’en deux dimensions.
Cela est dû au fait que la base de calcul pour les États de deux qubit est formée par les produits tenseur de l’un des États qubit.  Par exemple, nous avons \begin{align}
00 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } &= \begin{ bmatrix } 1 0 0 0 \\ \\ \\\\ \\\\ \end{ bmatrix } , \qquad 01 \equiv \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 1 \\\\ 0 \\\\ 0 \end{ bmatrix } , \\ \\ 10 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{\otimes \begin{ bmatrix } bmatrix } 1 \\ \\ 0 \end{ bmatrix } &= \begin{ bmatrix } 0 \\ \\ 0 \\\\ 1 \\\\ 0 \end{ bmatrix } , \qquad 11 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } = \begin{ bmatrix } 0 \\ \\ 0 \\\\ 0 \\\\ 1 \end{ bmatrix } .
\end{align}

Il est facile de voir que plus généralement, l’État Quantum de $n $ qubits est représenté par un vecteur d’unité de dimension $2 ^ n $ à l’aide de cette construction.  Le vecteur

$ $ \begin{ bmatrix } \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11 } \end{bmatrix}
$$

représente un État Quantum sur deux qubits si $ | \ alpha_ {00 } | ^ 2 + | \ alpha_ {01 } | ^ 2 + | \ alpha_ {10 } | ^ 2 + | \ alpha_ {11 } | ^ 2 = 1 $ . Tout comme avec un qubits unique, le vecteur d’État Quantum de plusieurs qubits contient toutes les informations nécessaires pour décrire le comportement du système.

Si vous disposez de deux qubits distincts, l’un dans l’État $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $ et le second qubit dans l’État $ \begin{ bmatrix } \gamma \delta \\ \\ \end{ bmatrix } $, l’état deux-qubit correspondant est

$ $ \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } \otimes bmatrix } \\ \\ \begin{\gamma \delta \end{bmatrix} 
= \begin{ bmatrix } \alpha \begin{ bmatrix } \gamma \\ \\ \delta \end{\beta bmatrix } \\ \\ \begin{ bmatrix } \gamma \\ \\ \delta bmatrix } \end{\end{bmatrix}
= \begin{ bmatrix } \alpha \gamma \\ \\ \alpha \delta \\ \\ \beta \gamma \\ \\ \beta \delta \end{ bmatrix } , $ $

où l’opération $ \otimes $ est appelée le produit tenseur (ou le produit Kronecker) des vecteurs. Notez que, bien que nous puissions toujours prendre le produit tenseur de deux États à qubit pour former un État à deux qubit, les États quantiques à deux qubit ne peuvent pas être écrits en tant que produit tenseur de deux États à qubit unique.
Par exemple, il n’existe aucun État $ \Psi = \begin{ bmatrix } \alpha \\ \\ \beta \end{ bmatrix } $ et $ \Phi \begin{\gamma \delta \end{ = bmatrix } \\ \\ bmatrix } $, de sorte que leur produit tenseur est l’État 

$ $ \Psi \otimes \Phi = \begin{ bmatrix } 1/\ sqrt {2 } \\ \\ 0 \\ \\ 0 \\ \\ 1/\ racine {2 } \end{ bmatrix } . $ $ 

Un tel État à deux qubit, qui ne peut pas être écrit en tant que produit tenseur d’États de qubit unique, est appelé « état enchevêtré ». les deux qubits sont considérés comme étant [*enchevêtrés*](https://en.wikipedia.org/wiki/Quantum_entanglement).  En fait, comme l’État Quantum ne peut pas être considéré comme un produit tenseur d’États qubit uniques, les informations que l’état contient ne sont pas limitées à l’un ou l’autre des qubits individuellement.  Au lieu de cela, les informations sont stockées non localement dans les corrélations entre les deux États.  Cette non-localité d’informations est l’une des principales fonctionnalités distinctives de quantum computing par rapport à l’informatique classique et est essentielle pour un certain nombre de protocoles quantiques, y compris la [téléportage quantique](https://github.com/microsoft/Quantum/tree/master/samples/getting-started/teleportation) et la [Correction d’Erreurs quantique](xref:microsoft.quantum.libraries.error-correction).

## <a name="measuring-two-qubit-states"></a>Mesure de deux États qubit ##
La mesure de deux États qubit est très similaire aux mesures à qubit unique. Mesure de l’État

$ $ \begin{bmatrix}
        \ alpha_ {00 } \\ \\ \ alpha_ {01 } \\ \\ \ alpha_ {10 } \\ \\ \ alpha_ {11}
    effetbmatrix}
$$

produit $0 $ avec la probabilité $ | \ alpha_ {00 } | ^ 2 $ , $1 $ avec la probabilité $ | \ alpha_ {01 } | ^ 2, $10 avec la probabilité $ | $ $ \ alpha_ {10 } | ^ 2 $ et $11 $ avec la probabilité $ | \ alpha_ {11 } | ^ 2 $ . Les variables $ \ alpha_ {00 } , \ alpha_ {01 } , \ alpha_ {10 } , $ et $ \ alpha_ {11 } $ ont été délibérément nommées pour rendre cette connexion claire. Après la mesure, si le résultat est $0, $ l’État Quantum du système à deux qubit est réduit et est maintenant

$ $0 \equiv \begin{bmatrix}
        1 0 0 0 \\ \\ \\ \\ \\ \\ \end{ bmatrix } .
$$

Il est également possible de mesurer une seule qubit d’un État Quantum à deux qubit. Dans les cas où vous mesurez uniquement l’un des qubits, l’impact de la mesure est légèrement différent, car l’état entier n’est pas réduit à un état de base de calcul, au lieu d’être réduit à un seul sous-système.  En d’autres termes, dans de tels cas, la mesure d’un seul qubit réduit uniquement l’un des sous-systèmes, mais pas tous.  

Pour voir cela, envisagez de mesurer le premier qubit de l’état suivant, qui est formé en appliquant la transformation hadarmard $H $ sur deux qubits initialement définie à l’État « 0 » : $ $ H ^ {\otimes 2 } \left (\begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \right) = \frac{1 } {2 } \begin{ bmatrix } 1 & 1 & 1 & 1 \\ \\ 1 &-1 & 1 &-1 \\ \\ 1 & 1 &-1 &-1 1 &-1 & \\ \\ -1 & 1 \end{ bmatrix } \begin{ bmatrix } 1 0 0 0 \\\\ \\\\ \\\\ \end{bmatrix} = \frac{1 } {2 } \begin{ bmatrix } 1 1 1 1 \\\\ \mapsto \begin{cases \\\\ \\\\ \end{bmatrix} } \text{Outcome} = 0 & \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 1 \\\\ 1 \\\\ 0 \\\\ 0 \end{ bmatrix } \\ \\ \text{Outcome} = 1 & \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \end{\end{cases \\\\ bmatrix } \\ \\ } .
$ $ Les deux résultats ont une probabilité de 50%.  Le résultat d’une probabilité de 50% pour les deux peut être Intuit à partir du fait que le vecteur d’État Quantum initial est invariant sous échangeant $0 $ avec $1 $ sur le premier qubit.

La règle mathématique pour mesurer la première ou la deuxième qubit est simple.  Si nous laissons $e _k $ être le } vecteur de base de calcul $k ^ {\rm Th $ et $S $ être l’ensemble de tous les $e _K de $ telle sorte que le qubit en question prenne la valeur $1 $ pour cette valeur de $k $ .  Par exemple, si nous nous intéressons à mesurer le premier qubit, $S $ serait composé de $e \equiv 1 $ et 10 $e _3 \equiv 11 $ .  De même, si nous sommes intéressés par le deuxième qubit $S $ se comporterait $e _2 \equiv 01 $ et $e _3 \equiv 11 $ .  La probabilité de mesurer le qubit choisi sur $1 est alors le $ vecteur d’État $ \Psi$

$ $ P (\text{Outcome } = 1) = \ sum_ {e_k \text { dans le jeu} S } \psi ^ \dagger e_k e_k ^ \dagger \Psi.
$$

> [!NOTE]
> Dans ce document, nous utilisons le format avec primauté des octets de poids faible (Little-endian) pour étiqueter la base de calcul. Au format Little endian, les bits les moins significatifs sont placés en premier. Par exemple, le nombre quatre au format Little endian est représenté par la chaîne de bits 001.

Étant donné que chaque mesure qubit peut générer uniquement $0 $ ou $1 $ , la probabilité de mesurer $0 $ est simplement $1-P (\text{Outcome } = 1) $.  C’est pourquoi nous fournissons explicitement une formule pour la probabilité de mesurer $1 $ .

L’action qu’une telle mesure a sur l’État peut être exprimée de façon mathématique comme

$ $ \Psi \mapsto \frac { \ sum_ {e_k \text { dans le jeu} S } e_k e_k ^ \Dagger \Psi } {\sqrt{P (\text{Outcome } = 1)}}.
$$

Le lecteur prudent peut se soucier de ce qui se passe lorsque la probabilité de la mesure est égale à zéro.  Alors que l’état résultant est techniquement non défini dans ce cas, nous n’avons pas à vous soucier de ces éventualités, car la probabilité est nulle !


Si nous prenons $ le vecteur d’État uniforme indiqué ci-dessus et que nous souhaitons mesurer le premier qubit, 

$ $ P (\text{Measurement of First qubit } = 1) = (\Psi ^ \dagger e_1) (e_1 ^ \dagger \Psi) + (\Psi ^ \dagger e_3) (e_3 ^ \dagger \Psi) = | e_1 ^ \dagger \Psi | ^ 2 + | e_3 ^ \dagger \Psi | ^ 2.
$$

Notez qu’il s’agit simplement de la somme des deux probabilités attendues pour mesurer les résultats $10 $ et $11 $ tous les qubits à mesurer.
Pour notre exemple, cette valeur est

$ $ \frac{1 } {4 } \left | \begin{ bmatrix } 0&0&1&0 \end{bmatrix} \begin{ bmatrix } 1 \\\\ 1 \\\\ 1 \\\\ 1 \end{bmatrix} \right | ^ 2 + \frac{1 } {4 } \left | \begin{ bmatrix } 0&0&0&1 \end{bmatrix} \begin{ bmatrix } 1 \\\\ 1 \\\\ 1 \\\\ 1 \end{bmatrix} \right | ^ 2 = \frac{1 } {2 } .
$$

ce qui correspond parfaitement à ce que notre intuition nous dit que la probabilité doit être.  De même, l’État peut être écrit comme

$ $ \frac { \frac{e_1 } {2 } + \frac{e_3 } {2 } } {\sqrt { \frac{1 } {2 } }} = \frac{1 } {\sqrt{2 } } \begin{ bmatrix } 0 \\\\ 0 \\\\ 1 \\\\ 1\end{bmatrix}
$$

là encore, conformément à notre intuition.

## <a name="two-qubit-operations"></a>Opérations à deux qubit
Comme dans le cas d’une qubit, toute transformation unitaire est une opération valide sur qubits. En général, une transformation unitaire sur $n $ qubits est une matrice $U $ de taille $2 ^ n \times 2 ^ n $ (afin qu’elle agisse sur des vecteurs de taille de $2 ^ n $ ), de sorte que $U ^ {-1 } = U ^ \dagger $ .
Par exemple, la porte CNOTIN (contrôlée-NOT) est une porte à deux qubit couramment utilisée et est représentée par la matrice d’unités suivante :

$ $ \operatorname{CNOT } = \begin{ bmatrix } 1 \ 0 \ 0 \ 0 \\ \\ 0 \ 1 \ 0 \ 0 0 \ 0 \ 0 \ \\ \\ 1 \\ \\ 0 \ 0 \ 1 \ 0 \end{bmatrix}
$$

Nous pouvons également former des portes à deux qubit en appliquant des portes à qubit unique sur les deux qubits. Par exemple, si nous appliquons les portes 

$ $ \begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
$$

et

$ $ \begin{bmatrix}
e \ f \\\\ v \ h \end{bmatrix}
$$

pour le premier et le deuxième qubits, respectivement, cela équivaut à appliquer l’unité qubit fournie par le produit tenseur : $ $ \begin{bmatrix}
a \ b \\\\ c \ d \end{bmatrix}
\otimes \begin{bmatrix}
e \ f \\\\ g \ h \end{ bmatrix } = \begin{bmatrix}
    AE \ AF \ est \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ ce \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \End{ bmatrix } . $ $ nous pouvons donc former deux portes qubit en acceptant le produit tenseur des portes à qubit unique connues. Voici quelques exemples de portes à deux qubit : $H \otimes H $ , $X \otimes \boldone $ et $X \otimes Z $ .

Notez que si deux portes à qubit unique définissent une porte à deux qubit en prenant leur produit tenseur, la réciproque n’est pas vraie. Les portes à deux qubit ne peuvent pas être écrites en tant que produit tenseur de portes à qubit unique.  Une porte de ce type est appelée porte *emmêlante* . La porte CNOTIN en est un exemple.

L’intuition derrière une porte contrôlée ne peut pas être généralisée à des portes arbitraires.  Une porte contrôlée en général est une porte qui agit comme identité (c’est-à-dire qu’elle n’a aucune action), sauf si un qubit spécifique est $1 $ .  Nous indiquons une unité contrôlée, contrôlée dans ce cas sur le qubit étiqueté $x $ , avec un $ \Lambda \_ x (U) $.  Par exemple, $ \ Lambda_0 (U) e \_ {1 } \otimes {\Psi } = e \_ {1 } \otimes U { \Psi } $ et $ \Lambda \_ 0 (U) e \_ {0 } \otimes {\psi } = e \_ {0 } \otimes { \Psi } $, où $e \_ 0 $ et $e \_ 1 $ sont les vecteurs de base de calcul pour un qubit unique correspondant aux valeurs $0 $ et $1 $ .  Par exemple, considérez la porte de $Z contrôlée suivante. $ nous pouvons l’exprimer sous la forme $ $ \Lambda \_ 0 (Z) = \begin{ bmatrix } 1&0&0&0 0&1&0&0 \\ \\ 0&0&\\ \\ 1&0 \\ \\ 0&0&0 & -1 \end{ bmatrix } = (\boldone \otimes h) \operatorname{CNOT } (\boldone \otimes h).
$$

La création d’unités contrôlées de manière efficace est un défi majeur.  La façon la plus simple d’implémenter cela consiste à former une base de données de versions contrôlées de portes fondamentales et à remplacer chaque porte fondamentale dans l’opération d’origine par son équivalent contrôlé.  C’est souvent un gaspillage et des informations astucieuses peuvent souvent être utilisées pour remplacer quelques portes avec des versions contrôlées pour obtenir le même impact.  Pour cette raison, nous fournissons dans notre infrastructure la possibilité d’effectuer la méthode naïve de contrôle ou de permettre à l’utilisateur de définir une version contrôlée de l’unité si une version optimisée est connue.

Les portes peuvent également être contrôlées à l’aide d’informations classiques.  Un non-porte contrôlé de manière classique, par exemple, n’est qu’une simple non-porte, mais il est appliqué uniquement si un bit classique est $1 $ par opposition à un bit Quantum.  Dans ce sens, une porte de contrôle classique peut être considérée comme une instruction if dans le code de Quantum dans lequel la porte est appliquée uniquement dans une branche du code.


Comme dans le cas d’une seule qubit, un ensemble de portes à deux qubit est universel si \times une $ matrice unitaire de $4 4 peut être approximative par un produit de portes de ce jeu à une précision arbitraire.
Un exemple de jeu de portes universel est la porte Hadarmard, la porte T et la porte CNOTIN. En acceptant les produits de ces portes, nous pouvons rapprocher n’importe quelle matrice unitaire sur deux qubits.

## <a name="many-qubit-systems"></a>Systèmes à plusieurs qubit
Nous suivons exactement les mêmes modèles que ceux explorés dans le cas de qubit pour créer des États quantiques à plusieurs qubit à partir de systèmes plus petits.  De tels États sont créés en formant des produits tenseur d’États plus petits.  Par exemple, envisagez d’encoder la chaîne de bits $1011001 $ sur un ordinateur Quantum.  Nous pouvons Encoder ceci comme

$ $1011001 \equiv \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{\otimes bmatrix } \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{\otimes \begin{ bmatrix } bmatrix } 0 \\ \\ 1 \end{ bmatrix } .
$$

Les portes Quantum fonctionnent exactement de la même façon.  Par exemple, si vous souhaitez appliquer la porte $X $ au premier qubit, puis effectuer un cnotin entre le deuxième et le troisième qubits, nous pouvons exprimer cette transformation en

\begin{align}
& (X \otimes \operatorname{CNOT}_{12 } \otimes \boldone \otimes \boldone \otimes \boldone \otimes \boldone) \begin{ bmatrix } 0 \\ \\ 1 \end{\otimes \begin{ bmatrix } bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 0 \\ \\ 1 \end{\otimes bmatrix } \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } \otimes \begin{ bmatrix } 1 \\ \\ 0 \end{\otimes bmatrix } \begin{ bmatrix } 0 \\ \\ 1 \end{ bmatrix } \\ \\ & \qquad \qquad \equiv 0011001.
\end{align}

Dans de nombreux systèmes qubit, il est souvent nécessaire d’allouer et de libérer des qubits qui servent de mémoire temporaire pour l’ordinateur Quantum.  Un qubit de ce type est appelé Ancilla.  Par défaut, nous supposons que l’État qubit est initialisé à $e _0 lors de l' $ allocation.  Nous partons du principe qu’il est renvoyé à $e _0 $ avant la désallocation.  Cette hypothèse est importante, car si un qubit Ancilla est associé à un autre registre qubit lorsqu’il est libéré, le processus de désallocation endommage le Ancilla.  Pour cette raison, nous partons toujours du principe que ces qubits sont rétablies à leur état initial avant d’être libérées.

Enfin, bien que de nouvelles portes devaient être ajoutées à notre ensemble de portes pour obtenir un calcul de Quantum universel pour deux ordinateurs Quantum qubit, il n’est pas nécessaire d’introduire de nouvelles portes dans le cas multi-qubit.  Les portes $H $ , $T $ et cnotin forment un ensemble de portes universelles sur de nombreux qubits, car toute transformation d’unité générale peut être divisée en une série de deux rotations qubit.  Nous pouvons ensuite tirer parti de la théorie développée pour le cas de deux-qubit et l’utiliser à nouveau ici quand nous avons plusieurs qubits.

Alors que la notation algébrique linéaire que nous utilisons jusqu’ici peut certainement être utilisée pour décrire les États de plusieurs qubit, elle devient de plus en plus lourde, car nous augmentons la taille des États.  Le vecteur de colonne résultant pour une chaîne de longueur de 7 bits, par exemple, est $128 $ dimensionnel, ce qui le rend en l’exprimant à l’aide de la notation décrite précédemment très lourde.  Pour cette raison, nous présentons une notation commune dans le calcul quantique qui nous permet de décrire de manière concise ces vecteurs de grande dimension.
