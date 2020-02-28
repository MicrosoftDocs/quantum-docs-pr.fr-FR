---
title: Oracles de quantum
description: Découvrez comment utiliser et définir des opérations d’Oracle quantique et de boîte noire utilisées comme entrée d’un autre algorithme.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
ms.openlocfilehash: 1d1d0b0903db8e994166c3e8a5798f70742a1c7e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77904925"
---
# <a name="quantum-oracles"></a>Oracle Quantum

Oracle $O $ est une opération « boîte noire » utilisée comme entrée d’un autre algorithme.
Ces opérations sont souvent définies à l’aide d’une fonction classique $f : \\{0, 1\\} ^ n \To \\{0, 1\\} ^ m $ qui prend une entrée binaire de $n $ bits et produit une sortie binaire de $m $ bits.
Pour ce faire, considérons une entrée binaire particulière $x = (x_{0}, x_{1}, \dots, x_ {n-1}) $.
Nous pouvons étiqueter les États qubit sous la forme $ \ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_ {n-1}} $.

Nous pouvons tenter d’abord de définir $O $ afin que $O \ket{x} = \ket{f (x)} $, mais cela pose quelques problèmes.
Tout d’abord, $f $ peut avoir une taille différente d’entrée et de sortie ($n \ne m $), de sorte que l’application de $O $ modifie le nombre de qubits dans le registre.
Deuxièmement, même si $n = m $, la fonction ne peut pas être réversible : si $f (x) = f (y) $ pour un $x \ne y $, alors $O \ket{x} = O\ket {y} $, mais $O ^ \dagger O\ket {x} \ne O ^ \dagger O\ket {y} $.
Cela signifie que nous ne pouvons pas construire l’opération joint $O ^ \dagger $, et Oracle doivent avoir un voisin défini pour eux.

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a>Définition d’Oracle par son effet sur les États de base de calcul
Nous pouvons traiter ces deux problèmes en introduisant un deuxième Registre de $m $ qubits pour conserver notre réponse.
Ensuite, nous allons définir l’effet d’Oracle sur tous les États de base de calcul : pour tous les $x \Dans \\{0, 1\\} ^ n $ et $y \Dans \\{0, 1\\} ^ m $,

$ $ \begin{align} O (\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f (x)}.
\end{align} $ $

À présent $O = O ^ \dagger $ par construction, nous avons résolu les deux problèmes précédents.

> [!TIP]
> Pour voir que $O = O ^ {\dagger} $, Notez que $O ^ 2 = \boldone $ depuis $a \oplus b \oplus b = a $ pour tous les $a, b \Dans \{0, 1\}$.
> Par conséquent, $O \ket{x} \ket{y \oplus f (x)} = \ket{x} \ket{y \oplus f (x) \oplus f (x)} = \ket{x} \ket{y} $.

Plus important encore, la définition d’une Oracle de cette façon pour chaque État de base de calcul $ \ket{x}\ket{y} $ définit également la manière dont $O $ agit pour tout autre État.
Cela vient immédiatement du fait que $O $, comme toutes les opérations de Quantum, est linéaire dans l’État sur lequel il agit.
Prenons l’exemple de l’opération Hadarmard, par exemple, qui est définie par $H \ket{0} = \ket{+} $ et $H \ket{1} = \ket{-}$.
Si nous souhaitons savoir comment $H $ agit sur $ \ket{+} $, nous pouvons utiliser ce $H $ est linéaire,

$ $ \begin{align} H\ket {+} & = \frac{1}{\sqrt{2}} H (\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0}-\ket{1}) = \ket{0}.
\end{align} $ $

Dans le cas de la définition de notre $O Oracle $, nous pouvons utiliser de la même façon que n’importe quel état $ \ket{\Psi} $ sur $n + m $ qubits peut être écrit comme

$ $ \begin{align} \ket{\Psi} & = \ sum_ {x \Dans \\{0, 1\\} ^ n, y \Dans \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \end{align} $ $

où $ \alpha : \\{0, 1\\} ^ n \times \\{0, 1\\} ^ m \To \mathbb{C} $ représente les coefficients de l’État $ \ket{\Psi} $. Faisant

$ $ \begin{align} O \ket{\Psi} & = O \ sum_ {x \Dans \\{0, 1\\} ^ n, y \Dans \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y} \\\\ & = \ sum_ {x \Dans \\{0, 1\\} ^ n, y \Dans \\{0, 1\\} ^ m} \alpha (x, y) O \ket{x} \ket{y} \\\\ & = \ sum_ {x \Dans \\{0, 1\\} ^ n , y \Dans \\{0, 1\\} ^ m} \alpha (x, y) \ket{x} \ket{y \oplus f (x)}.
\end{align} $ $

## <a name="phase-oracles"></a>Oracle phase
Vous pouvez également Encoder $f $ dans Oracle $O $ en appliquant une _phase_ basée sur l’entrée à $O $.
Par exemple, nous pouvons définir $O $ de sorte que $ $ \begin{align} O \ket{x} = (-1) ^ {f (x)} \ket{x}.
\end{align} $ $ si une phase Oracle agit sur un registre initialement dans un état de base de calcul $ \ket{x} $, cette phase est une phase globale qui n’est donc pas observable.
Toutefois, Oracle peut être une ressource très puissante si elle est appliquée à une superposition ou en tant qu’opération contrôlée.
Par exemple, considérez un Orcale de phase $O _f $ pour une fonction à qubit unique $f $.
Ensuite, $ $ \begin{align} O_f \ket{+} & = O_f (\ket{0} + \ket{1})/\sqrt{2} \\\\ & = ((-1) ^ {f (0)} \ket{0} + (-1) ^ {f (1)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} (\ket{0} + (-1) ^ {f (1)-f (0)} \ket{1})/\sqrt{2} \\\\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket{+}.
\end{align} $ $

Plus généralement, les deux vues d’Oracle peuvent être élargies pour représenter des fonctions classiques qui retournent des nombres réels au lieu d’un seul bit.

Le choix de la meilleure façon d’implémenter Oracle dépend fortement de la façon dont ce Oracle sera utilisé dans un algorithme donné.
Par exemple, l' [algorithme Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) s’appuie sur Oracle implémenté de la même façon, tandis que l' [algorithme de Grover s'](https://en.wikipedia.org/wiki/Grover's_algorithm) appuie sur Oracle implémenté de la seconde façon.


Pour plus d’informations, nous vous suggérons la discussion dans [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).
