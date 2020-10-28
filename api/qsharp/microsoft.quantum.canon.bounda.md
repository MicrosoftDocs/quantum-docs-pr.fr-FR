---
uid: Microsoft.Quantum.Canon.BoundA
title: Fonction liée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: BoundA
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence. The modifier `A` indicates that all operations in the array are adjointable.
ms.openlocfilehash: 40c112d0572dc4eebfc284c9ef29f43706e20c64
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704467"
---
# <a name="bounda-function"></a>Fonction liée

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.
Le modificateur `A` indique que toutes les opérations dans le tableau sont adjointable.

```qsharp
function BoundA<'T> (operations : ('T => Unit is Adj)[]) : ('T => Unit is Adj)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit-adj"></a>opérations : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit) []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit-adj"></a>Sortie : 't => ajustement d' [unité](xref:microsoft.quantum.lang-ref.unit)

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. Bound](xref:Microsoft.Quantum.Canon.Bound)