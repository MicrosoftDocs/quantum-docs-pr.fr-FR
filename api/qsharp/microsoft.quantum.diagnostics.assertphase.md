---
uid: Microsoft.Quantum.Diagnostics.AssertPhase
title: Opération AssertPhase
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertPhase
qsharp.summary: Asserts that the phase of an equal superposition state has the expected value.
ms.openlocfilehash: 59fa0f2f68b4de271b972aef776ee5097fd5c201
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98830076"
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



## <a name="example"></a>Exemple

L’assertion suivante aboutit : `qubit` est dans l’État $ \ket{\Psi} = e ^ {i 0,5} \ sqrt {1/2} \ Ket {0} + e ^ {i 0.5} \ sqrt {1/2} \ Ket {1} $;

- `AssertPhase(0.0,qubit,10e-10);`

`qubit` est dans l’État $ \ket{\Psi} = e ^ {i 0,5} \ racine {1/2} \ Ket {0} + e ^ {-i 0,5} \ racine {1/2} \ Ket {1} $;

- `AssertPhase(0.5,qubit,10e-10);`

`qubit` est dans l’État $ \ket{\Psi} = e ^ {-i 2.2} \ racine {1/2} \ Ket {0} + e ^ {i 0,2} \ racine {1/2} \ Ket {1} $;

- `AssertPhase(-1.2,qubit,10e-10);`