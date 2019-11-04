---
title: Dynamique Quantum | Microsoft Docs
description: Documentation conceptuelle sur les concepts de Quantum
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.quantumdynamics
ms.openlocfilehash: 0fd27e59921fdf8429bf164c4c64cfa3b8e44160
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185339"
---
# <a name="quantum-dynamics"></a>Dynamique Quantum

Le mécanisme quantique est en grande partie l’étude de la dynamique quantique, qui cherche à comprendre comment un état de Quantum initial $ \ket{\Psi (0)} $ varie au fil du temps (consultez les [documents conceptuels](xref:microsoft.quantum.concepts.dirac) sur Quantum Computing pour plus d’informations sur la notation Dirac).
Plus précisément, étant donné la condition initiale un État Quantum, une heure d’évolution et une spécification du système dynamique Quantum, un État Quantum $ \ket{\Psi (t)} $ est recherché.
Avant de continuer à expliquer le fonctionnement de la dynamique quantique, il est utile de revenir en arrière et de réfléchir à la dynamique en matière de Dynamics, car elle fournit des Insights sur la manière dont les mécanismes quantiques ne sont pas vraiment différents de la dynamique classique.

Dans Dynamics classique, nous savons à partir de la deuxième loi de Newton que la position d’une particule évolue en fonction de $F (x, t) = ma = m\frac {\ DD ^ 2} {\dd t ^ 2} {x} (t) $, où $F (x, t) $ est la force, $m $ est la masse et $a $ est l’accélération.
Ensuite, étant donné une position initiale $x (0) $, l’heure d’évolution $t $ et la description des forces qui agissent sur la particule, nous pouvons trouver $x (t) $ en résolvant l’équation différentielle donnée par les équations de Newton pour $x (t) $.
La spécification des forces de cette façon est un peu délicate.
Nous avons donc souvent exprimé les forces en termes d’énergie potentielle du système, qui nous donne $-\partial_x V (x, t) = m \frac{\dd ^ 2} {\dd t ^ 2} {x} (t) $.
Ainsi, pour une particule, la dynamique du système est spécifiée uniquement par la fonction d’énergie potentielle, la masse de particule et le temps d’évolution.

Une plus grande langue est souvent introduite pour les Dynamics classiques qui vont au-delà de $F = ma $.
Une formulation, particulièrement utile dans le mécanisme quantique, est une mécanique de la nutrition.
Dans le mécanisme de la peste, l’énergie totale d’un système et les positions (généralisées) et le tempsa fournissent toutes les informations nécessaires pour décrire le mouvement d’un objet classique arbitraire.
En particulier, laissez $f (x, p, t) $ être une fonction des positions généralisées $x $ et le moment $p $ d’un système, et laissez $H (x, p, t) $ la fonction de Hamilton.
Par exemple, si nous prenons $f (x, p, t) = x (t) $ et $H (x, p, t) = p ^ 2 (t)/2m-V (x, t) $, nous récupérerions le cas ci-dessus de Dynamics Newton.
En général, nous avons \begin{align} \frac{d}{dt} f & = \partial_t f-(\partial_x H\partial_p f + \partial_p H\partial_x f)\\\\ & \defeq \partial_t f + \\{f, H\\}.
\end{align} ici $\\{f, H\\} $ est appelé le [crochet de poisson](https://en.wikipedia.org/wiki/Poisson_bracket) et apparaît de façon omniprésente dans Dynamics classique en raison du rôle central qu’il joue dans la définition de Dynamics.

La dynamique Quantum peut être décrite en utilisant exactement la même langue.
Le système Hamilton, ou énergie totale, spécifie complètement la dynamique de tout système Quantum fermé.
Toutefois, il existe des différences importantes entre les deux théories.
Dans les mécanismes classiques $x $ et $p $ sont simplement des nombres, tandis que dans le mécanisme Quantum, ils ne le sont pas.
En effet, ils n’ont même pas de permuter : $xp \ne px $.

Le concept mathématique approprié pour décrire ces objets de non-déplacements est un opérateur, qui, dans les cas où $x $ et $p $ ne peut prendre qu’un ensemble discret de valeurs coïncide avec le concept d’une matrice.
Par conséquent, pour des raisons de simplicité, nous partons du principe que notre système Quantum est limité afin de pouvoir être décrit à l’aide de [vecteurs et de matrices](xref:microsoft.quantum.concepts.vectors).
Nous exigeons davantage que ces matrices soient Hermitian (ce qui signifie que la transforme conjuguée de la matrice est identique à la matrice d’origine).
Cela garantit que les valeurs propres des matrices sont des valeurs réelles ; condition que nous imposez pour garantir que lorsque nous mesurons une quantité comme une position, nous n’obtenons pas un nombre imaginaire.

Tout comme les analogiques de la position et de l’inertie dans le mécanisme quantique doivent être remplacés par les opérateurs, la fonction Hamilton doit être remplacée de la même manière par un opérateur.
Par exemple, pour une particule dans l’espace libre, nous avons $H (x, p) = p ^ 2/2M $, tandis que dans le mécanisme quantique, l’opérateur de \hat{H} $ est $ \hat{H} = \hat{p} ^ 2/2M $ où $ \hat{p} $ est l’opérateur de Momentum.
À partir de ce point de vue, passer de la classique à Quantum Dynamics implique simplement de remplacer les variables utilisées dans Dynamics ordinaire avec les opérateurs.
Une fois que nous avons construit l’opérateur de la « Hamilton » en traduisant le traditionnel de la Hamilton classique en langage quantique, nous pouvons exprimer la dynamique d’une quantité mécanique de Quantum arbitraire (par exemple, opérateur mécanique quantique) $ \hat{f} (t) $ via \begin{ align} \frac{d}{DT} \hat{f} = \partial_t \hat{f} + [\hat{f}, \hat{H}], \end{align} où $ [f, H] = fH-HF $ est appelé commutator.
Cette expression est exactement similaire à l’expression classique indiquée ci-dessus, à la différence près que le crochet de poisson $\\{f, H\\} $ est remplacé par le commutator entre $f $ et $H $.
Ce processus de création d’un lieu de la même manière à l’aide de l’informatique à la recherche d’un Quantum Hamilton est connu dans le jargon quantique en tant que quantification canonique.

Quels sont les opérateurs $f $ qui nous intéressent le plus ?  La réponse à cela dépend du problème que nous souhaitons résoudre.
La quantité la plus utile à trouver est peut-être l’opérateur d’État Quantum, qui, comme indiqué dans la documentation conceptuelle précédente, peut être utilisé pour extraire tout ce que nous aimerions apprendre sur la dynamique.
Après cela (et en simplifiant le résultat dans le cas où l’un d’eux a un état pur), l’équation Schrödinger pour l’État Quantum est trouvée \begin{align} i\partial_t \ket{\Psi (t)} = \hat{H} (t) \ket{\Psi (t)}.
\end{align}

Cette équation, quoique moins intuitive que celle ci-dessus, produit peut-être l’expression la plus simple pour comprendre comment simuler le quantum dynamique sur un ordinateur Quantum ou classique.
Cela est dû au fait que la solution à l’équation différentielle peut être exprimée sous la forme suivante (pour le cas où la valeur de la variable Hamilton est constante dans $t $) \begin{align} \ket{\Psi (t)} = e ^ {-iHt} \ket{\Psi (0)}.
\end{align} ici $e ^ {-iHt} $ est une matrice d’unités.
Cela signifie qu’il existe un circuit quantique qui peut être conçu pour être exécuté, car les ordinateurs quantiques peuvent être très proches des matrices unitaires.
Cette opération de recherche d’un circuit Quantum pour implémenter l’opérateur d’évolution du temps Quantum $e ^ {-iHt} $ est ce qui est souvent appelé simulation de Quantum, ou en particulier simulation de Quantum dynamique.
