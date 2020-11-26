---
uid: Microsoft.Quantum.Diagnostics._assertEqualOnBasisVector
title: opération de _assertEqualOnBasisVector
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: _assertEqualOnBasisVector
qsharp.summary: Checks if the result of applying two operations `givenU` and `expectedU` to a basis state is the same. The basis state is described by `basis` parameter. See <xref:microsoft.quantum.extensions.fliptobasis> function for more details on this description.
ms.openlocfilehash: d8f2195f75de49918032053dc8d1fa4fb4eba840
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96213767"
---
# <a name="_assertequalonbasisvector-operation"></a>opération de _assertEqualOnBasisVector

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


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


### <a name="expectedu--qubit--unit--is-adj"></a>expected : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération de référence sur $n $ qubits à laquelle l’donnée doit être comparée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)

