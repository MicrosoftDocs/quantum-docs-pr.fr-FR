---
uid: Microsoft.Quantum.Chemistry.HTermToGenIdx
title: HTermToGenIdx fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermToGenIdx
qsharp.summary: Converts a Hamiltonian term in `HTerm` data format to a GeneratorIndex.
ms.openlocfilehash: dd72355adb32f9a0d109ee36b24be2d445f3fa66
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703552"
---
# <a name="htermtogenidx-function"></a>HTermToGenIdx fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Packages [](https://nuget.org/packages/)


Convertit un terme de la `HTerm` structure de données en GeneratorIndex.

```qsharp
function HTermToGenIdx (term : Microsoft.Quantum.Chemistry.HTerm, termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorIndex
```


## <a name="input"></a>Entrée

### <a name="term--hterm"></a>terme : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)

Données d’entrée au `HTerm` format.


### <a name="termtype--int"></a>termType : [int](xref:microsoft.quantum.lang-ref.int)[]

Informations supplémentaires ajoutées à GeneratorIndex.



## <a name="output--generatorindex"></a>Sortie : [GeneratorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

GeneratorIndex représentant un terme de Hamilton représenté par `term` , ainsi que des informations supplémentaires ajoutées par `termType` .