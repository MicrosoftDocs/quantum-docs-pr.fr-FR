---
uid: Microsoft.Quantum.Synthesis.TruthTablesFromPermutationFolder
title: TruthTablesFromPermutationFolder fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: TruthTablesFromPermutationFolder
qsharp.summary: Decomposition logic for a single variable index
ms.openlocfilehash: 6b00c9e880ed7b7b3bf446dcb17dab3bab7a83a7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708846"
---
# <a name="truthtablesfrompermutationfolder-function"></a>TruthTablesFromPermutationFolder fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


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

