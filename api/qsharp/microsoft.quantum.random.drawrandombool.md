---
uid: Microsoft.Quantum.Random.DrawRandomBool
title: Opération DrawRandomBool
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Random
qsharp.name: DrawRandomBool
qsharp.summary: Given a success probability, returns a single Bernoulli trial that is true with the given probability.
ms.openlocfilehash: 7c13f8305756421b8d07baf22ff87764efac0418
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98853690"
---
# <a name="drawrandombool-operation"></a>Opération DrawRandomBool

Espace de noms : [Microsoft. Quantum. Random](xref:Microsoft.Quantum.Random)

Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)


Pour une probabilité de réussite donnée, retourne une seule version d’essai de Bernoulli qui est vraie avec la probabilité donnée.

```qsharp
operation DrawRandomBool (successProbability : Double) : Bool
```


## <a name="input"></a>Entrée

### <a name="successprobability--double"></a>successProbability : [double](xref:microsoft.quantum.lang-ref.double)

Probabilité avec laquelle `true` doit être retourné.



## <a name="output--bool"></a>Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)

`true` avec la probabilité `successProbability` et `false` avec la probabilité `1.0 - successProbability` .

## <a name="example"></a>Exemple

Les exemples d’extraits de code Q # suivants retournent à partir d’une pièce de monnaie biaisée :

```qsharp
let flips = DrawMany(DrawRandomBool, 10, 0.6);
```