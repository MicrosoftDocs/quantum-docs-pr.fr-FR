---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206882"
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