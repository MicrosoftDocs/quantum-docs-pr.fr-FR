---
uid: Microsoft.Quantum.Chemistry.HTerm
title: Type défini par l’utilisateur HTerm
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: HTerm
qsharp.summary: Format of data passed from C# to Q# to represent a term of the Hamiltonian. The meaning of the data represented is determined by the algorithm that receives it.
ms.openlocfilehash: 744668a4fe96ee00fe2f7991f4e1f05eea19d417
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851786"
---
# <a name="hterm-user-defined-type"></a>Type défini par l’utilisateur HTerm

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Format des données passées de C# à Q # pour représenter un terme de la même façon.
La signification des données représentées est déterminée par l’algorithme qui la reçoit.

```qsharp

newtype HTerm = (Int[], Double[]);
```

