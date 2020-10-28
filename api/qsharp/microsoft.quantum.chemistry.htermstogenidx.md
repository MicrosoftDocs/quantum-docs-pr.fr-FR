---
uid: Microsoft.Quantum.Chemistry.HTermsToGenIdx
title: HTermsToGenIdx fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenIdx
qsharp.summary: Converts an index to a Hamiltonian term in `HTerm[]` data format to a GeneratorIndex.
ms.openlocfilehash: 73324a48cc4b42de0d5d8618ad9e833d289125f7
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703561"
---
# <a name="htermstogenidx-function"></a>HTermsToGenIdx fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Packages [](https://nuget.org/packages/)


Convertit un index en un terme de `HTerm[]` données au format de données en GeneratorIndex.

```qsharp
function HTermsToGenIdx (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[], idx : Int) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrée

### <a name="data--hterm"></a>données : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Données d’entrée au `HTerm[]` format.


### <a name="termtype--int"></a>termType : [int](xref:microsoft.quantum.lang-ref.int)[]

Informations supplémentaires ajoutées à GeneratorIndex.


### <a name="idx--int"></a>idx : [int](xref:microsoft.quantum.lang-ref.int)

Indexer sur un terme de la « Hamilton »



## <a name="output--generatorindex"></a>Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

GeneratorIndex représentant un terme de Hamilton représenté par `data[idx]` , ainsi que des informations supplémentaires ajoutées par `termType` .