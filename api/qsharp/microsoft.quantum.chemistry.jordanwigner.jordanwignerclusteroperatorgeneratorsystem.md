---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerClusterOperatorGeneratorSystem
title: JordanWignerClusterOperatorGeneratorSystem fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerClusterOperatorGeneratorSystem
qsharp.summary: Converts a Hamiltonian described by `JWOptimizedHTerms` to a `GeneratorSystem` expressed in terms of the `GeneratorIndex` convention defined in this file.
ms.openlocfilehash: e6deca3c8261c7730e9b208d9f834ad0db101fd3
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214804"
---
# <a name="jordanwignerclusteroperatorgeneratorsystem-function"></a>JordanWignerClusterOperatorGeneratorSystem fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Convertit un de Hamilton décrit par en `JWOptimizedHTerms` un `GeneratorSystem` exprimé en termes de la `GeneratorIndex` Convention définie dans ce fichier.

```qsharp
function JordanWignerClusterOperatorGeneratorSystem (data : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState[]) : Microsoft.Quantum.Simulation.GeneratorSystem
```


## <a name="input"></a>Entrée

### <a name="data--jordanwignerinputstate"></a>données : [JordanWignerInputState](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState)[]

Description de la structure de l’un au `JWOptimizedHTerms` format.



## <a name="output--generatorsystem"></a>Sortie : [GeneratorSystem](xref:Microsoft.Quantum.Simulation.GeneratorSystem)

Représentation de Hamilton sous la forme `GeneratorSystem` .