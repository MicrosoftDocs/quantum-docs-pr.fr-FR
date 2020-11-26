---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 92d7deb7010791e7de3d22ad4616b20110d5e84e
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96214379"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)


Développe la représentation compacte des coefficients de Jordan-Wigner afin d’obtenir un mappage un-à-un entre ces termes et Pauli.

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a>Entrée

### <a name="coeff--double"></a>Coeff : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableau de coefficients, lus à partir de la structure de données Jordan-Wigner Hamilton.


### <a name="termtype--int"></a>termType : [entier](xref:microsoft.quantum.lang-ref.int)

Type du terme Jordan-Wigner.



## <a name="output--double"></a>Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]

Tableaux étendus de coefficients, un par Pauli terme.