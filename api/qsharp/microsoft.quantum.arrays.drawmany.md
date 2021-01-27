---
uid: Microsoft.Quantum.Arrays.DrawMany
title: Opération DrawMany
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: DrawMany
qsharp.summary: Repeats an operation for a given number of samples, collecting its outputs in an array.
ms.openlocfilehash: bf63ce308679cef97c776d3383ff732ed4d4e500
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98846204"
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



## <a name="example"></a>Exemple

L’exemple suivant illustre un entier, étant donné une opération qui échantillonne un seul bit à la fois.

```qsharp
let randomInteger = BoolArrayAsInt(DrawMany(SampleRandomBit, 16, ()));
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. REPEAT](xref:Microsoft.Quantum.Canon.Repeat)