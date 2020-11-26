---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 02e9b6a9676cdd1996d3a2413b2a6383e3a4e90e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207579"
---
# <a name="boundc-function"></a>BoundC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.
Le modificateur `C` indique que toutes les opérations dans le tableau sont contrôlables.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit--is-ctl"></a>opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit--is-ctl"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit)  est CTL

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)