---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704166"
---
# <a name="graycode-function"></a>GrayCode fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


Crée des séquences de code en grisé

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a>Entrée

### <a name="n--int"></a>n : [entier](xref:microsoft.quantum.lang-ref.int)

Nombre de bits



## <a name="output--intint"></a>Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []

Tableau de tuples. La première valeur dans le tuple est la valeur dans la séquence de GrayCode la seconde valeur dans le tuple est position à changer dans la valeur actuelle pour en afficher une suivante.