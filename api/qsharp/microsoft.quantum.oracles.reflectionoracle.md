---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Type défini par l’utilisateur ReflectionOracle
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 7bb0626e7cca9ae0b640699ea57f2e114bda2d06
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96226653"
---
# <a name="reflectionoracle-user-defined-type"></a>Type défini par l’utilisateur ReflectionOracle

Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Représente une réflexion Oracle.

Une réflexion Oracle, $O $, a des entrées :

- Phase $ \Phi $ par laquelle faire pivoter le sous-espace réfléchi.
- Registre qubit sur lequel effectuer la réflexion donnée.

```qsharp

newtype ReflectionOracle = (ApplyReflection : ((Double, Qubit[]) => Unit is Adj + Ctl));
```



## <a name="named-items"></a>Éléments nommés

### <a name="applyreflection--doublequbit--unit--is-adj--ctl"></a>ApplyReflection : ([double](xref:microsoft.quantum.lang-ref.double),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL



## <a name="remarks"></a>Notes

Ce $O Oracle = \boldone-(1-e ^ {i \Phi}) \ket{\Psi}\bra{\Psi} $ effectue une réflexion partielle par une phase $ \Phi $ à propos d’un seul état pur $ \ket{\Psi} $.