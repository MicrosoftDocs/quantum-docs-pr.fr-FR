---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: opération de _assertEqualOnBasisVector
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: 01b6d5aede102e47df86ea70d071d81eba1ade6f
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92702832"
---
# <a name="_assertequalonbasisvector-operation"></a>opération de _assertEqualOnBasisVector

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Packages [](https://nuget.org/packages/)


Vérifie si le résultat de l’application de deux opérations `givenU` et `expectedU` à un état de base est le même. L’état de base est décrit par le `basis` paramètre.
<xref:microsoft.quantum.extensions.fliptobasis>Pour plus d’informations sur cette description, consultez fonction.

```qsharp
operation _assertEqualOnBasisVector (basis : Int[], givenU : (Qubit[] => Unit), expectedU : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="basis--int"></a>base : [int](xref:microsoft.quantum.lang-ref.int)[]

État de base spécifié par un ID d’état de base à qubit unique (0 <= ID <= 3) pour chaque $n $ qubits.


### <a name="givenu--qubit--unit"></a>donné : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] = [unité](xref:microsoft.quantum.lang-ref.unit)> 

Opération sur $n $ qubits à vérifier.


### <a name="expectedu--qubit--unit-adj"></a>expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Opération de référence sur $n $ qubits à laquelle l’donnée doit être comparée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

