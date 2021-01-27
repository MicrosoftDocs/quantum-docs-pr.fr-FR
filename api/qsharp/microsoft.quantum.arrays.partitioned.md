---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Fonction partitionnée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: 43d99a0e33a813e4af23a3890ace808e91c1049c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98845539"
---
# <a name="partitioned-function"></a>Fonction partitionnée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Fractionne un tableau en plusieurs parties.

```qsharp
function Partitioned<'T> (nElements : Int[], arr : 'T[]) : 'T[][]
```


## <a name="input"></a>Entrée

### <a name="nelements--int"></a>nElements : [int](xref:microsoft.quantum.lang-ref.int)[]

Nombre d’éléments dans chaque partie d’un tableau


### <a name="arr--t"></a>ARR : 't []

Tableau d’entrée à fractionner.



## <a name="output--t"></a>Sortie : 't [] []

Plusieurs tableaux dans lesquels le premier tableau est le premier `nElements[0]` `arr` et le deuxième tableau sont le suivant, `nElements[1]` `arr` etc. Le dernier tableau contiendra tous les éléments restants.

## <a name="type-parameters"></a>Paramètres de type

### <a name="t"></a>Peut



## <a name="example"></a>Exemple

```qsharp
// The following returns [[1, 5], [3], [7]];
let split = Partitioned([2,1], [1,5,3,7]);
```