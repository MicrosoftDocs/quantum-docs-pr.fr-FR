---
uid: Microsoft.Quantum.Diagnostics.DumpOperation
title: Opération DumpOperation
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Diagnostics
qsharp.name: DumpOperation
qsharp.summary: Given an operation, displays diagnostics about the operation that are made available by the current execution target.
ms.openlocfilehash: b0e07173ddbeb8a96d4a85928258b6e30deb394d
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96202054"
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



## <a name="remarks"></a>Notes

L’appel de cette opération n’a aucun effet observable à partir de Q #. Les diagnostics précis qui s’affichent, le cas échéant, dépendent de la cible d’exécution actuelle et de l’environnement de l’éditeur.
Par exemple, lorsqu’il est utilisé sur le simulateur Quantum à état complet, une matrice d’unités utilisée pour représenter `op` est affichée.

Notez que, lorsqu’il est exécuté sur des simulateurs qui reconnaissent une ambiguïté de phase globale (par exemple, le simulateur d’état complet), les représentations retournées peuvent varier jusqu’à une phase globale.

De même, le classement des représentations de matrices de lignes et de colonnes peut varier selon les conventions utilisées par chaque simulateur qui prend en charge cette opération.