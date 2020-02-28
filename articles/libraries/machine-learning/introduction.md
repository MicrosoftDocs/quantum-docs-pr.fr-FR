---
title: Bibliothèque de Machine Learning Quantum
author: alexeib2
ms.author: alexei.bocharov@microsoft.com
ms.date: 11/22/2019
ms.topic: article
uid: microsoft.quantum.libraries.machine-learning.introduction
ms.openlocfilehash: 4c42612fee3a58e15368677bb2c77a70c5680f45
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77909787"
---
# <a name="introduction-to-quantum-machine-learning"></a>Présentation des Machine Learning Quantum

## <a name="framework-and-goals"></a>Infrastructure et objectifs

L’encodage et le traitement des informations Quantum constituent une alternative puissante aux classifieurs Quantum Machine Learning classiques, en particulier l’encodage des données dans des registres quantiques concis par rapport au nombre de fonctionnalités, en employant systématiquement Quantum en tant que ressource de calcul et utiliser la mesure quantique pour l’inférence de classe.
Le classifieur Quantum axé sur les circuits est une solution Quantum relativement simple qui associe l’encodage des données à un circuit Quantum démêler la rapide suivi d’une mesure pour déduire les étiquettes de classe des exemples de données.
L’objectif est de garantir la caractérisation et le stockage classiques des circuits de sujet, ainsi que la formation hybride Quantum/classique des paramètres de circuit, même pour les espaces de fonctionnalités extrêmement volumineux.

## <a name="classifier-architecture"></a>Architecture du classifieur

La classification est une tâche de Machine Learning supervisée, où l’objectif est de déduire les étiquettes de classe $\{y_1, y_2, \ldots, y_d\}$ de certains échantillons de données. Le « jeu de données d’apprentissage » est une collection d’exemples $ \mathcal{D} =\{(x, y)} $ avec des étiquettes préaffectées connues. Ici $x $ est un exemple de données et $y $ est son étiquette connue appelée « étiquette de formation ».
À l’instar des méthodes traditionnelles, la classification Quantum se compose de trois étapes :
- encodage des données
- préparation d’un état de classifieur
- mesure en raison de la nature probabiliste de la mesure, ces trois étapes doivent être répétées plusieurs fois. La mesure peut être considérée comme un équivalent quantique de l’activation non linéaire.
L’encodage et le calcul de l’état du classifieur sont effectués au moyen de *circuits quantiques*. Alors que le circuit d’encodage est généralement piloté par les données et sans paramètre, le circuit de classifieur contient un ensemble suffisant de paramètres en cours d’apprentissage. 

Dans la solution proposée, le circuit de classifieur est composé de rotations à qubit unique et de rotations contrôlées à deux qubit. Les paramètres en apprentissage ici sont les angles de rotation. Les portes de rotation et de rotation contrôlée sont connues pour être *universelles* pour le calcul Quantum, ce qui signifie que toute matrice de poids unitaire peut être décomposée en un circuit suffisamment long constitué de ces portes.

![Perceptron multicouches et classificateur centré sur les circuits](~/media/DLvsQCC.png)

Nous pouvons comparer ce modèle à un perceptron multicouche pour obtenir une meilleure compréhension de la structure de base. Dans le Perceptron, le prédiction $p (y | x, \Theta) $ est paramétrée par l’ensemble des poids $ \Theta $ qui déterminent les fonctions linéaires qui connectent les fonctions d’activation non linéaires (neurones). Ces paramètres peuvent être formés pour créer le modèle. Au niveau de la couche de sortie, nous pouvons obtenir la probabilité d’un échantillon appartenant à une classe en utilisant des fonctions d’activation non linéaires comme SoftMax. Dans le classifieur de circuit centré sur les circuits, le prédiction est paramétrée par les angles de rotation des rotations à qubit et à deux qubit contrôlées du circuit du modèle. De la même façon, ces paramètres peuvent être formés par une version hybride Quantum/classique de l’algorithme de descente de dégradé. Pour calculer la sortie, au lieu d’utiliser des fonctions d’activation non linéaires, la probabilité de la classe est obtenue en lisant des mesures répétées sur un qubit spécifique après les rotations contrôlées. Pour encoder les données classiques dans un État Quantum, nous utilisons un circuit de codage contrôlable pour la préparation de l’État.

Notre architecture explore des circuits relativement superficiels, qui doivent donc être *rapidement emmêlants* afin de capturer toutes les corrélations entre les fonctionnalités de données de toutes les plages. La figure ci-dessous montre un exemple du composant de circuit le plus rapide et le plus utile. Même si un circuit avec cette géométrie se compose uniquement de $3 n + 1 $ portes, la matrice de poids unitaire qu’il calcule assure une communication croisée importante entre les fonctionnalités de $2 ^ n $.

![Circuit quantique de 5 qubits (avec deux couches cycliques) rapidement emmêlant le circuit Quantum.](~/media/5-qubit-qccc.png)

Le circuit dans l’exemple ci-dessus est constitué de 6 G_1 portes qubit, \ldots, G_5 ; G_{16}) $ et 10 2-qubits Gates $ (G_6, \ldots, G_{15}) $. En supposant que chacune des portes est définie avec un paramètre en cours d’apprentissage, nous avons 16 paramètres d’apprentissage, tandis que la dimension de l’espace de 5 qubit Hilbert est de 32. Une telle géométrie de circuit peut être facilement généralisée à tout $n Registre $-qubit, lorsque $n $ est impair, produisant des circuits avec $3 n + 1 $ paramètres pour l’espace de fonctionnalité de $2 ^ n $.

## <a name="classifier-training-as-a-supervised-learning-task"></a>Apprentissage du classifieur en tant que tâche d’apprentissage supervisé

La formation d’un modèle de classifieur implique la recherche de valeurs optimales de ses paramètres opérationnels, de sorte qu’ils optimisent la probabilité moyenne d’inférence des étiquettes d’apprentissage appropriées dans les exemples d’apprentissage.
Ici, nous nous soucions de la classification à deux niveaux uniquement, c’est-à-dire le cas de $d = $2 et seulement deux classes avec les étiquettes $y _ 1, y_2 $.

> [!NOTE]
> La généralisation de la généralisation de nos méthodes à un nombre arbitraire de classes consiste à remplacer qubits par qudits, c.-à-d. les unités quantiques avec des États de base $d $ et la mesure bidirectionnelle avec $d mesure en $.

### <a name="likelihood-as-the-training-goal"></a>Probabilité de l’objectif de formation

Dans le cas d’un circuit Quantum $U (\Theta) $, où $ \Theta $ est un vecteur de paramètres et indiquant la mesure finale par $M $, la probabilité moyenne de l’inférence de l’étiquette correcte est $ $ \begin{align} \mathcal{L} (\Theta) = \frac{1}{| \mathcal{D} |} \left (\ sum_ {(x, y_1) \in\mathcal{D}} P (M = y_1 | U (\Theta) x) + \ sum_ {(x, y_2) \in\mathcal{D}} P (M = y_2 | U (\Theta) x) \right) \end{align} $ $ où $P (M = y | z) $ est la probabilité de mesurer $y $ dans l’État Quantum $z $.
Ici, il suffit de comprendre que la fonction de probabilité $ \mathcal{L} (\Theta) $ est lisse dans $ \Theta $ et que son dérivé dans un $ \ theta_j $ peut être calculé en faisant essentiellement le même protocole Quantum que celui utilisé pour calculer la fonction de probabilité proprement dite. Cela permet d’optimiser la profondeur du gradient $ \mathcal{L} (\Theta) $.

### <a name="classifier-bias-and-training-score"></a>Décalage du classifieur et score de formation

Compte tenu de certaines valeurs intermédiaires (ou finales) des paramètres de $ \Theta $, nous devons identifier une seule valeur réelle $b $ savent comme *biais de classifieur* pour effectuer l’inférence. La règle d’inférence d’étiquette fonctionne comme suit : 
- Une étiquette $y _2 $ est assignée à un exemple $x $ si et seulement si $P (M = y_2 | U (\Theta) x) + b > $0,5 (RULE1) (dans le cas contraire, une étiquette $y 1 _ 1 $) est affectée

Clairement $b $ doit être dans l’intervalle $ (-0.5, + 0,5) $ pour être significatif.

Un cas d’apprentissage $ (x, y) \Dans \mathcal{D} $ est considéré comme une *classification* incorrecte en raison de l’écart $b $ si l’étiquette déduite pour $x $ comme par Rule1 est en fait différente de $y $. Le nombre global de classifications incorrectes est le *score d’apprentissage* du classifieur en fonction de l’écart $b $. L’écart *optimal* du classifieur $b $ minimise le score de formation. Il est facile de le voir, étant donné les estimations de probabilité précalculées $\{ P (M = y_2 | U (\Theta) x) | (x, *) \in\mathcal{D} \}$, le décalage optimal du classifieur peut être trouvé par la recherche binaire dans Interval $ (-0.5, + 0.5) $ en effectuant au maximum $ \ log_2 (| \mathcal{D} |) $ étapes.

### <a name="reference"></a>Informations de référence

Ces informations doivent être suffisantes pour commencer à utiliser le code. Toutefois, si vous souhaitez en savoir plus sur ce modèle, veuillez lire la proposition d’origine : [ *« classificateurs quantiques centrés sur le circuit », Maria Schuld, Alex Bocharov, Krysta Svore et Nathan Wiebe*](https://arxiv.org/abs/1804.00633)
