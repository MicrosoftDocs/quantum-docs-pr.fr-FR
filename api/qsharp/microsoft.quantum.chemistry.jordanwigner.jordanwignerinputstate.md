---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Type défini par l’utilisateur JordanWignerInputState
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 171a2999ab8c73925d4624c565bfd41a4e73c99d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703186"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Type défini par l’utilisateur JordanWignerInputState

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Packages [](https://nuget.org/packages/)


Format des données passées de C# à Q # pour représenter la préparation de l’état initial la signification des données représentées est déterminée par l’algorithme qui les reçoit.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

