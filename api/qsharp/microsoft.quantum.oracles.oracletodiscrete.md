---
uid: Microsoft.Quantum.Oracles.OracleToDiscrete
title: OracleToDiscrete fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Oracles
qsharp.name: OracleToDiscrete
qsharp.summary: Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.
ms.openlocfilehash: d26d57c587f24e7f74102c12753bcddb00fd8a9d
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708756"
---
# <a name="oracletodiscrete-function"></a><span data-ttu-id="c643c-102">OracleToDiscrete fonction)</span><span class="sxs-lookup"><span data-stu-id="c643c-102">OracleToDiscrete function</span></span>

<span data-ttu-id="c643c-103">Espace de noms : [Microsoft. Quantum. Oracle](xref:Microsoft.Quantum.Oracles)</span><span class="sxs-lookup"><span data-stu-id="c643c-103">Namespace: [Microsoft.Quantum.Oracles](xref:Microsoft.Quantum.Oracles)</span></span>

<span data-ttu-id="c643c-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="c643c-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="c643c-105">Dans le cas d’une opération qui représente une « boîte noire » Oracle, retourne une Oracle discrète qui représente la « boîte noire » Oracle répétée plusieurs fois.</span><span class="sxs-lookup"><span data-stu-id="c643c-105">Given an operation representing a "black-box" oracle, returns a discrete-time oracle which represents the "black-box" oracle repeated multiple times.</span></span>

```qsharp
function OracleToDiscrete (blackBoxOracle : (Qubit[] => Unit is Adj + Ctl)) : Microsoft.Quantum.Oracles.DiscreteOracle
```


## <a name="input"></a><span data-ttu-id="c643c-106">Entrée</span><span class="sxs-lookup"><span data-stu-id="c643c-106">Input</span></span>

### <a name="blackboxoracle--qubit--unit-adj--ctl"></a><span data-ttu-id="c643c-107">blackBoxOracle : [qubit](xref:microsoft.quantum.lang-ref.qubit)[] [=> ajuster](xref:microsoft.quantum.lang-ref.unit) + CTL</span><span class="sxs-lookup"><span data-stu-id="c643c-107">blackBoxOracle : [Qubit](xref:microsoft.quantum.lang-ref.qubit)[] => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl</span></span>

<span data-ttu-id="c643c-108">Opération à élever.</span><span class="sxs-lookup"><span data-stu-id="c643c-108">The operation to be exponentiated.</span></span>



## <a name="output--discreteoracle"></a><span data-ttu-id="c643c-109">Sortie : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span><span class="sxs-lookup"><span data-stu-id="c643c-109">Output : [DiscreteOracle](xref:Microsoft.Quantum.Oracles.DiscreteOracle)</span></span>

<span data-ttu-id="c643c-110">Opération partiellement appliquée sur la « boîte noire » Oracle représentant le temps d’Oracle discret</span><span class="sxs-lookup"><span data-stu-id="c643c-110">An operation partially applied over the "black-box" oracle representing the discrete-time oracle</span></span>