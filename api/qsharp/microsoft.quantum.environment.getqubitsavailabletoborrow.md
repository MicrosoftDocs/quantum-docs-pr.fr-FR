---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow
title: Opération GetQubitsAvailableToBorrow
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToBorrow
qsharp.summary: Returns the number of qubits currently available to borrow.
ms.openlocfilehash: 30b97c2b6e1353f008d085c3bae6160763557c67
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201459"
---
# <a name="getqubitsavailabletoborrow-operation"></a>Opération GetQubitsAvailableToBorrow

Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne le nombre de qubits actuellement disponibles pour emprunter.

```qsharp
operation GetQubitsAvailableToBorrow () : Int
```


## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits qui peuvent être empruntés et qui ne sont pas alloués dans le cadre d’une `borrowing` instruction.
Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Environment. GetQubitsAvailableToUse](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToUse)