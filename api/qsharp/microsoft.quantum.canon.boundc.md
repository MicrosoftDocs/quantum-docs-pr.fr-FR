---
uid: Microsoft.Quantum.Canon.BoundC
title: BoundC fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundC
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `C` indicates that all operations in the array are controllable.
ms.openlocfilehash: 04dca4ff317bf3cee053f7c3903112f4e05a3973
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704454"
---
# <a name="boundc-function"></a>BoundC fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.
Le modificateur `C` indique que toutes les opérations dans le tableau sont contrôlables.

```qsharp
function BoundC<'T> (operations : ('T => Unit is Ctl)[]) : ('T => Unit is Ctl)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit-ctl"></a>opérations : 't => CTL d' [unité](xref:microsoft.quantum.lang-ref.unit) []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit-ctl"></a>Sortie : 't => CTL de l' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)