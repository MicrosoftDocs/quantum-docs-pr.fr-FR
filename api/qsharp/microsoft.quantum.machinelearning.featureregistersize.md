---
uid: Microsoft.Quantum.MachineLearning.FeatureRegisterSize
title: FeatureRegisterSize fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.MachineLearning
qsharp.name: FeatureRegisterSize
qsharp.summary: Returns the number of qubits required to encode a particular feature vector.
ms.openlocfilehash: 8f7c47c7547e7a0ac1672f308de445c1b46461e1
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708345"
---
# <a name="featureregistersize-function"></a><span data-ttu-id="49e1b-102">FeatureRegisterSize fonction)</span><span class="sxs-lookup"><span data-stu-id="49e1b-102">FeatureRegisterSize function</span></span>

<span data-ttu-id="49e1b-103">Espace de noms : [Microsoft. Quantum. MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span><span class="sxs-lookup"><span data-stu-id="49e1b-103">Namespace: [Microsoft.Quantum.MachineLearning](xref:Microsoft.Quantum.MachineLearning)</span></span>

<span data-ttu-id="49e1b-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="49e1b-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="49e1b-105">Retourne le nombre de qubits nécessaires pour encoder un vecteur de fonctionnalité particulier.</span><span class="sxs-lookup"><span data-stu-id="49e1b-105">Returns the number of qubits required to encode a particular feature vector.</span></span>

```qsharp
function FeatureRegisterSize (sample : Double[]) : Int
```


## <a name="input"></a><span data-ttu-id="49e1b-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="49e1b-106">Input</span></span>

### <a name="sample--double"></a><span data-ttu-id="49e1b-107">exemple : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="49e1b-107">sample : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="49e1b-108">Exemple de vecteur de fonctionnalité à encoder dans un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="49e1b-108">A sample feature vector to be encoded into a qubit register.</span></span>



## <a name="output--int"></a><span data-ttu-id="49e1b-109">Sortie : [int](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="49e1b-109">Output : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="49e1b-110">Taille requise pour encoder `sample` dans un registre qubit, exprimée sous la forme d’un nombre de qubits.</span><span class="sxs-lookup"><span data-stu-id="49e1b-110">The size required to encode `sample` into a qubit register, expressed as a number of qubits.</span></span>