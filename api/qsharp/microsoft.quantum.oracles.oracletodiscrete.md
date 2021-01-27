---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: ab59cdf0ab05092a9d4e7856b7808b13df655571
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98842536"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="337af-102">OracleToDiscrete fonction)</span><span class="sxs-lookup"><span data-stu-id="337af-102">OracleToDiscrete function</span></span>

<span data-ttu-id="337af-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="337af-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="337af-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="337af-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


<span data-ttu-id="337af-105">Dans le cas d’une opération qui représente une « boîte noire » Oracle, retourne une Oracle discrète qui représente la « boîte noire » Oracle répétée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="337af-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="337af-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="337af-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit--is-adj--ctl"></a><span data-ttu-id="337af-107">blackBoxOracle : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL</span><span class="sxs-lookup"><span data-stu-id="337af-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl</span></span>

<span data-ttu-id="337af-108">Opération à élever.</span><span class="sxs-lookup"><span data-stu-id="337af-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="337af-109">Sortie : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="337af-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="337af-110">Opération partiellement appliquée sur la « boîte noire » Oracle représentant le temps d’Oracle discret</span><span class="sxs-lookup"><span data-stu-id="337af-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>

## <a name="example"></a><span data-ttu-id="337af-111">Exemple</span><span class="sxs-lookup"><span data-stu-id="337af-111">Example</span></span>

<span data-ttu-id="337af-112">`OracleToDiscrete(U)(3, target)` équivaut à une `U(target)` répétition à trois reprises.</span><span class="sxs-lookup"><span data-stu-id="337af-112">`OracleToDiscrete(U)(3, target)` is equivalent to `U(target)` repeated three times.</span></span>