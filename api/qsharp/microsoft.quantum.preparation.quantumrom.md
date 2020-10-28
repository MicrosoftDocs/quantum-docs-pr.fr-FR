---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM fonction)
ms.date: 10/26/2020 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 8ba5c6fab4abcfaee7233df9535f22eea5f68c28
ms.sourcegitcommit: 29e0d88a30e4166fa580132124b0eb57e1f0e986
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92708204"
---
# <a name="quantumrom-function"></a><span data-ttu-id="35127-102">QuantumROM fonction)</span><span class="sxs-lookup"><span data-stu-id="35127-102">QuantumROM function</span></span>

<span data-ttu-id="35127-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="35127-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="35127-104">Packages [](https://nuget.org/packages/)</span><span class="sxs-lookup"><span data-stu-id="35127-104">Package: [](https://nuget.org/packages/)</span></span>


<span data-ttu-id="35127-105">Utilise la technique Quantum ROM pour représenter une matrice de densité donnée.</span><span class="sxs-lookup"><span data-stu-id="35127-105">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="35127-106">À partir de la liste des $N $ coefficients $ \ alpha_j $, retourne un $U unitaire $ qui utilise la technique Quantum-ROM pour préparer une approximation $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ de la purification de la matrice de densité $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="35127-106">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="35127-107">Dans cette approximation, l’erreur $ \epsilon $ est telle que $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ et $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="35127-107">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="35127-108">En d’autres termes, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ Ket {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="35127-108">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="35127-109">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="35127-109">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="35127-110">Entrée</span><span class="sxs-lookup"><span data-stu-id="35127-110">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="35127-111">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="35127-111">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="35127-112">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="35127-112">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="35127-113">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="35127-113">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="35127-114">Tableau de $N $ coefficient spécifiant la probabilité des États de base.</span><span class="sxs-lookup"><span data-stu-id="35127-114">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="35127-115">Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="35127-115">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit-adj--ctl"></a><span data-ttu-id="35127-116">Sortie : (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit) + CTL)</span><span class="sxs-lookup"><span data-stu-id="35127-116">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit) Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="35127-117">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="35127-117">First parameter</span></span>

<span data-ttu-id="35127-118">Un Tuple `(x,(y,z))` où `x = y + z` est le nombre total d’qubits allouées, `y` est le nombre de qubits pour le `LittleEndian` Registre et `z` est le nombre de garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="35127-118">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="35127-119">Deuxième paramètre</span><span class="sxs-lookup"><span data-stu-id="35127-119">Second parameter</span></span>

<span data-ttu-id="35127-120">La norme $ \ sum_j | \ alpha_j | $ du tableau coefficient.</span><span class="sxs-lookup"><span data-stu-id="35127-120">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="35127-121">Troisième paramètre</span><span class="sxs-lookup"><span data-stu-id="35127-121">Third parameter</span></span>

<span data-ttu-id="35127-122">Le $U unitaire $.</span><span class="sxs-lookup"><span data-stu-id="35127-122">The unitary $U$.</span></span>

## <a name="references"></a><span data-ttu-id="35127-123">Références</span><span class="sxs-lookup"><span data-stu-id="35127-123">References</span></span>

- <span data-ttu-id="35127-124">Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="35127-124">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>