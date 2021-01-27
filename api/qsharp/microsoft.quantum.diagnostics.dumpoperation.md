---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Opération DumpOperation
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: cde188806506c586c4c77a7f9b2b43ad0e10ef1b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98829279"
---
# <a name="dumpoperation-operation"></a>Opération DumpOperation

Espace de noms : [Microsoft. Quantum. Diagnostics](xref:Microsoft.Quantum.Diagnostics)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Pour une opération donnée, affiche des diagnostics sur l’opération qui sont rendues disponibles par la cible d’exécution actuelle.

```qsharp
operation DumpOperation (nQubits : Int, op : (Qubit[] => Unit is Adj)) : Unit
```


## <a name="input"></a>Entrée

### <a name="nqubits--int"></a>nQubits : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de qubits sur lequel l’opération donnée agit.


### <a name="op--qubit--unit--is-adj"></a>OP : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Opération à diagnostiquer.



## <a name="output--unit"></a>Sortie : [unité](xref:microsoft.quantum.lang-ref.unit)



## <a name="example"></a>Exemple

Lorsqu’il est exécuté sur la cible du simulateur Quantum, l’extrait de code suivant génère la sortie de la matrice $ $ \begin{Aligned} \left (\begin{Matrix} 1 & 0 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \end{Matrix}\right) \end{Aligned}.
$$

```qsharp
operation DumpCnot() : Unit {
    DumpOperation(2, ApplyToFirstTwoQubitsCA(CNOT, _));
}
```

## <a name="remarks"></a>Notes

L’appel de cette opération n’a aucun effet observable à partir de Q #. Les diagnostics précis qui s’affichent, le cas échéant, dépendent de la cible d’exécution actuelle et de l’environnement de l’éditeur.
Par exemple, lorsqu’il est utilisé sur le simulateur Quantum à état complet, une matrice d’unités utilisée pour représenter `op` est affichée.

Notez que, lorsqu’il est exécuté sur des simulateurs qui reconnaissent une ambiguïté de phase globale (par exemple, le simulateur d’état complet), les représentations retournées peuvent varier jusqu’à une phase globale.

De même, le classement des représentations de matrices de lignes et de colonnes peut varier selon les conventions utilisées par chaque simulateur qui prend en charge cette opération.