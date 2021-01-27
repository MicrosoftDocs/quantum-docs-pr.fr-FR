---
uid: Microsoft.Quantum.Oracles.ReflectionOracle
title: Type défini par l’utilisateur ReflectionOracle
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: ReflectionOracle
qsharp.summary: >-
  Represents a reflection oracle.

  A reflection oracle, $O$, has inputs:

  - The phase $\phi$ by which to rotate the reflected subspace. - The qubit register on which to perform the given reflection.
ms.openlocfilehash: 1ef07126596b70d2c5574430656009116c34d2bc
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854486"
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