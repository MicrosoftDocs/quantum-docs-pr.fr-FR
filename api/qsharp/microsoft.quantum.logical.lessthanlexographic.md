---
uid: Microsoft.Quantum.Logical.LessThanLexographic
title: LessThanLexographic fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Logical
qsharp.name: LessThanLexographic
qsharp.summary: Used to implement `LexographicComparison`.
ms.openlocfilehash: 716f58b747e9f58c338670271bb2e7aed96fe98c
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98815641"
---
# <a name="lessthanlexographic-function"></a><span data-ttu-id="3c82e-102">LessThanLexographic fonction)</span><span class="sxs-lookup"><span data-stu-id="3c82e-102">LessThanLexographic function</span></span>

<span data-ttu-id="3c82e-103">Espace de noms : [Microsoft. Quantum. Logical](xref:Microsoft.Quantum.Logical)</span><span class="sxs-lookup"><span data-stu-id="3c82e-103">Namespace: [Microsoft.Quantum.Logical](xref:Microsoft.Quantum.Logical)</span></span>

<span data-ttu-id="3c82e-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="3c82e-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="3c82e-105">Utilisé pour implémenter `LexographicComparison` .</span><span class="sxs-lookup"><span data-stu-id="3c82e-105">Used to implement `LexographicComparison`.</span></span>

```qsharp
function LessThanLexographic<'T> (comparison : (('T, 'T) -> Bool), left : 'T[], right : 'T[]) : Bool
```


## <a name="input"></a><span data-ttu-id="3c82e-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="3c82e-106">Input</span></span>

### <a name="comparison--tt---bool"></a><span data-ttu-id="3c82e-107">Comparaison : (t, t)-> [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3c82e-107">comparison : ('T,'T) -> [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>




### <a name="left--t"></a><span data-ttu-id="3c82e-108">gauche : 't []</span><span class="sxs-lookup"><span data-stu-id="3c82e-108">left : 'T[]</span></span>




### <a name="right--t"></a><span data-ttu-id="3c82e-109">Right : 't []</span><span class="sxs-lookup"><span data-stu-id="3c82e-109">right : 'T[]</span></span>





## <a name="output--bool"></a><span data-ttu-id="3c82e-110">Sortie : [bool](xref:microsoft.quantum.lang-ref.bool)</span><span class="sxs-lookup"><span data-stu-id="3c82e-110">Output : [Bool](xref:microsoft.quantum.lang-ref.bool)</span></span>



## <a name="type-parameters"></a><span data-ttu-id="3c82e-111">Paramètres de type</span><span class="sxs-lookup"><span data-stu-id="3c82e-111">Type Parameters</span></span>

### <a name="t"></a><span data-ttu-id="3c82e-112">Peut</span><span class="sxs-lookup"><span data-stu-id="3c82e-112">'T</span></span>

