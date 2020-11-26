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
# <a name="expandedcoefficients-function"></a><span data-ttu-id="2130d-102">ExpandedCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="2130d-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="2130d-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="2130d-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="2130d-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="2130d-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="2130d-105">Développe la représentation compacte des coefficients de Jordan-Wigner afin d’obtenir un mappage un-à-un entre ces termes et Pauli.</span><span class="sxs-lookup"><span data-stu-id="2130d-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="2130d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2130d-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="2130d-107">Coeff : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2130d-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2130d-108">Tableau de coefficients, lus à partir de la structure de données Jordan-Wigner Hamilton.</span><span class="sxs-lookup"><span data-stu-id="2130d-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="2130d-109">termType : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2130d-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2130d-110">Type du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="2130d-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="2130d-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2130d-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2130d-112">Tableaux étendus de coefficients, un par Pauli terme.</span><span class="sxs-lookup"><span data-stu-id="2130d-112">Expanded arrays of coefficients, one per Pauli term.</span></span>