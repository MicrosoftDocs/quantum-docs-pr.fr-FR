---
uid: Microsoft.Quantum.Chemistry.HTermsToGenSys
title: HTermsToGenSys fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTermsToGenSys
qsharp.summary: Converts a Hamiltonian in `HTerm[]` data format to a GeneratorSystem.
ms.openlocfilehash: 936e1bcc58b2f1af3bdb606884128c38d2f58867
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204111"
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