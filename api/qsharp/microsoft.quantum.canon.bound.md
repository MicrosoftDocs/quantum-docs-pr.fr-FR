---
uid: Microsoft.Quantum.Canon.Bound
title: Fonction Bound
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: Bound
qsharp.summary: Given an array of operations acting on a single input, produces a new operation that performs each given operation in sequence.
ms.openlocfilehash: c12ce37054ddde1b98778888e90916c6e4725814
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96207596"
---
# <a name="bound-function"></a>Fonction Bound

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


À partir d’un tableau d’opérations agissant sur une seule entrée, produit une nouvelle opération qui effectue chaque opération donnée dans l’ordre.

```qsharp
function Bound<'T> (operations : ('T => Unit)[]) : ('T => Unit)
```


## <a name="input"></a>Entrée

### <a name="operations--t--unit-"></a>opérations : 't => [unité](xref:microsoft.quantum.lang-ref.unit) []

Séquence d’opérations à effectuer sur une entrée donnée.



## <a name="output--t--unit"></a>Sortie : 't => [unité](xref:microsoft.quantum.lang-ref.unit) 

Nouvelle opération qui effectue chaque opération donnée dans l’ordre de son entrée.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut

Cible sur laquelle les opérations du tableau agissent.

## <a name="see-also"></a>Voir aussi

- [Microsoft. Quantum. Canon. BoundC](xref:Microsoft.Quantum.Canon.BoundC)
- [Microsoft. Quantum. Canon. bounda](xref:Microsoft.Quantum.Canon.BoundA)
- [Microsoft. Quantum. Canon. BoundCA](xref:Microsoft.Quantum.Canon.BoundCA)