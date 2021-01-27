---
uid: Microsoft.Quantum.Simulation.QuantumWalkByQubitization
title: QuantumWalkByQubitization fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Simulation
qsharp.name: QuantumWalkByQubitization
qsharp.summary: Converts a block-encoding reflection into a quantum walk.
ms.openlocfilehash: 8ffb6eb77a3f910d3064c4a3c90215d5d9a694aa
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98851057"
---
# <a name="quantumwalkbyqubitization-function"></a>QuantumWalkByQubitization fonction)

Espace de noms : [Microsoft. Quantum. simulation](xref:Microsoft.Quantum.Simulation)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Convertit une réflexion d’encodage de bloc en un parcours quantique.

```qsharp
function QuantumWalkByQubitization (blockEncoding : Microsoft.Quantum.Simulation.BlockEncodingReflection) : ((Qubit[], Qubit[]) => Unit is Adj + Ctl)
```


## <a name="description"></a>Description

À partir d’un `BlockEncodingReflection` représenté par un $U unitaire $ qui encode un opérateur $H $ d’intérêt, le convertit en un parcours quantique $W $ contenant le spectre de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="input"></a>Entrée

### <a name="blockencoding--blockencodingreflection"></a>blockEncoding : [BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)

`BlockEncodingReflection`$U unitaire $ à convertir en un parcours quantique.



## <a name="output--qubitqubit--unit--is-adj--ctl"></a>Sortie : ([qubit](xref:microsoft.quantum.lang-ref.qubit)[],[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Un parcours quantique $W $ agissant conjointement sur les registres `a` et `s` qui encodent en bloc $H $ et contient le spectre de $ \pm e ^ {\pm i\sin ^ {-1} (H)} $.

## <a name="references"></a>Références

- Simulation de la Qubitization Guang Hao Low, Isaac L. Chuang https://arxiv.org/abs/1610.06546

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. simulation. BlockEncoding](xref:Microsoft.Quantum.Simulation.BlockEncoding)
- [Microsoft. Quantum. simulation. BlockEncodingReflection](xref:Microsoft.Quantum.Simulation.BlockEncodingReflection)