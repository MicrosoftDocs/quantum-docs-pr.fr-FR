---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Opération GetQubitsAvailableToUse
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: ce461b03a08b4c83b9de142c957ce5c590fe9659
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96201408"
---
# <a name="getqubitsavailabletouse-operation"></a>Opération GetQubitsAvailableToUse

Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Retourne le nombre de qubits actuellement disponibles à utiliser.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits qui peuvent être alloués dans une `using` instruction.
Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)