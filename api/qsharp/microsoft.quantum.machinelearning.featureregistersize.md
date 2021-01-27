---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 2754e901d74175c1841a38d795f5de02dabc9b8d
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98848442"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="2f311-102">FeatureRegisterSize fonction)</span><span class="sxs-lookup"><span data-stu-id="2f311-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="2f311-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2f311-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="2f311-104">Package : [Microsoft. Quantum. MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="2f311-104">Package: [Microsoft.Quantum.MachineLearning](https://nuget.org/packages/Microsoft.Quantum.MachineLearning)</span></span>


<span data-ttu-id="2f311-105">Retourne le nombre de qubits nécessaires pour encoder un vecteur de fonctionnalité particulier.</span><span class="sxs-lookup"><span data-stu-id="2f311-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="2f311-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="2f311-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="2f311-107">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="2f311-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="2f311-108">Exemple de vecteur de fonctionnalité à encoder dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="2f311-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="2f311-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="2f311-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="2f311-110">Taille requise pour encoder `sample` dans un registre qubit, exprimée sous la forme d’un nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="2f311-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>