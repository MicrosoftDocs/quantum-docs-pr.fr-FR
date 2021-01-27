---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.ExpandedCoefficients
title: ExpandedCoefficients fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: ExpandedCoefficients
qsharp.summary: Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.
ms.openlocfilehash: b953fb8f5737956e8597cd90a7d6bfc0bafce4e3
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835618"
---
# <a name="expandedcoefficients-function"></a><span data-ttu-id="ab719-102">ExpandedCoefficients fonction)</span><span class="sxs-lookup"><span data-stu-id="ab719-102">ExpandedCoefficients function</span></span>

<span data-ttu-id="ab719-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="ab719-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="ab719-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="ab719-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="ab719-105">Développe la représentation compacte des coefficients de Jordan-Wigner afin d’obtenir un mappage un-à-un entre ces termes et Pauli.</span><span class="sxs-lookup"><span data-stu-id="ab719-105">Expands the compact representation of the Jordan-Wigner coefficients in order to obtain a one-to-one mapping between these and Pauli terms.</span></span>

```qsharp
function ExpandedCoefficients (coeff : Double[], termType : Int) : Double[]
```


## <a name="input"></a><span data-ttu-id="ab719-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="ab719-106">Input</span></span>

### <a name="coeff--double"></a><span data-ttu-id="ab719-107">Coeff : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ab719-107">coeff : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ab719-108">Tableau de coefficients, lus à partir de la structure de données Jordan-Wigner Hamilton.</span><span class="sxs-lookup"><span data-stu-id="ab719-108">An array of coefficients, as read from the Jordan-Wigner Hamiltonian data structure.</span></span>


### <a name="termtype--int"></a><span data-ttu-id="ab719-109">termType : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="ab719-109">termType : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="ab719-110">Type du terme Jordan-Wigner.</span><span class="sxs-lookup"><span data-stu-id="ab719-110">The type of the Jordan-Wigner term.</span></span>



## <a name="output--double"></a><span data-ttu-id="ab719-111">Sortie : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="ab719-111">Output : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="ab719-112">Tableaux étendus de coefficients, un par Pauli terme.</span><span class="sxs-lookup"><span data-stu-id="ab719-112">Expanded arrays of coefficients, one per Pauli term.</span></span>