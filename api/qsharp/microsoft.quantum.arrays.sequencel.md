---
uid: Microsoft.Quantum.Arrays.SequenceL
title: Fonction Sequence
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: SequenceL
qsharp.summary: Get an array of integers in a given interval.
ms.openlocfilehash: d5ce63575e703341fce42c0be393765c342bbd89
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705782"
---
# <a name="sequencel-function"></a>Fonction Sequence

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


Obtient un tableau d’entiers dans un intervalle donné.

```qsharp
function SequenceL (from : BigInt, to : BigInt) : BigInt[]
```


## <a name="input"></a>Entrée

### <a name="from--bigint"></a>de : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Index de début inclusif de l’intervalle.


### <a name="to--bigint"></a>à : [bigint](xref:microsoft.quantum.lang-ref.bigint)

Index de fin inclusif de l’intervalle qui n’est pas inférieur à `from` .



## <a name="output--bigint"></a>Sortie : [bigint](xref:microsoft.quantum.lang-ref.bigint)[]

Tableau contenant la séquence de nombres `from` , `from + 1` ,..., `to` .

## <a name="remarks"></a>Notes

La différence entre `from` et `to` doit tenir dans une `Int` valeur.