---
uid: Microsoft.Quantum.Diagnostics.AssertQubitWithinTolerance
title: Opération AssertQubitWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitWithinTolerance
qsharp.summary: Asserts that the qubit `q` is in the expected eigenstate of the Pauli Z operator up to a given tolerance.
ms.openlocfilehash: 3fe4aa739c5e15199401aecb76ef551e52f6dcff
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702715"
---
# <a name="assertqubitwithintolerance-operation"></a>Opération AssertQubitWithinTolerance

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare que qubit `q` se trouve dans le eigenstate attendu de l’opérateur Z Pauli jusqu’à une tolérance donnée.

```qsharp
operation AssertQubitWithinTolerance (expected : Result, q : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Entrée

### <a name="expected--__invalidresult__"></a>ATTENDU : __non <Result> valide__

Dans quel état le qubit doit être dans : `Zero` ou `One` .


### <a name="q--qubit"></a>q : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit dont l’État est déclaré.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance sur la probabilité d’une mesure de la qubit qui retourne le résultat attendu.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

<xref:microsoft.quantum.diagnostics.assertqubitisinstatewithintolerance> permet d’déclarer des États qubit arbitraires plutôt que $Z $ eigenstates.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Diagnostics. AssertQubitIsInStateWithinTolerance](xref:Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance)