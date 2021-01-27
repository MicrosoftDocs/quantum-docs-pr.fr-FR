---
uid: Microsoft.Quantum.Canon.EmbedPauli
title: EmbedPauli fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: EmbedPauli
qsharp.summary: Given a single-qubit Pauli operator and the index of a qubit, returns a multi-qubit Pauli operator with the given single-qubit operator at that index and `PauliI` at every other index.
ms.openlocfilehash: 0e6a93e22ee495abcc44bdf522e7c72c0981308b
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840532"
---
# <a name="embedpauli-function"></a>EmbedPauli fonction)

Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)

Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)


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



## <a name="example"></a>Exemple

Pour obtenir le tableau `[PauliI, PauliI, PauliX, PauliI]` :

```qsharp
EmbedPauli(PauliX, 2, 3);
```