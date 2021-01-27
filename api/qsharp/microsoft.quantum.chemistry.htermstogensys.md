---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 3d5963b8751a22d7116d6c1cf094d89e1d6b556f
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851763"
---
# <a name="htermstogensys-function"></a>HTermsToGenSys fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


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