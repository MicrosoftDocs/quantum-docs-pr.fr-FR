---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: >-
  > [!WARNING]

  > QuantumROMQubitCount has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.


  Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: d6eac64eb62ec7a88d3231249b0bb1e05818f6e6
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856792"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="26753-102">QuantumROMQubitCount fonction)</span><span class="sxs-lookup"><span data-stu-id="26753-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="26753-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="26753-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="26753-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="26753-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="26753-105">QuantumROMQubitCount est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="26753-105">QuantumROMQubitCount has been deprecated.</span></span> <span data-ttu-id="26753-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements>.</span><span class="sxs-lookup"><span data-stu-id="26753-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedStateRequirements> instead.</span></span>

<span data-ttu-id="26753-107">Retourne le nombre total de qubits qui doivent être alloués à l’opération retournée par `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="26753-107">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="26753-108">Entrée</span><span class="sxs-lookup"><span data-stu-id="26753-108">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="26753-109">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="26753-109">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="26753-110">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="26753-110">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="26753-111">nCoeffs : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="26753-111">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="26753-112">Nombre de coefficients spécifiés dans `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="26753-112">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="26753-113">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="26753-113">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="26753-114">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="26753-114">First parameter</span></span>

<span data-ttu-id="26753-115">Un Tuple `(x,(y,z))` où `x = y + z` est le nombre total d’qubits allouées, `y` est le nombre de qubits pour le `LittleEndian` Registre et `z` est le nombre de garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="26753-115">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>