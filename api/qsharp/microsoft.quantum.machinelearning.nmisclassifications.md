---
uid: Microsoft.Quantum.MachineLearning.NMisclassifications
title: NMisclassifications fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: NMisclassifications
qsharp.summary: Given a set of inferred labels and a set of correct labels, returns the number of indices at which each set of labels differ.
ms.openlocfilehash: 9e356d68233519978e007e5a2999ca1be8cb7f83
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701368"
---
# <a name="nmisclassifications-function"></a>NMisclassifications fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


Étant donné un ensemble d’étiquettes déduites et un ensemble d’étiquettes correctes, retourne le nombre d’index dont chaque ensemble d’étiquettes est différent.

```qsharp
function NMisclassifications (proposed : Int[], actual : Int[]) : Int
```


## <a name="input"></a>Entrée

### <a name="proposed--int"></a>proposé : [int](xref:microsoft.quantum.lang-ref.int)[]




### <a name="actual--int"></a>réel : [int](xref:microsoft.quantum.lang-ref.int)[]





## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)

Nombre d’index de ce `idx` type `inferredLabels[idx] != actualLabels[idx]` .