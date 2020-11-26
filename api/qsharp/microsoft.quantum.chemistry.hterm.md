---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Type défini par l’utilisateur HTerm
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 504d55dc57ce92c12e6f016e9afcedfd59664aa1
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204128"
---
# <a name="hterm-user-defined-type"></a>Type défini par l’utilisateur HTerm

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format des données passées de C# à Q # pour représenter un terme de la même façon.
La signification des données représentées est déterminée par l’algorithme qui la reçoit.

```qsharp

newtype HTerm = (Int[], Double[]);
```

