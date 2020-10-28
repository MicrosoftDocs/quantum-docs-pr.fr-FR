---
uid: Microsoft.Quantum.Preparation.PrepareSingleQubitIdentity
title: Opération PrepareSingleQubitIdentity
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: PrepareSingleQubitIdentity
qsharp.summary: >-
  Prepares a qubit in the maximally mixed state.

  It prepares the given qubit in the $\boldone / 2$ state by applying the depolarizing channel $$ \begin{align} \Omega(\rho) \mathrel{:=} \frac{1}{4} \sum_{\mu \in \{0, 1, 2, 3\}} \sigma\_{\mu} \rho \sigma\_{\mu}^{\dagger}, \end{align} $$ where $\sigma\_i$ is the $i$th Pauli operator, and where $\rho$ is a density operator representing a mixed state.
ms.openlocfilehash: 12a650568aa5682e8fb6498808d188b154527acb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709029"
---
# <a name="preparesinglequbitidentity-operation"></a>Opération PrepareSingleQubitIdentity

Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)

Packages [](https://nuget.org/packages/)


Prépare un qubit dans l’état maximal mélangé.

Elle prépare le qubit donné dans l’État $ \boldone/$2 en appliquant le canal de dépolarisation $ $ \begin{align} \Omega (\rho) \mathrel{ : =} \frac {1} {4} \ sum_ {\mu \Dans \{ 0, 1, 2, 3 \} } \sigma \_ {\mu} \rho \sigma \_ {\mu} ^ {\dagger}, \end{align} $ $ où $ \sigma \_ i $ correspond à l’opérateur $i $ th Pauli et où $ \rho $ est un opérateur de densité représentant un État mixte.

```qsharp
operation PrepareSingleQubitIdentity (qubit : Qubit) : Unit
```


## <a name="input"></a>Entrée

### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Un qubit dont l’État doit être dépolarisé de la manière décrite ci-dessus.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

L’État mixte $ \boldone/$2 décrivant le résultat de l’application de cette opération à un état décrit de façon implicite une valeur d’attente sur les choix aléatoires effectués dans cette opération.
Ainsi, pour n’importe quelle application, cette opération mappe des États purs à des États purs, mais elle agit comme décrit en prévision.
En particulier, cette opération peut être utilisée dans la tomographie de processus pour mesurer les composants *non unitaires* d’un canal.