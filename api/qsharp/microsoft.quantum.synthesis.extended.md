---
uid: Microsoft.Quantum.Synthesis.Extended
title: Fonction étendue
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Extended
qsharp.summary: Extends a spectrum by inverted coefficients
ms.openlocfilehash: 1855f3cab98c5fbf08c4505b90423df50cbec95b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855474"
---
# <a name="extended-function"></a>Fonction étendue

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Étend un spectre par les coefficients inversés

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a>Entrée

### <a name="spectrum--int"></a>spectre : [int](xref:microsoft.quantum.lang-ref.int)[]

Coefficients spectraux



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Coefficients suivis d’une copie inversée

## <a name="example"></a>Exemple

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```