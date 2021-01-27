---
uid: Microsoft.Quantum.Chemistry.JordanWigner.VQE.EstimateEnergy
title: Opération EstimateEnergy
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Chemistry.JordanWigner.VQE
qsharp.name: EstimateEnergy
qsharp.summary: Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.
ms.openlocfilehash: a64ac3970e3e67568f91b4e67775d834a80c04a1
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98835725"
---
# <a name="estimateenergy-operation"></a><span data-ttu-id="6ffc8-102">Opération EstimateEnergy</span><span class="sxs-lookup"><span data-stu-id="6ffc8-102">EstimateEnergy operation</span></span>

<span data-ttu-id="6ffc8-103">Espace de noms : [Microsoft. Quantum. chimie. JordanWigner. VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-103">Namespace: [Microsoft.Quantum.Chemistry.JordanWigner.VQE](xref:Microsoft.Quantum.Chemistry.JordanWigner.VQE)</span></span>

<span data-ttu-id="6ffc8-104">Package : [Microsoft. Quantum. chimie](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-104">Package: [Microsoft.Quantum.Chemistry](https://nuget.org/packages/Microsoft.Quantum.Chemistry)</span></span>


<span data-ttu-id="6ffc8-105">Estime l’énergie de la molécule en additionnant l’énergie fournie par les conditions d' Jordan-Wigner individuelles.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-105">Estimates the energy of the molecule by summing the energy contributed by the individual Jordan-Wigner terms.</span></span>

```qsharp
operation EstimateEnergy (jwHamiltonian : Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData, nSamples : Int) : Double
```


## <a name="description"></a><span data-ttu-id="6ffc8-106">Description</span><span class="sxs-lookup"><span data-stu-id="6ffc8-106">Description</span></span>

<span data-ttu-id="6ffc8-107">Cette opération repose implicitement sur la Convention d’indexation Spin Down.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-107">This operation implicitly relies on the spin up-down indexing convention.</span></span>

## <a name="input"></a><span data-ttu-id="6ffc8-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="6ffc8-108">Input</span></span>

### <a name="jwhamiltonian--jordanwignerencodingdata"></a><span data-ttu-id="6ffc8-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-109">jwHamiltonian : [JordanWignerEncodingData](xref:Microsoft.Quantum.Chemistry.JordanWigner.JordanWignerEncodingData)</span></span>

<span data-ttu-id="6ffc8-110">Jordan-Wigner Hamilton.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-110">The Jordan-Wigner Hamiltonian.</span></span>


### <a name="nsamples--int"></a><span data-ttu-id="6ffc8-111">nSamples : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-111">nSamples : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="6ffc8-112">Nombre d’échantillons à utiliser pour l’estimation du terme attentes.</span><span class="sxs-lookup"><span data-stu-id="6ffc8-112">The number of samples to use for the estimation of the term expectations.</span></span>



## <a name="output--double"></a><span data-ttu-id="6ffc8-113">Sortie : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="6ffc8-113">Output : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="6ffc8-114">L’énergie estimée de la molécule</span><span class="sxs-lookup"><span data-stu-id="6ffc8-114">The estimated energy of the molecule</span></span>