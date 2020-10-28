---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: 8f5a2319b5839d0d9e47972389330dc16dffcaf0
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92703072"
---
# <a name="expandedcoefficients-function"></a>ExpandedCoefficients fonction)

Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)

Packages [](https://nuget.org/packages/)


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