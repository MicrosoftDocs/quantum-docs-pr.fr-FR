---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Opération GetQubitsAvailableToBorrow
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow. This includes unused qubits; that is, this includes the qubits returned by `GetQubitsAvailableToUse`.
ms.openlocfilehash: cb56ce4aefd7a03c0f0827b8d34688ef17988f56
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702589"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Opération GetQubitsAvailableToBorrow

Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Packages [](https://nuget.org/packages/)


Retourne le nombre de qubits actuellement disponibles pour emprunter.
Cela comprend les qubits inutilisés ; autrement dit, cela comprend le qubits retourné par `GetQubitsAvailableToUse` .

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits qui peuvent être alloués dans une `borrowing` instruction.
Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)