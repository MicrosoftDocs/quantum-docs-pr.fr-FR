---
uid: Microsoft.Quantum.Synthesis.SizeAdjustedTruthTable
title: SizeAdjustedTruthTable fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: SizeAdjustedTruthTable
qsharp.summary: >-
  Adjusts truth table from array of Booleans according to number of variables

  A new array is returned of length `2^numVars`, possibly requiring to extend `table`'s size with `false` entries or truncating it to `2^numVars` elements.
ms.openlocfilehash: 3480f022df7a289594b003f201d16d8bf7c29d7e
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709281"
---
# <a name="sizeadjustedtruthtable-function"></a>SizeAdjustedTruthTable fonction)

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)


Ajuste la table de vérité à partir d’un tableau de valeurs booléennes en fonction du nombre de variables

Un nouveau tableau est retourné de longueur `2^numVars` , ce qui peut nécessiter l’extension de `table` la taille de dans les `false` entrées ou sa troncation aux `2^numVars` éléments.

```qsharp
function SizeAdjustedTruthTable (table : Bool[], numVars : Int) : Bool[]
```


## <a name="input"></a>Entrée

### <a name="table--bool"></a>table : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Table de vérité en tant que tableau de valeurs de vérité


### <a name="numvars--int"></a>numVars : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de variables



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Table de vérité à taille ajustée