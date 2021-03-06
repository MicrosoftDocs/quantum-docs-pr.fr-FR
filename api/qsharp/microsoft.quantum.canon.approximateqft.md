---
uid: Microsoft.Quantum.Canon.ApproximateQFT
title: Opération ApproximateQFT
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: ApproximateQFT
qsharp.summary: Apply the Approximate Quantum Fourier Transform (AQFT) to a quantum register.
ms.openlocfilehash: 31fd87c0f61292142c7493cc29cad1082a9a2d67
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98850320"
---
# <a name="approximateqft-operation"></a>Opération ApproximateQFT

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Appliquez la transformation de Fourier quantique approximative (AQFT) à un registre Quantum.

```qsharp
operation ApproximateQFT (a : Int, qs : Microsoft.Quantum.Arithmetic.BigEndian) : Unit is Adj + Ctl
```


## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

paramètre de approximation qui détermine à quel niveau les rotations Z contrôlées qui se produisent dans le circuit QFT sont nettoyées.

Le paramètre approximatif a détermine le niveau de nettoyage des rotations Z, c’est-à-dire un ∈ {0.. n} et toutes les rotations de Z 2π/2k où k>a sont supprimés du circuit QFT. Il est connu que, pour k >= log ₂ (n) + Journal ₂ (1/ε) + 3, une liaison peut être liée | | QFT-AQFT | |<ε.


### <a name="qs--bigendian"></a>QS : [bigEndian](xref:Microsoft.Quantum.Arithmetic.BigEndian)

Registre quantique de n qubits auquel la transformation de Fourier quantique approximative est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

AQFT requiert des portes de rotation Z de la forme 2π/2k et des portes Hadarmard.

L’entrée et la sortie sont supposées être encodées en encodage Big endian.

## <a name="references"></a>Références

- [*M. Roetteler, Th. Beth*, Appl. algèbre eng. commun. Terminé. 19 (3) : 177-193 (2008)](http://doi.org/10.1007/s00200-008-0072-2)
- [*D. Coppersmith* arXiv : quant-pH/0201067v1](https://arxiv.org/abs/quant-ph/0201067)