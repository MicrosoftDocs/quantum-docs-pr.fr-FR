---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: b15586c57180b00064721afc990436320824cba2
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96206882"
---
# <a name="graycode-function"></a><span data-ttu-id="7894f-102">GrayCode fonction)</span><span class="sxs-lookup"><span data-stu-id="7894f-102">GrayCode function</span></span>

<span data-ttu-id="7894f-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="7894f-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="7894f-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="7894f-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="7894f-105">Crée des séquences de code en grisé</span><span class="sxs-lookup"><span data-stu-id="7894f-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="7894f-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="7894f-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="7894f-107">n : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="7894f-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="7894f-108">Nombre de bits</span><span class="sxs-lookup"><span data-stu-id="7894f-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="7894f-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="7894f-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="7894f-110">Tableau de tuples.</span><span class="sxs-lookup"><span data-stu-id="7894f-110">Array of tuples.</span></span> <span data-ttu-id="7894f-111">La première valeur dans le tuple est la valeur dans la séquence de GrayCode la seconde valeur dans le tuple est position à changer dans la valeur actuelle pour en afficher une suivante.</span><span class="sxs-lookup"><span data-stu-id="7894f-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>