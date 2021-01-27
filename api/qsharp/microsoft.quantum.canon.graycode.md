---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840499"
---
# <a name="graycode-function"></a>GrayCode fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Crée des séquences de code en grisé

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Entrée

### <a name="n--int"></a>n : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de bits



## <a name="output--intint"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tableau de tuples. La première valeur dans le tuple est la valeur dans la séquence de GrayCode la seconde valeur dans le tuple est position à changer dans la valeur actuelle pour en afficher une suivante.

## <a name="example"></a>Exemple

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```