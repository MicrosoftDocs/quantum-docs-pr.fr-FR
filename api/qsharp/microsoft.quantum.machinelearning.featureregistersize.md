---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize fonction)
ms.date: 11/25/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: bc5d5a23cfb431f9506b15bc404ab6955d1c2a35
ms.sourcegitcommit: a87c1aa8e7453360025e47ba614f25b02ea84ec3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/26/2020
ms.locfileid: "96196410"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="6d224-102">FeatureRegisterSize fonction)</span><span class="sxs-lookup"><span data-stu-id="6d224-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="6d224-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6d224-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="6d224-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="6d224-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="6d224-105">Retourne le nombre de qubits nécessaires pour encoder un vecteur de fonctionnalité particulier.</span><span class="sxs-lookup"><span data-stu-id="6d224-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="6d224-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="6d224-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="6d224-107">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="6d224-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="6d224-108">Exemple de vecteur de fonctionnalité à encoder dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="6d224-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="6d224-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6d224-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6d224-110">Taille requise pour encoder `sample` dans un registre qubit, exprimée sous la forme d’un nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="6d224-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>