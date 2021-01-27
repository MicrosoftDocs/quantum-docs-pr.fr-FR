---
uid: Microsoft.Quantum.Canon.BoundA
title: Fonction liée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 3d0a5ba5d3d9c76289ed29e59a9c226358b83797
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844541"
---
# <a name="bounda-function"></a>Fonction liée

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.
Le modificateur `A` indique que toutes les opérations dans le tableau sont adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit--is-adj"></a>opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est ADJ []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit--is-adj"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est adj

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="example"></a>Exemple

Les éléments suivants sont équivalents :

```qsharp
let bound = BoundA([U, V]);
bound(x);
```

and

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)