---
uid: Microsoft.Quantum.Preparation.QuantumROM
title: QuantumROM fonction)
ms.date: 1/23/2021 12:00:00 AM
ms.topic: article
qsharp.kind: function
qsharp.namespace: Microsoft.Quantum.Preparation
qsharp.name: QuantumROM
qsharp.summary: >-
  > [!WARNING]

  > QuantumROM has been deprecated. Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.


  Uses the Quantum ROM technique to represent a given density matrix.

  Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$. In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$. In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}. \end{align} $$
ms.openlocfilehash: 64ed9aed7c9d9a4a689c5926f3cd085a2521c4db
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98856819"
---
# <a name="quantumrom-function"></a><span data-ttu-id="5c107-102">QuantumROM fonction)</span><span class="sxs-lookup"><span data-stu-id="5c107-102">QuantumROM function</span></span>

<span data-ttu-id="5c107-103">Espace de noms : [Microsoft. Quantum. PREPARATION](xref:Microsoft.Quantum.Preparation)</span><span class="sxs-lookup"><span data-stu-id="5c107-103">Namespace: [Microsoft.Quantum.Preparation](xref:Microsoft.Quantum.Preparation)</span></span>

<span data-ttu-id="5c107-104">Package : [Microsoft. Quantum. standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span><span class="sxs-lookup"><span data-stu-id="5c107-104">Package: [Microsoft.Quantum.Standard](https://nuget.org/packages/Microsoft.Quantum.Standard)</span></span>


> [!WARNING]
> <span data-ttu-id="5c107-105">QuantumROM est déconseillé.</span><span class="sxs-lookup"><span data-stu-id="5c107-105">QuantumROM has been deprecated.</span></span> <span data-ttu-id="5c107-106">Utilisez plutôt <xref:Microsoft.Quantum.Preparation.PurifiedMixedState>.</span><span class="sxs-lookup"><span data-stu-id="5c107-106">Please use <xref:Microsoft.Quantum.Preparation.PurifiedMixedState> instead.</span></span>

<span data-ttu-id="5c107-107">Utilise la technique Quantum ROM pour représenter une matrice de densité donnée.</span><span class="sxs-lookup"><span data-stu-id="5c107-107">Uses the Quantum ROM technique to represent a given density matrix.</span></span>

<span data-ttu-id="5c107-108">À partir de la liste des $N $ coefficients $ \ alpha_j $, retourne un $U unitaire $ qui utilise la technique Quantum-ROM pour préparer une approximation $ \tilde\rho\ sum_ {j = 0} ^ {N-1} p_j \ket{j}\bra{j} $ de la purification de la matrice de densité $ \rho = \ sum_ {j = 0} ^ {N-1} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $.</span><span class="sxs-lookup"><span data-stu-id="5c107-108">Given a list of $N$ coefficients $\alpha_j$, this returns a unitary $U$ that uses the Quantum-ROM technique to prepare an approximation  $\tilde\rho\sum_{j=0}^{N-1}p_j\ket{j}\bra{j}$ of the purification of the density matrix $\rho=\sum_{j=0}^{N-1}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$.</span></span> <span data-ttu-id="5c107-109">Dans cette approximation, l’erreur $ \epsilon $ est telle que $ | p_j-\frac{| alpha_j |} {\ sum_k | \ alpha_k |} | \Le \epsilon/N $ et $ \| \tilde\rho-\rho \| \Le \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="5c107-109">In this approximation, the error $\epsilon$ is such that $|p_j-\frac{|alpha_j|}{\sum_k |\alpha_k|}|\le \epsilon / N$ and $\|\tilde\rho - \rho\| \le \epsilon$.</span></span> <span data-ttu-id="5c107-110">En d’autres termes, $ $ \begin{align} U\ket {0} ^ {\lceil\ Log_2 N\rceil} \ Ket {0} ^ {m} = \ sum_ {j = 0} ^ {N-1} \sqrt{p_j} \ket{j}\ket{\text{garbage} _J}.</span><span class="sxs-lookup"><span data-stu-id="5c107-110">In other words, $$ \begin{align} U\ket{0}^{\lceil\log_2 N\rceil}\ket{0}^{m}=\sum_{j=0}^{N-1}\sqrt{p_j} \ket{j}\ket{\text{garbage}_j}.</span></span>
<span data-ttu-id="5c107-111">\end{align} $ $</span><span class="sxs-lookup"><span data-stu-id="5c107-111">\end{align} $$</span></span>

```qsharp
function QuantumROM (targetError : Double, coefficients : Double[]) : ((Int, (Int, Int)), Double, ((Microsoft.Quantum.Arithmetic.LittleEndian, Qubit[]) => Unit is Adj + Ctl))
```


## <a name="input"></a><span data-ttu-id="5c107-112">Entrée</span><span class="sxs-lookup"><span data-stu-id="5c107-112">Input</span></span>

### <a name="targeterror--double"></a><span data-ttu-id="5c107-113">targetError : [double](xref:microsoft.quantum.lang-ref.double)</span><span class="sxs-lookup"><span data-stu-id="5c107-113">targetError : [Double](xref:microsoft.quantum.lang-ref.double)</span></span>

<span data-ttu-id="5c107-114">L’erreur cible $ \epsilon $.</span><span class="sxs-lookup"><span data-stu-id="5c107-114">The target error $\epsilon$.</span></span>


### <a name="coefficients--double"></a><span data-ttu-id="5c107-115">coefficients : [double](xref:microsoft.quantum.lang-ref.double)[]</span><span class="sxs-lookup"><span data-stu-id="5c107-115">coefficients : [Double](xref:microsoft.quantum.lang-ref.double)[]</span></span>

<span data-ttu-id="5c107-116">Tableau de $N $ coefficient spécifiant la probabilité des États de base.</span><span class="sxs-lookup"><span data-stu-id="5c107-116">Array of $N$ coefficients specifying the probability of basis states.</span></span>
<span data-ttu-id="5c107-117">Les nombres négatifs $-\ alpha_j $ seront traités comme étant positifs $ | \ alpha_j | $.</span><span class="sxs-lookup"><span data-stu-id="5c107-117">Negative numbers $-\alpha_j$ will be treated as positive $|\alpha_j|$.</span></span>



## <a name="output--intintintdoublelittleendianqubit--unit--is-adj--ctl"></a><span data-ttu-id="5c107-118">Sortie : (([int](xref:microsoft.quantum.lang-ref.int), ([int](xref:microsoft.quantum.lang-ref.int),[int](xref:microsoft.quantum.lang-ref.int))),[double](xref:microsoft.quantum.lang-ref.double), ([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [unité](xref:microsoft.quantum.lang-ref.unit)  est Adj + CTL)</span><span class="sxs-lookup"><span data-stu-id="5c107-118">Output : (([Int](xref:microsoft.quantum.lang-ref.int),([Int](xref:microsoft.quantum.lang-ref.int),[Int](xref:microsoft.quantum.lang-ref.int))),[Double](xref:microsoft.quantum.lang-ref.double),([LittleEndian](xref:Microsoft.Quantum.Arithmetic.LittleEndian),[Qubit](xref:microsoft.quantum.lang-ref.qubit)[]) => [Unit](xref:microsoft.quantum.lang-ref.unit)  is Adj + Ctl)</span></span>

## <a name="first-parameter"></a><span data-ttu-id="5c107-119">Premier paramètre</span><span class="sxs-lookup"><span data-stu-id="5c107-119">First parameter</span></span>

<span data-ttu-id="5c107-120">Un Tuple `(x,(y,z))` où `x = y + z` est le nombre total d’qubits allouées, `y` est le nombre de qubits pour le `LittleEndian` Registre et `z` est le nombre de garbage qubits.</span><span class="sxs-lookup"><span data-stu-id="5c107-120">A tuple `(x,(y,z))` where `x = y + z` is the total number of qubits allocated, `y` is the number of qubits for the `LittleEndian` register, and `z` is the Number of garbage qubits.</span></span>

## <a name="second-parameter"></a><span data-ttu-id="5c107-121">Deuxième paramètre</span><span class="sxs-lookup"><span data-stu-id="5c107-121">Second parameter</span></span>

<span data-ttu-id="5c107-122">La norme $ \ sum_j | \ alpha_j | $ du tableau coefficient.</span><span class="sxs-lookup"><span data-stu-id="5c107-122">The one-norm $\sum_j |\alpha_j|$ of the coefficient array.</span></span>

## <a name="third-parameter"></a><span data-ttu-id="5c107-123">Troisième paramètre</span><span class="sxs-lookup"><span data-stu-id="5c107-123">Third parameter</span></span>

<span data-ttu-id="5c107-124">Le $U unitaire $.</span><span class="sxs-lookup"><span data-stu-id="5c107-124">The unitary $U$.</span></span>

## <a name="example"></a><span data-ttu-id="5c107-125">Exemple</span><span class="sxs-lookup"><span data-stu-id="5c107-125">Example</span></span>

<span data-ttu-id="5c107-126">L’extrait de code suivant prépare une purification de l’État $3 $-qubit $ \rho = \ sum_ {j = 0} ^ {4} \frac{| alpha_j |} {\ sum_k | \ alpha_k |} \ket{j}\bra{j} $, où $ \vec\alpha = (1.0, 2.0, 3.0, 4.0, 5.0) $ et l’erreur est `1e-3` ;</span><span class="sxs-lookup"><span data-stu-id="5c107-126">The following code snippet prepares an purification of the $3$-qubit state $\rho=\sum_{j=0}^{4}\frac{|alpha_j|}{\sum_k |\alpha_k|}\ket{j}\bra{j}$, where $\vec\alpha=(1.0,2.0,3.0,4.0,5.0)$, and the error is `1e-3`;</span></span>

```qsharp
let coefficients = [1.0,2.0,3.0,4.0,5.0];
let targetError = 1e-3;
let ((nTotalQubits, (nIndexQubits, nGarbageQubits)), oneNorm, op) = QuantumROM(targetError, coefficients);
using (indexRegister = Qubit[nIndexQubits]) {
    using (garbageRegister = Qubit[nGarbageQubits]) {
        op(LittleEndian(indexRegister), garbageRegister);
    }
}
```

## <a name="references"></a><span data-ttu-id="5c107-127">Références</span><span class="sxs-lookup"><span data-stu-id="5c107-127">References</span></span>

- <span data-ttu-id="5c107-128">Encodage des spectres électroniques dans des circuits quantiques avec une complexité T linéaire Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru pâle, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span><span class="sxs-lookup"><span data-stu-id="5c107-128">Encoding Electronic Spectra in Quantum Circuits with Linear T Complexity Ryan Babbush, Craig Gidney, Dominic W. Berry, Nathan Wiebe, Jarrod McClean, Alexandru Paler, Austin Fowler, Hartmut Neven https://arxiv.org/abs/1805.03662</span></span>