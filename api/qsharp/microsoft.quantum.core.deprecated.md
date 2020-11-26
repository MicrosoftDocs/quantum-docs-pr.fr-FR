---
uid: Microsoft.Quantum.Core.Deprecated
title: Type défini par l’utilisateur déconseillé
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: udt
qsharp.namespace: Microsoft.Quantum.Core
qsharp.name: Deprecated
qsharp.summary: Compiler-recognized attribute used to mark a type or callable as deprecated.
ms.openlocfilehash: 122cbc113a68cec107558d68a6fb145cf6bbd9db
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96224086"
---
# <a name="deprecated-user-defined-type"></a><span data-ttu-id="3e771-102">Type défini par l’utilisateur déconseillé</span><span class="sxs-lookup"><span data-stu-id="3e771-102">Deprecated user defined type</span></span>

<span data-ttu-id="3e771-103">Espace de noms : [Microsoft. Quantum. Core](xref:Microsoft.Quantum.Core)</span><span class="sxs-lookup"><span data-stu-id="3e771-103">Namespace: [Microsoft.Quantum.Core](xref:Microsoft.Quantum.Core)</span></span>

<span data-ttu-id="3e771-104">Package : [Microsoft. Quantum. QSharp. Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span><span class="sxs-lookup"><span data-stu-id="3e771-104">Package: [Microsoft.Quantum.QSharp.Core](https://nuget.org/packages/Microsoft.Quantum.QSharp.Core)</span></span>


<span data-ttu-id="3e771-105">Attribut reconnu par le compilateur utilisé pour marquer un type ou être appelé comme déconseillé.</span><span class="sxs-lookup"><span data-stu-id="3e771-105">Compiler-recognized attribute used to mark a type or callable as deprecated.</span></span>

```qsharp

@ Microsoft.Quantum.Core.Attribute()
newtype Deprecated = (NewName : String);
```



## <a name="named-items"></a><span data-ttu-id="3e771-106">Éléments nommés</span><span class="sxs-lookup"><span data-stu-id="3e771-106">Named Items</span></span>

### <a name="newname--string"></a><span data-ttu-id="3e771-107">NewName : [chaîne](xref:microsoft.quantum.lang-ref.string)</span><span class="sxs-lookup"><span data-stu-id="3e771-107">NewName : [String](xref:microsoft.quantum.lang-ref.string)</span></span>

<span data-ttu-id="3e771-108">Nom complet du type ou pouvant être appelé à utiliser à la place.</span><span class="sxs-lookup"><span data-stu-id="3e771-108">The full name of the type or callable to use instead.</span></span>
<span data-ttu-id="3e771-109">Est défini sur la chaîne vide si un type ou un appelable est déconseillé sans substitution.</span><span class="sxs-lookup"><span data-stu-id="3e771-109">Is set to the empty String if a type or callable has been deprecated without substitution.</span></span>