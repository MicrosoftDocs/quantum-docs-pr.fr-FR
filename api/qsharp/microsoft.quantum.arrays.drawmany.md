---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Opération DrawMany
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: 3185f2ec01a2b9d01cff82a0c4667f12483801a7
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96209993"
---
# <a name="drawmany-operation"></a>Opération DrawMany

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Répète une opération pour un nombre donné d’échantillons, en collectant ses sorties dans un tableau.

```qsharp
operation DrawMany<'TInput, 'TOutput> (op : ('TInput => 'TOutput), nSamples : Int, input : 'TInput) : 'TOutput[]
```


## <a name="input"></a>Entrée

### <a name="op--tinput--toutput"></a>OP : 'TInput => 'TOutput 

Opération à appeler à plusieurs reprises.


### <a name="nsamples--int"></a>nSamples : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre d’exemples d’appels `op` à collecter.


### <a name="input--tinput"></a>entrée : 'TInput

Entrée à passer à `op` .



## <a name="output--toutput"></a>Sortie : 'TOutput []



## <a name="type-parameters"></a>Paramètres de type

### <a name="tinput"></a>'TInput


### <a name="toutput"></a>«TOutput



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)