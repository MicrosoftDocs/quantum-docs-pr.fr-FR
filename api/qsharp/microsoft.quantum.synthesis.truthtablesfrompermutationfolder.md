---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 86e112782825303805029b2f9f6cfd9d6ce9e8b6
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96231022"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Logique de décomposition pour un index à une seule variable

```qsharp
function TruthTablesFromPermutationFolder (numVars : Int, state : Microsoft.Quantum.Synthesis.DecompositionState, index : Int) : Microsoft.Quantum.Synthesis.DecompositionState
```


## <a name="description"></a>Description

Cela prend l’état actuel et génère une permutation mise à jour et ajoute éventuellement de nouvelles fonctions pour les portes contrôlées.

## <a name="input"></a>Entrée

### <a name="numvars--int"></a>numVars : [entier](xref:microsoft.quantum.lang-ref.int)




### <a name="state--decompositionstate"></a>État : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)




### <a name="index--int"></a>index : [int](xref:microsoft.quantum.lang-ref.int)





## <a name="output--decompositionstate"></a>Sortie : [DecompositionState](xref:Microsoft.Quantum.Synthesis.DecompositionState)

