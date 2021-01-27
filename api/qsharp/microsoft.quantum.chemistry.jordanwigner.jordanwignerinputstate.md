---
uid: Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerInputState
title: Type défini par l’utilisateur JordanWignerInputState
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner
qsharp.name: JordanWignerInputState
qsharp.summary: Format of data passed from C# to Q# to represent preparation of the initial state The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 18adf28b4e99c825f14e9271791ded069e687901
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98837688"
---
# <a name="jordanwignerinputstate-user-defined-type"></a>Type défini par l’utilisateur JordanWignerInputState

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner](xref:Microsoft.Quantum.Chemistry.JordanWigner)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format des données passées de C# à Q # pour représenter la préparation de l’état initial la signification des données représentées est déterminée par l’algorithme qui les reçoit.

```qsharp

newtype JordanWignerInputState = ((Double, Double), Int[]);
```

