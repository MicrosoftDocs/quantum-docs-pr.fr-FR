---
uid: Microsoft.Quantum.MachineLearning.InputEncoder
title: InputEncoder fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: InputEncoder
qsharp.summary: Given a set of coefficients and a tolerance, returns a state preparation operation that prepares each coefficient as the corresponding amplitude of a computational basis state.
ms.openlocfilehash: 771cf01866498f4662864939e6946526c2b5827a
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92701374"
---
# <a name="inputencoder-function"></a>InputEncoder fonction)

Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)

Packages [](https://nuget.org/packages/)


À partir d’un ensemble de coefficients et d’une tolérance, retourne une opération de préparation de l’État qui prépare chaque coefficient comme amplitude correspondante d’un état de base de calcul.

```qsharp
function InputEncoder (coefficients : Double[]) : Microsoft.Quantum.MachineLearning.StateGenerator
```


## <a name="input"></a>Entrée

### <a name="coefficients--double"></a>coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]

Coefficients à encoder dans un état d’entrée.



## <a name="output--stategenerator"></a>Sortie : [StateGenerator](xref:Microsoft.Quantum.MachineLearning.StateGenerator)

Opération de préparation de l’État qui prépare les coefficients donnés comme un état d’entrée sur un registre donné.