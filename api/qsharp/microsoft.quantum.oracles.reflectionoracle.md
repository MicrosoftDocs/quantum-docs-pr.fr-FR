---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Type défini par l’utilisateur ReflectionOracle
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 8e35e7e508ea7e0c30ea2a70633f71a6c87d4be1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708741"
---
# <a name="reflectionoracle-user-defined-type"></a>Type défini par l’utilisateur ReflectionOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Packages [](https://nuget.org/packages/)


Représente une réflexion Oracle.

Une réflexion Oracle, $O $, a des entrées :

- Phase $ \Phi $ par laquelle faire pivoter le sous-espace réfléchi.
- Registre qubit sur lequel effectuer la réflexion donnée.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Éléments nommés

### <a name="applyreflection--doublequbit--unit-adj--ctl"></a>ApplyReflection : ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => la touche d' [unité](xref:microsoft.quantum.lang-ref.unit) + CTL



## <a name="remarks"></a>Notes

Ce $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\Psi}\bra{\Psi} $ effectue une réflexion partielle par une phase $ \Phi $ à propos d’un seul état pur $ \ket{\Psi} $.