---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: 0a9a19685f0511c44942df7d0bc8d257ad6b18c6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98840499"
---
# <a name="graycode-function"></a><span data-ttu-id="adc9d-102">GrayCode fonction)</span><span class="sxs-lookup"><span data-stu-id="adc9d-102">GrayCode function</span></span>

<span data-ttu-id="adc9d-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="adc9d-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="adc9d-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="adc9d-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="adc9d-105">Crée des séquences de code en grisé</span><span class="sxs-lookup"><span data-stu-id="adc9d-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="adc9d-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="adc9d-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="adc9d-107">n : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="adc9d-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="adc9d-108">Nombre de bits</span><span class="sxs-lookup"><span data-stu-id="adc9d-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="adc9d-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="adc9d-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="adc9d-110">Tableau de tuples.</span><span class="sxs-lookup"><span data-stu-id="adc9d-110">Array of tuples.</span></span> <span data-ttu-id="adc9d-111">La première valeur dans le tuple est la valeur dans la séquence de GrayCode la seconde valeur dans le tuple est position à changer dans la valeur actuelle pour en afficher une suivante.</span><span class="sxs-lookup"><span data-stu-id="adc9d-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>

## <a name="example"></a><span data-ttu-id="adc9d-112">Exemple</span><span class="sxs-lookup"><span data-stu-id="adc9d-112">Example</span></span>

```qsharp
GrayCode(2); // [(0, 0),(1, 1),(3, 0),(2, 1)]
```