---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Opération GetQubitsAvailableToUse
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 2ed8c3789331a15b351769be960d06f6364d8047
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98827802"
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