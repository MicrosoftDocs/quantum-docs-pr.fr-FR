---
uid: Microsoft.Quantum.Simulation.Unitary
title: Type défini par l’utilisateur unitaire
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: Unitary
qsharp.summary: Represents evolution under a unitary operator.
ms.openlocfilehash: d2bba42e80132d0879f42922f28ad50bef54edf3
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709221"
---
# <a name="unitary-user-defined-type"></a>Type défini par l’utilisateur unitaire

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Packages [](https://nuget.org/packages/)


Représente l’évolution sous un opérateur unitaire.

```qsharp

newtype Unitary = ((Qubit[] => Unit is Adj + Ctl));
```

