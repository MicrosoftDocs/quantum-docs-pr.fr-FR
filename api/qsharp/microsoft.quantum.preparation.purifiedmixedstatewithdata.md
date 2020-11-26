---
uid: Microsoft.Quantum.Preparation.PurifiedMixedStateWithData
title: PurifiedMixedStateWithData fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedStateWithData
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed\rstate, entangled with a register representing a given collection of data.\rA \"purified mixed state with data\" refers to a state of the form Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |\U0001D465ᵢ⟩ |garbageᵢ⟩,\rwhere each \U0001D465ᵢ is a bitstring encoding additional data associated with the register |\U0001D456⟩.\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: c89ee8f5df58e5d6b154b67d2b39db208bc8a215
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96229951"
---
# <a name="purifiedmixedstatewithdata-function"></a>PurifiedMixedStateWithData fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération qui prépare une purification d’un État mixte donné, associée à un registre qui représente une collection donnée de données.
Un « État mixte purifié avec des données » fait référence à un État sous la forme σI √ pi | i ⟩ | XI ⟩ | garbagei ⟩, où chaque XI est un bitstring codant des données supplémentaires associées au registre | i ⟩.

https://arxiv.org/pdf/1805.03662.pdf?page=15Pour plus d’informations, consultez.

```qsharp
function PurifiedMixedStateWithData (targetError : Double, coefficients : (Double, Bool[])[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Description

Utilise la technique Quantum ROM pour représenter une matrice de densité donnée, en retournant cette représentation comme opération de préparation de l’État.

En particulier, étant donné une liste de $N $ coefficients $ \ alpha_j $ et un bitstring $ \vec{x}_j $ associé à chaque coefficient, cette fonction retourne une opération qui utilise la technique Quantum ROM pour préparer une approximation $ $ \begin{align} \tilde\rho = \sum_{j = 0} ^ {N-1} p_j \ket{j}\bra{j} \otimes \ket{\vec{x} _J} \bra{\vec{x}_j} \end{align} $ $ de l’État mixte $ $ \begin{align} \rho = \sum_{j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} \otimes \ket{\vec{x} _j} \bra{\vec{x} _j}, \end{align} $ $ où chaque $p _j $ est une approximation du coefficient $ \ alpha_j $ de sorte que $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ pour chaque $j $.

En cas de réussite d’un registre d’index et d’un registre de garbage qubits, initialement à l’État $ \ket {0} \ket{00\cdots 0}, l’opération retournée prépare les deux registres dans la purification de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j} \ket{\vec{x} _J} \ket{\text{garbage} _J}, \end{align} $ $ de sorte que la réinitialisation et la désallocation du registre de nettoyage de la mémoire enregistrent la préparation souhaitée dans l’erreur cible $ \epsilon $.

## <a name="input"></a>Entrée

### <a name="targeterror--double"></a>targetError : [double](xref:microsoft.quantum.lang-ref.double)

L’erreur cible $ \epsilon $.


### <a name="coefficients--doublebool"></a>coefficients : ([double](xref:microsoft.quantum.lang-ref.double),[bool](xref:microsoft.quantum.lang-ref.bool)[]) []

Tableau de $N $ coefficients spécifiant la probabilité des États de base, ainsi que le bitstring $ \vec{x} _j $ associé à chaque coefficient.
Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Sortie : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Opération qui prépare $ \tilde \rho $ comme une purification sur un index commun et un garbage Register.

## <a name="remarks"></a>Notes

Les coefficients fournis à cette opération sont normalisés après la norme 1, de sorte que les coefficients sont toujours considérés comme une distribution de probabilité catégorique valide.

## <a name="references"></a>Références

- Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PurifiedMixedState](xref:Microsoft.Quantum.Preparation.PurifiedMixedState)