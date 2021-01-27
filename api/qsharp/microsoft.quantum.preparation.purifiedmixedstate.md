---
uid: Microsoft.Quantum.Preparation.PurifiedMixedState
title: PurifiedMixedState fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PurifiedMixedState
qsharp.summary: "Returns an operation that prepares a a purification of a given mixed state.\rA \"purified mixed state\" refers to states of the form |ψ⟩ = Σᵢ √\U0001D45Dᵢ |\U0001D456⟩ |garbageᵢ⟩ specified by a vector of\rcoefficients {\U0001D45Dᵢ}. States of this form can be reduced to mixed states ρ ≔ \U0001D45Dᵢ |\U0001D456⟩⟨\U0001D456| by tracing over the \"garbage\"\rregister (that is, a mixed state that is diagonal in the computational basis).\r\rSee https://arxiv.org/pdf/1805.03662.pdf?page=15 for further discussion."
ms.openlocfilehash: 594a1d9fa674e457ab88072ade4198283b677af6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854303"
---
# <a name="purifiedmixedstate-function"></a>PurifiedMixedState fonction)

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Retourne une opération qui prépare une purification d’un État mixte donné.
Un « État mixte purifié » fait référence aux États de la forme | ψ ⟩ = σI √ pi | i ⟩ | garbagei ⟩ spécifiés par un vecteur de coefficients {pi}. Les États de ce formulaire peuvent être réduits à des États mixtes p ≔ pi | i ⟩ ⟨ i | en traçant sur le registre de « nettoyage » (autrement dit, un État mixte qui est diagonal dans la base de calcul).

https://arxiv.org/pdf/1805.03662.pdf?page=15Pour plus d’informations, consultez.

```qsharp
function PurifiedMixedState (targetError : Double, coefficients : Double[]) : Microsoft.Quantum.Preparation.MixedStatePreparation
```


## <a name="description"></a>Description

Utilise la technique Quantum ROM pour représenter une matrice de densité donnée, en retournant cette représentation comme opération de préparation de l’État.

En particulier, à partir d’une liste de $N $ coefficients $ \ alpha_j $, cette fonction retourne une opération qui utilise la technique Quantum ROM pour préparer une approximation $ $ \begin{align} \tilde\rho = \ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} \end{align} $ $ de l’État mixte $ $ \begin{align} \rho = \ sum_ {j = 0} ^ {N-1} \ FRAC {| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j}, \end{align} $ $ où chaque $p _j $ est une approximation du coefficient $ \ alpha_j $ de sorte que $ $ \begin{align} \left | p_j-\frac{| \ alpha_j |} {\ sum_k | \ alpha_k |} \Le \frac{\epsilon}{N} \end{align} $ $ pour chaque $j $.

En cas de réussite d’un registre d’index et d’un registre de garbage qubits, initialement, dans l’État $ \ket {0} \ket{00\cdots 0}, l’opération retournée prépare les deux registres dans la purification de $ \tilde \rho $, $ $ \begin{align} \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}, \end{align} $ $, de telle sorte que la réinitialisation et la désallocation du registre de nettoyage de la mémoire enregistrent la préparation souhaitée

## <a name="input"></a>Entrée

### <a name="targeterror--double"></a>targetError : [double](xref:microsoft.quantum.lang-ref.double)

L’erreur cible $ \epsilon $.


### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau de $N $ coefficient spécifiant la probabilité des États de base.
Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.



## <a name="output--mixedstatepreparation"></a>Sortie : [MixedStatePreparation](xref:Microsoft.Quantum.Preparation.MixedStatePreparation)

Opération qui prépare $ \tilde \rho $ comme une purification sur un index commun et un garbage Register.

## <a name="example"></a>Exemple

L’extrait de code suivant prépare une purification de l’État $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, où $ \vec\alpha = (1.0, 2,0, 3,0, 4,0, 5,0) $, et l’erreur cible est $10 ^ {-3} $ :

```qsharp
let coefficients = [1.0, 2.0, 3.0, 4.0, 5.0];
let targetError = 1e-3;
let purifiedState = PurifiedMixedState(targetError, coefficients);
using (indexRegister = Qubit[purifiedState::Requirements::NIndexQubits]) {
    using (garbageRegister = Qubit[purifiedState::Requirements::NGarbageQubits]) {
        purifiedState::Prepare(LittleEndian(indexRegister), new Qubit[0], garbageRegister);
    }
}
```

## <a name="remarks"></a>Notes

Les coefficients fournis à cette opération sont normalisés après la norme 1, de sorte que les coefficients sont toujours considérés comme une distribution de probabilité catégorique valide.

## <a name="references"></a>Références

- Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. PREPARATION. PurifiedMixedStateWithData](xref:Microsoft.Quantum.Preparation.PurifiedMixedStateWithData)