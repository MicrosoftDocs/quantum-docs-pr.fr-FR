---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Opération ApplyTransposition
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 46cf8c2c891aa02b0d8a1397e6c2b7a4b8618048
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855577"
---
# <a name="applytransposition-operation"></a>Opération ApplyTransposition

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit is Adj + Ctl
```


## <a name="description"></a>Description

Cette opération permute l’amplitude au niveau de l’index `a` avec l’amplitude à `b` l’index dans le vecteur d’État donné de `register` longueur $n $.  Si est `a` égal `b` à, le vecteur d’État n’est pas modifié.

## <a name="input"></a>Entrée

### <a name="a--int"></a>r : [entier](xref:microsoft.quantum.lang-ref.int)

Premier index (doit être une valeur comprise entre 0 et $2 ^ n-$1)


### <a name="b--int"></a>b : [entier](xref:microsoft.quantum.lang-ref.int)

Second index (doit être une valeur comprise entre 0 et $2 ^ n-$1)


### <a name="qubits--littleendian"></a>qubits : [LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian)

Liste de $n $ qubits à laquelle la transposition est appliquée.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemple

Préparez une superposition uniforme de nombre États $ | 1 \ rangle $, $ | 2 \ rangle $ et $ | 3 \ rangle $ sur 2 qubits.

```qsharp
using (qubits = Qubit[2]) {
  let register = LittleEndian(qubits);
  PrepareUniformSuperposition(3, register);
  ApplyTransposition(0, 3, register);
}
```