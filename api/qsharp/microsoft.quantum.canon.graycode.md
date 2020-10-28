---
uid: Microsoft.Quantum.Canon.GrayCode
title: GrayCode fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Canon
qsharp.name: GrayCode
qsharp.summary: Creates Gray code sequences
ms.openlocfilehash: fc673ae21a952788b5beb74c1bad94ee9fe54480
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92704166"
---
# <a name="graycode-function"></a><span data-ttu-id="d2474-102">GrayCode fonction)</span><span class="sxs-lookup"><span data-stu-id="d2474-102">GrayCode function</span></span>

<span data-ttu-id="d2474-103">Espace de noms : [Microsoft. Quantum. Canon](xref:Microsoft.Quantum.Canon)</span><span class="sxs-lookup"><span data-stu-id="d2474-103">Namespace: [Microsoft.Quantum.Canon](xref:Microsoft.Quantum.Canon)</span></span>

<span data-ttu-id="d2474-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="d2474-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="d2474-105">Crée des séquences de code en grisé</span><span class="sxs-lookup"><span data-stu-id="d2474-105">Creates Gray code sequences</span></span>

```qsharp
function GrayCode (n : Int) : (Int, Int)[]
```


## <a name="input"></a><span data-ttu-id="d2474-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="d2474-106">Input</span></span>

### <a name="n--int"></a><span data-ttu-id="d2474-107">n : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="d2474-107">n : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="d2474-108">Nombre de bits</span><span class="sxs-lookup"><span data-stu-id="d2474-108">Number of bits</span></span>



## <a name="output--intint"></a><span data-ttu-id="d2474-109">Sortie : ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)) []</span><span class="sxs-lookup"><span data-stu-id="d2474-109">Output : ([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))[]</span></span>

<span data-ttu-id="d2474-110">Tableau de tuples.</span><span class="sxs-lookup"><span data-stu-id="d2474-110">Array of tuples.</span></span> <span data-ttu-id="d2474-111">La première valeur dans le tuple est la valeur dans la séquence de GrayCode la seconde valeur dans le tuple est position à changer dans la valeur actuelle pour en afficher une suivante.</span><span class="sxs-lookup"><span data-stu-id="d2474-111">First value in tuple is value in GrayCode sequence Second value in tuple is position to change in current value to get next one.</span></span>