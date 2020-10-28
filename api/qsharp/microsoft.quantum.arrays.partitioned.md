---
uid: Microsoft.Quantum.Arrays.Partitioned
title: Fonction partitionnée
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Arrays
qsharp.name: Partitioned
qsharp.summary: Splits an array into multiple parts.
ms.openlocfilehash: e3395afeda206e255a58175b57245f91c588d978
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92705846"
---
# <a name="partitioned-function"></a>Fonction partitionnée

Espace de noms : [Microsoft. Quantum. Arrays](xref:Microsoft.Quantum.Arrays)

Packages [](https://nuget.org/packages/)


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

