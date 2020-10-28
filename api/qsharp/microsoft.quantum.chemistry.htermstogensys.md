---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: b78ff393fa1e51c38028ef56bb3c61b8f1d5e478
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703555"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Packages [](https://nuget.org/packages/)


Convertit un GeneratorSystem de l’un au `HTerm[]` format de données en un.

```qsharp
function HTermsToGenSys (data : Microsoft.Quantum.Chemistry.HTerm[], termType : Int[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="data--hterm"></a>données : [HTerm](xref:Microsoft.Quantum.Chemistry.HTerm)[]

Données d’entrée au `HTerm[]` format.


### <a name="termtype--int"></a>termType : [int](xref:microsoft.quantum.lang-ref.int)[]

Informations supplémentaires ajoutées à GeneratorIndex.



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

GeneratorSystem représentant un sous-Hamilton représenté par l’entrée `data` .