---
uid: Microsoft.Quantum.Canon.BoundCA
title: BoundCA fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundCA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `CA` indicates that all operations in the array are adjointable and controllable.
ms.openlocfilehash: 391183829a3cc8b7aa8051767dcfc6bec9638223
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98844527"
---
# <a name="boundca-function"></a>BoundCA fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.
Le modificateur `CA` indique que toutes les opérations dans le tableau sont adjointable et contrôlable.

```qsharp
function BoundCA<'T> (operations : ('T => Unit is Adj + Ctl)[]) : ('T => Unit is Adj + Ctl)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit--is-adj--ctl"></a>opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit--is-adj--ctl"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="example"></a>Exemple

Les éléments suivants sont équivalents :

```qsharp
let bound = BoundCA([U, V]);
bound(x);
```

and

```qsharp
U(x); V(x);
```

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)