---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: c78406aa4557834ac2bb40cf1847696d075e5135
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704187"
---
# <a name="embedpauli-function"></a>EmbedPauli fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Packages [](https://nuget.org/packages/)


À partir d’un opérateur Pauli qubit unique et de l’index d’un qubit, retourne un opérateur de Pauli à plusieurs qubit avec l’opérateur Single-qubit donné au niveau de cet index et `PauliI` à chaque autre index.

```qsharp
function EmbedPauli (pauli : Pauli, location : Int, n : Int) : Pauli[]
```


## <a name="input"></a>Entrée

### <a name="pauli--pauli"></a>Pauli : [Pauli](xref:microsoft.quantum.lang-ref.pauli)

Opérateur Pauli qubit unique à placer à l’emplacement donné.


### <a name="location--int"></a>emplacement : [int](xref:microsoft.quantum.lang-ref.int)

Index tel que `output[location] == pauli` , où `output` est la sortie de cette fonction.


### <a name="n--int"></a>n : [entier](xref:microsoft.quantum.lang-ref.int)

Longueur du tableau à retourner.



## <a name="output--pauli"></a>Sortie : [Pauli](xref:microsoft.quantum.lang-ref.pauli)[]

