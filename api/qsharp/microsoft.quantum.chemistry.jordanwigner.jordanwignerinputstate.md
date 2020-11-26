---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Type défini par l’utilisateur JordanWignerInputState
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 81993a7449098c03639cf090fb36ed39c6ba17c0
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214685"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Type défini par l’utilisateur JordanWignerInputState

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format des données passées de C# à Q # pour représenter la préparation de l’état initial la signification des données représentées est déterminée par l’algorithme qui les reçoit.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

