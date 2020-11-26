---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Opération AssertPhase
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 9130d6c735d90abbc51989ef4a68a8eff8b41371
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202258"
---
# <a name="assertphase-operation"></a>Opération AssertPhase

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Déclare que la phase d’un état de superposition égal a la valeur attendue.

```qsharp
operation AssertPhase (expected : Double, qubit : Qubit, tolerance : Double) : Unit
```


## <a name="description"></a>Description

Cette opération déclare que la phase $ \Phi $ d’un État Quantum qui peut être exprimée sous la forme $ \frac{e ^ {i t}} {\sqrt {2} } (e ^ {i\phi} \ Ket {0} + e ^ {-i\phi} \ Ket {1} ) $ pour un réel réel $t $ a la valeur attendue.

## <a name="input"></a>Entrée

### <a name="expected--double"></a>ATTENDU : [double](xref:microsoft.quantum.lang-ref.double)

La valeur attendue de $ \Phi \Dans (-\pi, \pi] $.


### <a name="qubit--qubit"></a>qubit : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit qui stocke l’État attendu.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance absolue sur la différence entre réel et attendu.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

