---
uid: Microsoft.Quantum.Synthesis.ApplyTransposition
title: Opération ApplyTransposition
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: ApplyTransposition
qsharp.summary: ''
ms.openlocfilehash: 1bd6f9580e09752f1de75927d6bb35417bb1ff21
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92709191"
---
# <a name="applytransposition-operation"></a>Opération ApplyTransposition

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Packages [](https://nuget.org/packages/)




```qsharp
operation ApplyTransposition (a : Int, b : Int, qubits : Microsoft.Quantum.Arithmetic.LittleEndian) : Unit
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

