---
uid: Microsoft.Quantum.Synthesis.FlipMasks
title: FlipMasks fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: FlipMasks
qsharp.summary: For every 2-level unitary calculates "flip mask", which denotes qubits which should be inverted before and after applying corresponding 1-qubit gate. For convenience prepends result with 0.
ms.openlocfilehash: ca0ce69b3353379a42cc109cebb32efe4e364825
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98859158"
---
# <a name="flipmasks-function"></a>FlipMasks fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour chaque unité de 2 niveaux, calcule le masque de retournement, qui désigne les qubits qui doivent être inversés avant et après l’application de la porte 1-qubit correspondante.
Pour des raisons pratiques, le résultat est trop à 0.

```qsharp
function FlipMasks (decomposition : (Microsoft.Quantum.Math.Complex[][], Int, Int)[], allQubitsMask : Int) : Int[]
```


## <a name="input"></a>Entrée

### <a name="decomposition--complexintint"></a>décomposition : ([complexe](xref:Microsoft.Quantum.Math.Complex)[] [],[int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []




### <a name="allqubitsmask--int"></a>allQubitsMask : [entier](xref:microsoft.quantum.lang-ref.int)





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

