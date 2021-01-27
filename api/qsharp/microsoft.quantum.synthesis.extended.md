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
# <a name="extended-function"></a><span data-ttu-id="87fd2-102">Fonction étendue</span><span class="sxs-lookup"><span data-stu-id="87fd2-102">Extended function</span></span>

<span data-ttu-id="87fd2-103">Espace de noms : [Microsoft. Quantum. Synthesis](xref:Microsoft.Quantum.Synthesis)</span><span class="sxs-lookup"><span data-stu-id="87fd2-103">Namespace: [Microsoft.Quantum.Synthesis](xref:Microsoft.Quantum.Synthesis)</span></span>

<span data-ttu-id="87fd2-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="87fd2-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="87fd2-105">Étend un spectre par les coefficients inversés</span><span class="sxs-lookup"><span data-stu-id="87fd2-105">Extends a spectrum by inverted coefficients</span></span>

```qsharp
function Extended (spectrum : Int[]) : Int[]
```


## <a name="input"></a><span data-ttu-id="87fd2-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="87fd2-106">Input</span></span>

### <a name="spectrum--int"></a><span data-ttu-id="87fd2-107">spectre : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="87fd2-107">spectrum : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="87fd2-108">Coefficients spectraux</span><span class="sxs-lookup"><span data-stu-id="87fd2-108">Spectral coefficients</span></span>



## <a name="output--int"></a><span data-ttu-id="87fd2-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)[]</span><span class="sxs-lookup"><span data-stu-id="87fd2-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)[]</span></span>

<span data-ttu-id="87fd2-110">Coefficients suivis d’une copie inversée</span><span class="sxs-lookup"><span data-stu-id="87fd2-110">Coefficients followed by inverted copy</span></span>

## <a name="example"></a><span data-ttu-id="87fd2-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="87fd2-111">Example</span></span>

```qsharp
Extended([2, 2, 2, -2]); // [2, 2, 2, -2, -2, -2, -2, 2]
```