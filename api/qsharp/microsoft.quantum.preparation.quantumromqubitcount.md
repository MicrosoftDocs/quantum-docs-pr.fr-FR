---
uid: Microsoft.Quantum.Preparation.QuantumROMQubitCount
title: QuantumROMQubitCount fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROMQubitCount
qsharp.summary: Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.
ms.openlocfilehash: 988d5efa3e27cf5e9a276ab3ab443c10f88fe1ad
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708192"
---
# <a name="quantumromqubitcount-function"></a><span data-ttu-id="c1df0-102">QuantumROMQubitCount fonction)</span><span class="sxs-lookup"><span data-stu-id="c1df0-102">QuantumROMQubitCount function</span></span>

<span data-ttu-id="c1df0-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="c1df0-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="c1df0-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c1df0-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c1df0-105">Retourne le nombre total de qubits qui doivent être alloués à l’opération retournée par `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="c1df0-105">Returns the total number of qubits that must be allocated to the operation returned by `QuantumROM`.</span></span>

```qsharp
function QuantumROMQubitCount (targetError : Double, nCoeffs : Int) : (Int, (Int, Int))
```


## <a name="input"></a><span data-ttu-id="c1df0-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c1df0-106">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="c1df0-107">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="c1df0-107">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="c1df0-108">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="c1df0-108">The target error $\epsilon$.</span></span>


### <a name="ncoeffs--int"></a><span data-ttu-id="c1df0-109">nCoeffs : [entier](xref:microsoft.quantum.lang-ref.int)</span><span class="sxs-lookup"><span data-stu-id="c1df0-109">nCoeffs : [Int](xref:microsoft.quantum.lang-ref.int)</span></span>

<span data-ttu-id="c1df0-110">Nombre de coefficients spécifiés dans `QuantumROM` .</span><span class="sxs-lookup"><span data-stu-id="c1df0-110">Number of coefficients specified in `QuantumROM`.</span></span>



## <a name="output--intintint"></a><span data-ttu-id="c1df0-111">Sortie : ([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int)))</span><span class="sxs-lookup"><span data-stu-id="c1df0-111">Output : ([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int)))</span></span>

## <a name="first-parameter"></a><span data-ttu-id="c1df0-112">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="c1df0-112">First parameter</span></span>

<span data-ttu-id="c1df0-113">Un Tuple `(x,(y,z))` où `x = y + z` est le nombre total d’qubits allouées, `y` est le nombre de qubits pour le `LittleEndian` Registre et `z` est le nombre de garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="c1df0-113">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>