---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerFermionFunction
title: JordanWignerFermionFunction fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerFermionFunction
qsharp.summary: Represents a dynamical generator as a set of simulatable gates and an expansion in the JordanWigner basis.
ms.openlocfilehash: a1c0b56e18f3adfb6c413880cc0c155741a3255a
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98838873"
---
# <a name="jordanwignerfermionfunction-function"></a>JordanWignerFermionFunction fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Représente un générateur dynamique sous la forme d’un ensemble de portes simulables et d’une expansion dans la base de JordanWigner.

```qsharp
function JordanWignerFermionFunction (generatorIndex : Microsoft.Quantum.Simulation.GeneratorIndex) : Microsoft.Quantum.Simulation.EvolutionUnitary
```


## <a name="input"></a>Entrée

### <a name="generatorindex--generatorindex"></a>generatorIndex : [generatorIndex](xref:Microsoft.Quantum.Simulation.GeneratorIndex)

Index de générateur à représenter comme évolution unitaire dans le JordanWigner.



## <a name="output--evolutionunitary"></a>Sortie : [EvolutionUnitary](xref:Microsoft.Quantum.Simulation.EvolutionUnitary)

`EvolutionUnitary`Représentant l’évolution temporelle du terme référencé dans’generatorIndex.