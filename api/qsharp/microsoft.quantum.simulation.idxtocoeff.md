---
uid: Microsoft.Quantum.Simulation.IdxToCoeff
title: IdxToCoeff fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: IdxToCoeff
qsharp.summary: Used in implementation of `PauliBlockEncoding`
ms.openlocfilehash: 4e10b61e56b791a39841385ec79893c1392b9563
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96225123"
---
# <a name="idxtocoeff-function"></a>IdxToCoeff fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Utilisé dans l’implémentation de `PauliBlockEncoding`

```qsharp
function IdxToCoeff (idx : Int, genFun : (Int -> Microsoft.Quantum.Simulation.GeneratorIndex), genIdxToCoeff : (Microsoft.Quantum.Simulation.GeneratorIndex -> Double)) : Double
```


## <a name="input"></a>Entrée

### <a name="idx--int"></a>idx : [int](xref:microsoft.quantum.lang-ref.int)




### <a name="genfun--int---generatorindex"></a>genFun : [int](xref:microsoft.quantum.lang-ref.int) -> [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)




### <a name="genidxtocoeff--generatorindex---double"></a>genIdxToCoeff : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex) -> [double](xref:microsoft.quantum.lang-ref.double)





## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)



## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. PauliBlockEncoding](xref:Microsoft.Quantum.Simulation.PauliBlockEncoding)