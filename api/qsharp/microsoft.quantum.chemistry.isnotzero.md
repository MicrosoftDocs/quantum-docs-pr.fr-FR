---
uid: Microsoft.Quantum.Chemistry.IsNotZero
title: IsNotZero fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry
qsharp.name: IsNotZero
qsharp.summary: Checks whether a `Double` number is not approximately zero.
ms.openlocfilehash: f80dbba6a51e62970e87c2782faba558340d2bd8
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96204060"
---
# <a name="isnotzero-function"></a>IsNotZero fonction)

Espace de noms : [Microsoft. Quantum. chimie](xref:Microsoft.Quantum.Chemistry)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Vérifie si un `Double` nombre n’est pas approximativement égal à zéro.

```qsharp
function IsNotZero (number : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="number--double"></a>nombre : [double](xref:microsoft.quantum.lang-ref.double)

Nombre à vérifier



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

Retourne la valeur true si `number` a une valeur absolue supérieure à `1e-15` .