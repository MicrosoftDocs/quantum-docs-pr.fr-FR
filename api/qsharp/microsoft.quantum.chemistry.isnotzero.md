---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: 3c0f9c6695e8c9ec4a0953d5217c28c512ac7de1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703549"
---
# <a name="isnotzero-function"></a>IsNotZero fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Packages [](https://nuget.org/packages/)


Vérifie si un `Double` nombre n’est pas approximativement égal à zéro.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="number--double"></a>nombre : [double](xref:microsoft.quantum.lang-ref.double)

Nombre à vérifier



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

Retourne la valeur true si `number` a une valeur absolue supérieure à `1e-15` .