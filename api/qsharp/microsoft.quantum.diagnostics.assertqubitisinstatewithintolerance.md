---
uid: Microsoft.Quantum.Diagnostics.AssertQubitIsInStateWithinTolerance
title: Opération AssertQubitIsInStateWithinTolerance
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: AssertQubitIsInStateWithinTolerance
qsharp.summary: >-
  Asserts that a qubit in the expected state.

  `expected` represents a complex vector, $\ket{\psi} = \begin{bmatrix}a & b\end{bmatrix}^{\mathrm{T}}$. The first element of the tuples representing each of $a$, $b$ is the real part of the complex number, while the second one is the imaginary part. The last argument defines the tolerance with which assertion is made.
ms.openlocfilehash: 5d34bdac53870326dacb5a11c27c857793c3f420
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702739"
---
# <a name="assertqubitisinstatewithintolerance-operation"></a>Opération AssertQubitIsInStateWithinTolerance

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Déclare qu’un qubit dans l’État attendu.

`expected` représente un vecteur complexe, $ \ket{\Psi} = \begin{bmatrix}a & b\end {bmatrix} ^ {\mathrm{T}} $.
Le premier élément des tuples représentant chacun des $a $, $b $ est la partie réelle du nombre complexe, tandis que le deuxième est la partie imaginaire.
Le dernier argument définit la tolérance avec laquelle l’assertion est faite.

```qsharp
operation AssertQubitIsInStateWithinTolerance (expected : (Microsoft.Quantum.Math.Complex, Microsoft.Quantum.Math.Complex), register : Qubit, tolerance : Double) : Unit
```


## <a name="input"></a>Entrée

### <a name="expected--complexcomplex"></a>ATTENDU : ([complexe](xref:Microsoft.Quantum.Math.Complex),[complexe](xref:Microsoft.Quantum.Math.Complex))

Amplitudes complexes attendues pour $ \ket {0} $ et $ \ket {1} $, respectivement.


### <a name="register--qubit"></a>inscription : [qubit](xref:microsoft.quantum.lang-ref.qubit)

Qubit dont l’État doit être déclaré. Notez que ce qubit est supposé être séparable des autres qubits alloués et non pris en compte.


### <a name="tolerance--double"></a>tolérance : [double](xref:microsoft.quantum.lang-ref.double)

Tolérance additive par laquelle les amplitudes réelles sont autorisées à s’écarter de la valeur attendue.
Pour plus d’informations, consultez les remarques ci-dessous.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="remarks"></a>Notes

Le code Mathematica suivant peut être utilisé pour vérifier les expressions pour mi, MX, My, MZ :

```mathematica
{Id, X, Y, Z} = Table[PauliMatrix[k], {k, 0, 3}];
st = {{ reA + I imA }, { reB + I imB} };
M = st . ConjugateTranspose[st];
mx = Tr[M.X] // ComplexExpand;
my = Tr[M.Y] // ComplexExpand;
mz = Tr[M.Z] // ComplexExpand;
mi = Tr[M.Id] // ComplexExpand;
2 m == Id mi + X mx + Z mz + Y my // ComplexExpand // Simplify
```

La tolérance est le $L de la \_ distance {\infty} $ entre le vecteur réel à 3 Dimensions (x ₂, x ₃, x ₄) défini par $ \langle\psi | \psi\rangle = x \_ 1 I + x \_ 2 x + x \_ 3 Y + x \_ 4 Z $ et Real vector (y ₂, y ₃, y ₄) défini par p = y ₁ I + y ₂ x + y ₃ y + y ₄ Z où p est la matrice de densité correspondant à l’état du Registre.
Cela est vrai uniquement en supposant que TR (p) et TR (| ψ ⟩ ⟨ ψ |) sont tous deux 1 (par exemple, x ₁ = 1/2, y ₁ = 1/2).
Si ce n’est pas le cas, la fonction déclare que la distance l ∞ entre (x ₂-x ₁, x ₃-x ₁, x ₄-x ₁, x ₄ + x ₁) et (y ₂-y ₁, y ₃-y ₁, y ₄-y ₁, y ₄ + y ₁) est inférieure au paramètre Tolerance.