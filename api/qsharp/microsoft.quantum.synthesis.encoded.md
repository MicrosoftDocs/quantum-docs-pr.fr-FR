---
uid: Microsoft.Quantum.Synthesis.Encoded
title: Fonction encodée
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Synthesis
qsharp.name: Encoded
qsharp.summary: Encode truth table in {1,-1} coding
ms.openlocfilehash: 44f6b247e6bfab7b55c46146cb63f8b6d219955b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98855496"
---
# <a name="encoded-function"></a>Fonction encodée

Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


Coder la table de vérité en {1,-1} codage

```qsharp
function Encoded (table : Bool[]) : Int[]
```


## <a name="input"></a>Entrée

### <a name="table--bool"></a>table : [bool](xref:microsoft.quantum.lang-ref.bool)[]

Table de vérité en tant que tableau de valeurs de vérité



## <a name="output--int"></a>Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]

Table de vérité en tant que tableau d' {1,-1} entiers

## <a name="example"></a>Exemple

```qsharp
Encoded([false, false, false, true]); // [1, 1, 1, -1]
```