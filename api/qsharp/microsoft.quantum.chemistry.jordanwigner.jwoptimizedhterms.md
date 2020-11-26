---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JWOptimizedHTerms
title: Type défini par l’utilisateur JWOptimizedHTerms
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JWOptimizedHTerms
qsharp.summary: Format of data passed from C# to Q# to represent terms of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: e86e9da42ce002babdd4d161eca4646cca7071ab
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224953"
---
# <a name="jwoptimizedhterms-user-defined-type"></a>Type défini par l’utilisateur JWOptimizedHTerms

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format des données passées de C# à Q # pour représenter les termes du niveau de la Hamilton.
La signification des données représentées est déterminée par l’algorithme qui la reçoit.

```qsharp

newtype JWOptimizedHTerms = (Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[], Microsoft.Quantum.Chemistry.HTerm[]);
```

