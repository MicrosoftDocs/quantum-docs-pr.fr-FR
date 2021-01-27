---
uid: Microsoft.Quantum.Characterization.SingleQubitProcessTomographyMeasurement
title: Opération SingleQubitProcessTomographyMeasurement
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: operation
qsharp.namespace: Microsoft.Quantum.Characterization
qsharp.name: SingleQubitProcessTomographyMeasurement
qsharp.summary: Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.
ms.openlocfilehash: 883b98ad4f2d0ac4a02e55e444c04e8e7cf37af5
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98839653"
---
# <a name="singlequbitprocesstomographymeasurement-operation"></a><span data-ttu-id="9e1d4-102">Opération SingleQubitProcessTomographyMeasurement</span><span class="sxs-lookup"><span data-stu-id="9e1d4-102">SingleQubitProcessTomographyMeasurement operation</span></span>

<span data-ttu-id="9e1d4-103">Espace de noms : [Microsoft. Quantum. caractérisation](xref:Microsoft.Quantum.Characterization)</span><span class="sxs-lookup"><span data-stu-id="9e1d4-103">Namespace: [Microsoft.Quantum.Characterization](xref:Microsoft.Quantum.Characterization)</span></span>

<span data-ttu-id="9e1d4-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="9e1d4-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="9e1d4-105">Effectue une mesure de tomographie de processus qubit unique dans la base de Pauli, en fonction d’un canal d’intérêt particulier.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-105">Performs a single-qubit process tomography measurement in the Pauli basis, given a particular channel of interest.</span></span>

```qsharp
operation SingleQubitProcessTomographyMeasurement (preparation : Pauli, measurement : Pauli, channel : (Qubit => Unit)) : Result
```


## <a name="input"></a><span data-ttu-id="9e1d4-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="9e1d4-106">Input</span></span>

### <a name="preparation--pauli"></a><span data-ttu-id="9e1d4-107">préparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9e1d4-107">preparation : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9e1d4-108">L’élément de base Pauli $P $ dans lequel un qubit doit être préparé.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-108">The Pauli basis element $P$ in which a qubit is to be prepared.</span></span>


### <a name="measurement--pauli"></a><span data-ttu-id="9e1d4-109">mesure : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span><span class="sxs-lookup"><span data-stu-id="9e1d4-109">measurement : [Pauli](xref:microsoft.quantum.lang-ref.pauli)</span></span>

<span data-ttu-id="9e1d4-110">L’élément de base Pauli $Q $ dans lequel un qubit doit être mesuré.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-110">The Pauli basis element $Q$ in which a qubit is to be measured.</span></span>


### <a name="channel--qubit--unit"></a><span data-ttu-id="9e1d4-111">canal : [](xref:microsoft.quantum.lang-ref.qubit) => [unité](xref:microsoft.quantum.lang-ref.unit) qubit</span><span class="sxs-lookup"><span data-stu-id="9e1d4-111">channel : [Qubit](xref:microsoft.quantum.lang-ref.qubit) => [Unit](xref:microsoft.quantum.lang-ref.unit)</span></span> 

<span data-ttu-id="9e1d4-112">Un canal qubit unique $ \Lambda $ dont le comportement est estimé avec la tomographie de processus.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-112">A single qubit channel $\Lambda$ whose behavior is being estimated with process tomography.</span></span>



## <a name="output--__invalidresult__"></a><span data-ttu-id="9e1d4-113">Sortie : __non <Result> valide__</span><span class="sxs-lookup"><span data-stu-id="9e1d4-113">Output : __invalid<Result>__</span></span>

<span data-ttu-id="9e1d4-114">Le résultat `Zero` avec la probabilité $ $ \Begin{align} \Pr (\texttt{Zero} | \Lambda ; P, Q) = \operatorname{Tr}\left (\frac{\boldone + Q} {2} \Lambda\left [\frac{\boldone + P} {2} \right] \right).</span><span class="sxs-lookup"><span data-stu-id="9e1d4-114">The Result `Zero` with probability $$ \begin{align} \Pr(\texttt{Zero} | \Lambda; P, Q) = \operatorname{Tr}\left( \frac{\boldone + Q}{2} \Lambda\left[ \frac{\boldone + P}{2} \right] \right).</span></span>
<span data-ttu-id="9e1d4-115">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="9e1d4-115">\end{align} $$</span></span>

## <a name="remarks"></a><span data-ttu-id="9e1d4-116">Notes</span><span class="sxs-lookup"><span data-stu-id="9e1d4-116">Remarks</span></span>

<span data-ttu-id="9e1d4-117">La distribution sur les résultats retournés par cette opération est un cas spécial de tomographie d’État à deux qubit.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-117">The distribution over results returned by this operation is a special case of two-qubit state tomography.</span></span> <span data-ttu-id="9e1d4-118">Laissez $ \rho = J (\Lambda)/$2 être l’État Choi – Jamiłkowski pour $ \Lambda $.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-118">Let $\rho = J(\Lambda) / 2$ be the Choi–Jamiłkowski state for $\Lambda$.</span></span> <span data-ttu-id="9e1d4-119">La distribution ci-dessus est alors identique à $ $ \begin{align} \Pr (\texttt{Zero} | \rho ; M) = \operatorname{Tr} (M \rho), \end{align} $ $ WHERE $M = 2 (\boldone + P) ^ \mathrm{T}/2 \cdot (\boldone + Q)/$2 est la mesure effective correspondant à $P $ et $Q $.</span><span class="sxs-lookup"><span data-stu-id="9e1d4-119">Then, the distribution above is identical to $$ \begin{align} \Pr(\texttt{Zero} | \rho; M) = \operatorname{Tr}(M \rho), \end{align} $$ where $M = 2 (\boldone + P)^\mathrm{T} / 2 \cdot (\boldone + Q) / 2$ is the effective measurement corresponding to $P$ and $Q$.</span></span>