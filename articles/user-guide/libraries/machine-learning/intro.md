---
title: Bibliothèque de Machine Learning quantique
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.intro
no-loc:
- Q#
- $$v
ms.openlocfilehash: 65b0aa6a7f385765933d4d89ce34901f77cf76ec
ms.sourcegitcommit: 75c4edc7c410cc63dc8352e2a5bef44b433ed188
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88863100"
---
# <a name="introduction-to-quantum-machine-learning"></a>Présentation des Machine Learning Quantum

## <a name="framework-and-goals"></a>Infrastructure et objectifs

L’encodage et le traitement des informations Quantum constituent une alternative puissante aux classifieurs Quantum Machine Learning classiques. En particulier, il nous permet d’encoder des données dans des registres quantiques concis par rapport au nombre de fonctionnalités, en employant systématiquement l’enchevêtrement quantique comme ressource de calcul et en employant une mesure de Quantum pour l’inférence de classe.
Le classifieur Quantum axé sur les circuits est une solution Quantum relativement simple qui associe l’encodage des données à un circuit Quantum démêler la rapide suivi d’une mesure pour déduire les étiquettes de classe des exemples de données.
L’objectif est de garantir la caractérisation et le stockage classiques des circuits de sujet, ainsi que la formation hybride Quantum/classique des paramètres de circuit, même pour les espaces de fonctionnalités extrêmement volumineux.

## <a name="classifier-architecture"></a>Architecture du classifieur

La classification est une tâche de Machine Learning supervisée, où l’objectif est de déduire les étiquettes de classe $ \{ Y_1, y_2, \ldots, y_d \} $ de certains échantillons de données. Le « jeu de données d’apprentissage » est une collection d’échantillons $ \mathcal{D} = \{ (x, y)} $ avec des étiquettes préaffectées connues. Ici $x $ est un exemple de données et $y $ est son étiquette connue appelée « étiquette de formation ».
À l’instar des méthodes traditionnelles, la classification Quantum se compose de trois étapes :
- encodage des données
- préparation d’un état de classifieur
- mesure en raison de la nature probabiliste de la mesure, ces trois étapes doivent être répétées plusieurs fois. L’encodage et le calcul de l’état du classifieur sont effectués au moyen de *circuits quantiques*. Alors que le circuit d’encodage est généralement piloté par les données et sans paramètre, le circuit de classifieur contient un ensemble suffisant de paramètres en cours d’apprentissage. 

Dans la solution proposée, le circuit de classifieur est composé de rotations à qubit unique et de rotations contrôlées à deux qubit. Les paramètres en apprentissage ici sont les angles de rotation. Les portes de rotation et de rotation contrôlée sont connues pour être *universelles* pour le calcul Quantum, ce qui signifie que toute matrice de poids unitaire peut être décomposée en un circuit suffisamment long constitué de ces portes.

Dans la version proposée, un seul circuit suivi d’une seule estimation de fréquence est pris en charge.
Par conséquent, la solution est une analogie quantique d’une machine à vecteurs de support avec un noyau polynomial à faible degré.

![Perceptron multicouches et classificateur centré sur les circuits](~/media/DLvsQCC.png)

Une conception de classifieur Quantum simple peut être comparée à une solution SVM (support vector machine) classique. L’inférence pour un exemple de données $x $ dans le cas de SVM est effectuée à l’aide d’une forme de noyau optimale $ \sum \ alpha_j k (x_j, x) $ où $k $ est une fonction de noyau spécifique.

En revanche, un classifieur quantum utilise le $p de prédiction (o x, U (\Theta)) = 〈 U (\Theta) x | M | U (\Theta) x 〉 $, qui est similaire dans l’esprit, mais techniquement très différent. Ainsi, lorsqu’un encodage d’amplitude simple est utilisé, $p (o x, U (\Theta)) $ est une forme quadratique dans les amplitudes de $x $, mais les coefficients de ce formulaire ne sont plus appris de manière indépendante. ils sont à la place regroupés à partir des éléments de matrice du circuit $U (\Theta) $, qui a généralement beaucoup moins de paramètres d’apprentissage $ \Theta $ que la dimension du vecteur $x $. Le degré polynomial de $p (y x │ x, U (\Theta)) $ dans les fonctionnalités d’origine peut être augmenté jusqu’à $2 ^ l $ en utilisant un encodage de produit Quantum sur $l $ copies de $x $.

Notre architecture explore des circuits relativement superficiels, qui doivent donc être *rapidement emmêlants* afin de capturer toutes les corrélations entre les fonctionnalités de données de toutes les plages. La figure ci-dessous montre un exemple du composant de circuit le plus rapide et le plus utile. Même si un circuit avec cette géométrie se compose uniquement de $3 n + 1 $ portes, la matrice de poids unitaire qu’il calcule assure une communication croisée importante entre les fonctionnalités de $2 ^ n $.

![Circuit quantique de 5 qubits (avec deux couches cycliques) rapidement emmêlant le circuit Quantum.](~/media/5-qubit-qccc.png)

Le circuit dans l’exemple ci-dessus est constitué de 6 G_1 portes qubit, \ldots, G_5 ; G_ {16} ) $ et 10 2-qubits Gates $ (G_6, \ldots, g_ {15} ) $. En supposant que chacune des portes est définie avec un paramètre en cours d’apprentissage, nous avons 16 paramètres d’apprentissage, tandis que la dimension de l’espace de 5 qubit Hilbert est de 32. Une telle géométrie de circuit peut être facilement généralisée à tout $n Registre $-qubit, lorsque $n $ est impair, produisant des circuits avec $3 n + 1 $ paramètres pour l’espace de fonctionnalité de $2 ^ n $.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Apprentissage du classifieur en tant que tâche d’apprentissage supervisé

La formation d’un modèle de classifieur implique la recherche de valeurs optimales de ses paramètres opérationnels, de sorte qu’ils optimisent la probabilité moyenne d’inférence des étiquettes d’apprentissage appropriées dans les exemples d’apprentissage.
Ici, nous nous soucions de la classification à deux niveaux uniquement, c’est-à-dire le cas de $d = $2 et seulement deux classes avec les étiquettes $y _ 1, y_2 $.

> [!NOTE]
> La généralisation de la généralisation de nos méthodes à un nombre arbitraire de classes consiste à remplacer qubits par qudits, c.-à-d. les unités quantiques avec des États de base $d $ et la mesure bidirectionnelle avec $d mesure en $.

### <a name="likelihood-as-the-training-goal"></a>Probabilité de l’objectif de formation

Dans le cas d’un $U circuit Quantum \Theta () $, où $ \Theta $ est un vecteur de paramètres et qui dénote la mesure finale par $M $, la probabilité moyenne de l’inférence de l’étiquette correcte est $ $ \begin{align} \mathcal{L} (\Theta) = \frac {1} {| \mathcal{D} |} \left (\ sum_ {(x, Y_1) \In\mathcal{D}} P (M = Y_1 | U (\Theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\Theta) x) \right) \end{align} $ $ où $P (M = y | z) $ est la probabilité de mesurer $y $ dans l’État Quantum $z $.
Ici, il suffit de comprendre que la fonction de probabilité $ \mathcal{L} (\Theta) $ est lisse dans $ \Theta $ et que son dérivé dans un $ \ theta_j $ peut être calculé en faisant essentiellement le même protocole Quantum que celui utilisé pour calculer la fonction de probabilité proprement dite. Cela permet d’optimiser la profondeur du gradient $ \mathcal{L} (\Theta) $.

### <a name="classifier-bias-and-training-score"></a>Décalage du classifieur et score de formation

Compte tenu de certaines valeurs intermédiaires (ou finales) des paramètres de $ \Theta $, nous devons identifier une seule valeur réelle $b $ savent comme *biais de classifieur* pour effectuer l’inférence. La règle d’inférence d’étiquette fonctionne comme suit : 
- Une étiquette $y _2 $ est assignée à un exemple $x $ si et seulement si $P (M = y_2 | U (\Theta) x) + b > $0,5 (RULE1) (dans le cas contraire, une étiquette $y 1 _ 1 $) est affectée

Clairement $b $ doit être dans l’intervalle $ (-0.5, + 0,5) $ pour être significatif.

Un cas d’apprentissage $ (x, y) \Dans \mathcal{D} $ est considéré comme une *classification* incorrecte en raison de l’écart $b $ si l’étiquette déduite pour $x $ comme par Rule1 est en fait différente de $y $. Le nombre global de classifications incorrectes est le *score d’apprentissage* du classifieur en fonction de l’écart $b $. L’écart *optimal* du classifieur $b $ minimise le score de formation. Il est facile de le voir, étant donné les estimations de probabilité précalculées $ \{ P (M = y_2 | U (\Theta) x) | (x, *) \in\mathcal{D} \} $, l’écart optimal du classifieur peut être trouvé par la recherche binaire dans Interval $ (-0.5, + 0.5) $ en effectuant au maximum $ \ Log_2 (| \mathcal{D} |) $ étapes.

### <a name="reference"></a>Référence

Ces informations doivent être suffisantes pour commencer à utiliser le code. Toutefois, si vous souhaitez en savoir plus sur ce modèle, veuillez lire la proposition d’origine : [ *« classificateurs quantiques centrés sur le circuit », Maria Schuld, Alex Bocharov, Krysta Svore et Nathan Wiebe*](https://arxiv.org/abs/1804.00633)

En plus de l’exemple de code que vous verrez dans les étapes suivantes, vous pouvez également commencer à explorer la classification quantique dans [ce didacticiel](https://github.com/microsoft/QuantumKatas/tree/master/tutorials/QuantumClassification) . 
