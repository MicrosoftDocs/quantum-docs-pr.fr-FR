---
uid: Microsoft.Quantum.Environment.GetQubitsAvailableToUse
title: Opération GetQubitsAvailableToUse
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Environment
qsharp.name: GetQubitsAvailableToUse
qsharp.summary: Returns the number of qubits currently available to use.
ms.openlocfilehash: 25d43d369193fc7453fd5ce9c50769c438a69afb
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702586"
---
# <a name="getqubitsavailabletouse-operation"></a>Opération GetQubitsAvailableToUse

Espace de noms : [Microsoft. Quantum. Environment](xref:Microsoft.Quantum.Environment)

Packages [](https://nuget.org/packages/)


Retourne le nombre de qubits actuellement disponibles à utiliser.

```qsharp
operation GetQubitsAvailableToUse () : Int
```


## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits qui peuvent être alloués dans une `using` instruction.
Si l’ordinateur cible utilisé ne fournit pas ces informations, `-1` est retourné.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Environment. GetQubitsAvailableToBorrow](xref:Microsoft.Quantum.Environment.GetQubitsAvailableToBorrow)