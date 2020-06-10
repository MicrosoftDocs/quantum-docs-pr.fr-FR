---
title: Mesures Pauli
description: Découvrez comment utiliser des opérations de mesure Pauli à simple et qubit.
author: QuantumWriter
uid: microsoft.quantum.concepts.pauli
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
no-loc:
- $
- $
- '\cdots'
- bmatrix
- '\ddots'
- '\equiv'
- '\sum'
- '\begin'
- '\end'
- '\sqrt'
- '\otimes'
- '{'
- '}'
- '\text'
- '\phi'
- '\kappa'
- '\psi'
- '\alpha'
- '\beta'
- '\gamma'
- '\delta'
- '\omega'
- '\bra'
- '\ket'
- '\boldone'
- '\\\\'
- '\\'
- =
- '\frac'
- '\text'
- '\mapsto'
- '\dagger'
- '\to'
- "\begin{cases}"
- "\end{cases}"
- '\operatorname'
- '\braket'
- '\id'
- '\expect'
- '\defeq'
- '\variance'
- '\dd'
- '&'
- "\begin{align}"
- "\end{align}"
- '\Lambda'
- '\lambda'
- '\Omega'
- '\mathrm'
- '\left'
- '\right'
- '\qquad'
- '\times'
- '\big'
- '\langle'
- '\rangle'
- '\bigg'
- '\Big'
- '|'
- '\mathbb'
- '\vec'
- '\in'
- '\texttt'
- '\ne'
- <
- '>'
- '\leq'
- '\geq'
- ~~
- "~"
ms.openlocfilehash: 115c1703e433f24930e4be61b545048c95da28d1
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630301"
---
# <a name="pauli-measurements"></a><span data-ttu-id="389f8-103">Mesures Pauli</span><span class="sxs-lookup"><span data-stu-id="389f8-103">Pauli Measurements</span></span>

<span data-ttu-id="389f8-104">Dans les discussions précédentes, nous nous sommes concentrés sur les mesures de base de calcul.</span><span class="sxs-lookup"><span data-stu-id="389f8-104">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="389f8-105">En fait, il existe d’autres mesures courantes qui se produisent dans quantum computing qui, du point de vue de la notation, sont pratiques pour exprimer en termes de mesures de la base de calcul.</span><span class="sxs-lookup"><span data-stu-id="389f8-105">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="389f8-106">Lorsque vous utilisez Q #, le type de mesure le plus courant dans lequel vous allez être exécuté sera probablement des *mesures Pauli*, qui généralisent les mesures de la base de calcul pour inclure les mesures dans d’autres bases et la parité entre les différents qubits.</span><span class="sxs-lookup"><span data-stu-id="389f8-106">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="389f8-107">Dans ce cas, il est courant d’aborder la mesure d’un opérateur Pauli, en général un opérateur tel que $X, Y, Z $ ou $Z \otimes z, x \otimes x, x \otimes Y $ , etc.</span><span class="sxs-lookup"><span data-stu-id="389f8-107">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
> <span data-ttu-id="389f8-108">Dans Q #, les opérateurs Pauli multi-qubit sont généralement représentés par des tableaux de type `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="389f8-108">In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
> <span data-ttu-id="389f8-109">Par exemple, pour représenter $X \otimes Z \otimes Y $ , vous pouvez utiliser le tableau `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="389f8-109">For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="389f8-110">L’étude des mesures en termes d’opérateurs Pauli est particulièrement courante dans le sous-champ de la correction des erreurs Quantum.</span><span class="sxs-lookup"><span data-stu-id="389f8-110">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="389f8-111">Dans Q #, nous suivons une convention similaire. Nous expliquons maintenant cette vue alternative des mesures.</span><span class="sxs-lookup"><span data-stu-id="389f8-111">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="389f8-112">Avant de plonger dans les détails sur la façon de considérer une mesure Pauli, il est utile de réfléchir à la mesure d’un qubit unique dans un ordinateur quantique à l’État Quantum.</span><span class="sxs-lookup"><span data-stu-id="389f8-112">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="389f8-113">Imaginez que nous avons un $ État quantum $n qubit, puis que la mesure d’un qubit règle immédiatement la moitié des possibilités de $2 ^ n $ dont l’État est peut-être.</span><span class="sxs-lookup"><span data-stu-id="389f8-113">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="389f8-114">En d’autres termes, la mesure projette l’État Quantum sur l’un des deux demi-espaces.</span><span class="sxs-lookup"><span data-stu-id="389f8-114">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="389f8-115">Nous pouvons généraliser la façon dont nous pensons à la mesure pour refléter cette intuition.</span><span class="sxs-lookup"><span data-stu-id="389f8-115">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="389f8-116">Pour identifier ces sous-espaces de manière concise, nous avons besoin d’un langage pour les décrire.</span><span class="sxs-lookup"><span data-stu-id="389f8-116">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="389f8-117">Une façon de décrire les deux sous-espaces consiste à les spécifier à l’aide d’une matrice qui a simplement deux valeurs propres uniques, pris par convention comme étant $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-117">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="389f8-118">Pour obtenir un exemple simple de description des sous-espaces de cette manière, envisagez $Z $ :</span><span class="sxs-lookup"><span data-stu-id="389f8-118">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

<span data-ttu-id="389f8-119">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-119">$$ \begin{align}</span></span>
  <span data-ttu-id="389f8-120">Z & = \begin{ bmatrix } 1 & 0 \\ \\ 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="389f8-120">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="389f8-121">\end{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-121">\end{align}</span></span>
$$

<span data-ttu-id="389f8-122">En lisant les éléments diagonales de la matrice Pauli-$Z $ , nous voyons que $Z $ a deux vecteurs propres, $ \ket{0 } $ et $ \ket{1 } $, avec la valeurs propres $ \pm 1 correspondante $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-122">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="389f8-123">Par conséquent, si nous mesurons qubit et obtenons `Zero` (correspondant à l’État $ \ket{0 } $), nous savons que l’état de notre qubit est un eigenstate $ + 1 $ de l' $ opérateur $Z.</span><span class="sxs-lookup"><span data-stu-id="389f8-123">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="389f8-124">De même, si nous obtenons `One` , nous savons que l’état de notre qubit est un $ eigenstate de $Z $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-124">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$.</span></span>
<span data-ttu-id="389f8-125">Ce processus est appelé dans le langage des mesures de Pauli comme la « mesure de la Pauli $Z $ » et est entièrement équivalent à l’exécution d’une mesure de base de calcul.</span><span class="sxs-lookup"><span data-stu-id="389f8-125">This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="389f8-126">Toute \times matrice $2 2 $ qui est une transformation unitaire de $Z $ remplit également ce critère.</span><span class="sxs-lookup"><span data-stu-id="389f8-126">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="389f8-127">Autrement dit, nous pourrions également utiliser une matrice $A = U ^ \dagger Z U $ , où $U $ est une autre matrice unitaire, pour fournir une matrice qui définit les deux résultats d’une mesure dans son $ \pm 1 $ vecteurs propres.</span><span class="sxs-lookup"><span data-stu-id="389f8-127">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="389f8-128">La notation des mesures Pauli fait référence à cette équivalence d’unité en identifiant les mesures $X, Y, Z $ comme des mesures équivalentes permettant d’obtenir des informations à partir d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="389f8-128">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="389f8-129">Ces mesures sont fournies ci-dessous pour des raisons pratiques.</span><span class="sxs-lookup"><span data-stu-id="389f8-129">These measurements are given below for convenience.</span></span>


|<span data-ttu-id="389f8-130">Mesure Pauli</span><span class="sxs-lookup"><span data-stu-id="389f8-130">Pauli Measurement</span></span>  |<span data-ttu-id="389f8-131">Transformation unitaire</span><span class="sxs-lookup"><span data-stu-id="389f8-131">Unitary transformation</span></span>  |
|-------------------|------------------------|
| <span data-ttu-id="389f8-132">$Z$</span><span class="sxs-lookup"><span data-stu-id="389f8-132">$Z$</span></span>               | <span data-ttu-id="389f8-133">$ \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-133">$\boldone$</span></span>             |
| <span data-ttu-id="389f8-134">$X$</span><span class="sxs-lookup"><span data-stu-id="389f8-134">$X$</span></span>               | <span data-ttu-id="389f8-135">$H$</span><span class="sxs-lookup"><span data-stu-id="389f8-135">$H$</span></span>                    |
| <span data-ttu-id="389f8-136">$Y$</span><span class="sxs-lookup"><span data-stu-id="389f8-136">$Y$</span></span>               | <span data-ttu-id="389f8-137">$HS ^ {\dagger}$</span><span class="sxs-lookup"><span data-stu-id="389f8-137">$HS^{\dagger}$</span></span>         |

<span data-ttu-id="389f8-138">Autrement dit, l’utilisation de ce langage, « Measure $Y $ » équivaut à appliquer $HS ^ \dagger, puis à $ mesurer le calcul, où [`S`](xref:microsoft.quantum.intrinsic.s) est une opération quantique intrinsèque parfois appelée « porte-phase » et peut être simulée par la matrice d’unités</span><span class="sxs-lookup"><span data-stu-id="389f8-138">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

<span data-ttu-id="389f8-139">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-139">$$ \begin{align}</span></span>
    <span data-ttu-id="389f8-140">S = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="389f8-140">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="389f8-141">1 & 0 \\ \\ 0 & je \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="389f8-141">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
<span data-ttu-id="389f8-142">\end{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-142">\end{align}</span></span>
$$

<span data-ttu-id="389f8-143">Cela équivaut également à appliquer $HS ^ \dagger $ au vecteur d’État Quantum, puis à mesurer $Z $ , de telle sorte que l’opération suivante soit équivalente à `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="389f8-143">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        H(q);
        Adjoint S(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="389f8-144">L’état correct est ensuite trouvé en transformant la base de calcul, ce qui revient à appliquer $SH $ au vecteur d’État Quantum. dans l’extrait de code ci-dessus, la transformation vers la base de calcul est gérée automatiquement par l’utilisation du `within … apply` bloc.</span><span class="sxs-lookup"><span data-stu-id="389f8-144">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="389f8-145">Dans Q #, nous disons le résultat---autrement dit, les informations classiques extraites de l’interaction avec l’État---sont fournies par une `Result` valeur $j \Dans \\ {\Texttt{Zero } , \texttt{One } \\ } $ indiquant si le résultat est dans $ (-1) ^ j $ eigenspace de l’opérateur Pauli mesuré.</span><span class="sxs-lookup"><span data-stu-id="389f8-145">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="389f8-146">Mesures à plusieurs qubit</span><span class="sxs-lookup"><span data-stu-id="389f8-146">Multiple-qubit measurements</span></span>

<span data-ttu-id="389f8-147">Les mesures des opérateurs Pauli à plusieurs qubit sont définies de la même manière, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="389f8-147">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

<span data-ttu-id="389f8-148">$ $ Z \otimes z = \begin{ bmatrix } 1 &0 &0&0 \\\\ 0 & -1&0&0 \\\\ 0&0 & -1&0 \\\\ 0&0&0&1 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="389f8-148">$$ Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="389f8-149">Ainsi, les produits tenseur de deux opérateurs Pauli-$Z $ forment une matrice composée de deux espaces constitués de $ + 1 $ et de $-1 $ valeurs propres.</span><span class="sxs-lookup"><span data-stu-id="389f8-149">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="389f8-150">Comme avec le cas qubit, les deux constituent un demi-espace, ce qui signifie que la moitié de l’espace de vecteur accessible appartient au eigenspace $ + 1 $ et la moitié restante à la eigenspace $-1 $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-150">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="389f8-151">En général, il est facile de voir à partir de la définition du produit tenseur que tout produit tenseur d’opérateurs Pauli-$Z $ et l’identité en obéissent également.</span><span class="sxs-lookup"><span data-stu-id="389f8-151">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="389f8-152">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="389f8-152">For example,</span></span>

<span data-ttu-id="389f8-153">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-153">$$ \begin{align}</span></span>
    <span data-ttu-id="389f8-154">Z \otimes \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="389f8-154">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="389f8-155">1 & 0 & 0 & 0 \\ \\ 0 & 1 & 0 & 0 0 & 0 \\ \\ &-1 & 0 \\ \\ 0 & 0 & 0 &-1 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="389f8-155">1 &  0 &  0 &  0 \\\\ 0 &  1 &  0 &  0 \\\\ 0 &  0 & -1 &  0 \\\\ 0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
<span data-ttu-id="389f8-156">\end{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-156">\end{align}</span></span>
$$

<span data-ttu-id="389f8-157">Comme précédemment, toute transformation unitaire de ces matrices décrit également deux demi-espaces étiquetés par $ \pm 1 $ valeurs propres.</span><span class="sxs-lookup"><span data-stu-id="389f8-157">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="389f8-158">Par exemple, $X \otimes X = h \otimes h (z \otimes z) h \otimes h $ à partir de l’identité qui $Z = HxH $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-158">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="389f8-159">Comme dans le cas d’une qubit, toutes les mesures Pauli à deux qubit peuvent être écrites comme $U ^ \dagger (Z \otimes \ID) U $ pour les \times $ matrices unitaires $4 4 $U $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-159">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$.</span></span> <span data-ttu-id="389f8-160">Nous énumérons les transformations dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="389f8-160">We enumerate the transformations in the following table.</span></span>

> [!NOTE]
> <span data-ttu-id="389f8-161">Dans le tableau ci-dessous, nous utilisons $ \operatorname{SWAP } $ pour indiquer la matrice $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-161">In the table below, we use $\operatorname{SWAP}$ to indicate the matrix $$ \begin{align}</span></span>
>     <span data-ttu-id="389f8-162">\operatorname{SWAP } & = \left (\begin{Matrix}</span><span class="sxs-lookup"><span data-stu-id="389f8-162">\operatorname{SWAP} & = \left(\begin{matrix}</span></span>
>         <span data-ttu-id="389f8-163">1 & 0 & 0 & 0 \\ \\ 0 & 0 & 1 & 0 \\ \\ 0 & 1 & 0 & 0 \\ \\ 0 & 0 & 0 & 1 \end{Matrix } \right) \end{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-163">1 & 0 & 0 & 0 \\\\ 0 & 0 & 1 & 0 \\\\ 0 & 1 & 0 & 0 \\\\ 0 & 0 & 0 & 1 \end{matrix}\right) \end{align}</span></span>
> <span data-ttu-id="389f8-164">$ $ utilisé pour simuler l’opération intrinsèque [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="389f8-164">$$ used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

|<span data-ttu-id="389f8-165">Mesure Pauli</span><span class="sxs-lookup"><span data-stu-id="389f8-165">Pauli Measurement</span></span>     |<span data-ttu-id="389f8-166">Transformation unitaire</span><span class="sxs-lookup"><span data-stu-id="389f8-166">Unitary transformation</span></span>  |
|----------------------|------------------------|
| <span data-ttu-id="389f8-167">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-167">$Z \otimes \boldone$</span></span> | <span data-ttu-id="389f8-168">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-168">$\boldone \otimes \boldone$</span></span> |
| <span data-ttu-id="389f8-169">$Z \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-169">$Z\otimes \boldone$</span></span> | <span data-ttu-id="389f8-170">$ \boldone \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-170">$\boldone\otimes \boldone$</span></span> |
| <span data-ttu-id="389f8-171">$X \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-171">$X\otimes \boldone$</span></span> | <span data-ttu-id="389f8-172">$H \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-172">$H\otimes \boldone$</span></span> |
| <span data-ttu-id="389f8-173">$Y \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-173">$Y\otimes \boldone$</span></span> | <span data-ttu-id="389f8-174">$HS ^ \dagger \otimes \boldone$</span><span class="sxs-lookup"><span data-stu-id="389f8-174">$HS^\dagger\otimes \boldone$</span></span> |
| <span data-ttu-id="389f8-175">$ \boldone \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="389f8-175">$\boldone \otimes Z$</span></span> | <span data-ttu-id="389f8-176">$ \operatorname{SWAP}$</span><span class="sxs-lookup"><span data-stu-id="389f8-176">$\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="389f8-177">$ \boldone \otimes X$</span><span class="sxs-lookup"><span data-stu-id="389f8-177">$\boldone \otimes X$</span></span> | <span data-ttu-id="389f8-178">$ (H \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="389f8-178">$(H\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="389f8-179">$ \boldone \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="389f8-179">$\boldone \otimes Y$</span></span> | <span data-ttu-id="389f8-180">$ (HS ^ \dagger \otimes \boldone) \operatorname{swap}$</span><span class="sxs-lookup"><span data-stu-id="389f8-180">$(HS^\dagger\otimes \boldone)\operatorname{SWAP}$</span></span> |
| <span data-ttu-id="389f8-181">$Z \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="389f8-181">$Z\otimes Z$</span></span> | <span data-ttu-id="389f8-182">$ \operatorname{CNOT } \_ {10}$</span><span class="sxs-lookup"><span data-stu-id="389f8-182">$\operatorname{CNOT}\_{10}$</span></span> |
| <span data-ttu-id="389f8-183">$X \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="389f8-183">$X\otimes Z$</span></span> | <span data-ttu-id="389f8-184">$ \operatorname{CNOT } \_ {10 } (H \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="389f8-184">$\operatorname{CNOT}\_{10}(H\otimes \boldone)$</span></span> |
| <span data-ttu-id="389f8-185">$Y \otimes Z$</span><span class="sxs-lookup"><span data-stu-id="389f8-185">$Y\otimes Z$</span></span> | <span data-ttu-id="389f8-186">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes \boldone) $</span><span class="sxs-lookup"><span data-stu-id="389f8-186">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$</span></span> |
| <span data-ttu-id="389f8-187">$Z \otimes X$</span><span class="sxs-lookup"><span data-stu-id="389f8-187">$Z\otimes X$</span></span> | <span data-ttu-id="389f8-188">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="389f8-188">$\operatorname{CNOT}\_{10}(\boldone\otimes H)$</span></span> |
| <span data-ttu-id="389f8-189">$X \otimes X$</span><span class="sxs-lookup"><span data-stu-id="389f8-189">$X\otimes X$</span></span> | <span data-ttu-id="389f8-190">$ \operatorname{CNOT } \_ {10 } (h \otimes h) $</span><span class="sxs-lookup"><span data-stu-id="389f8-190">$\operatorname{CNOT}\_{10}(H\otimes H)$</span></span> |
| <span data-ttu-id="389f8-191">$Y \otimes X$</span><span class="sxs-lookup"><span data-stu-id="389f8-191">$Y\otimes X$</span></span> | <span data-ttu-id="389f8-192">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes H) $</span><span class="sxs-lookup"><span data-stu-id="389f8-192">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$</span></span> |
| <span data-ttu-id="389f8-193">$Z \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="389f8-193">$Z\otimes Y$</span></span> | <span data-ttu-id="389f8-194">$ \operatorname{CNOT } \_ {10 } (\boldone \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="389f8-194">$\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="389f8-195">$X \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="389f8-195">$X\otimes Y$</span></span> | <span data-ttu-id="389f8-196">$ \operatorname{CNOT } \_ {10 } (H \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="389f8-196">$\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$</span></span> |
| <span data-ttu-id="389f8-197">$Y \otimes Y$</span><span class="sxs-lookup"><span data-stu-id="389f8-197">$Y\otimes Y$</span></span> | <span data-ttu-id="389f8-198">$ \operatorname{CNOT } \_ {10 } (HS ^ \dagger \otimes HS ^ \dagger) $</span><span class="sxs-lookup"><span data-stu-id="389f8-198">$\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$</span></span> |

<span data-ttu-id="389f8-199">Ici, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) opération s’affiche pour la raison suivante.</span><span class="sxs-lookup"><span data-stu-id="389f8-199">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="389f8-200">Chaque mesure Pauli qui n’inclut pas la matrice $ \boldone $ est équivalente à une unité pour $Z \otimes Z $ par le raisonnement ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="389f8-200">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="389f8-201">Le valeurs propres de $Z \otimes Z $ dépend uniquement de la parité des qubits qui composent chaque vecteur de base de calcul, et les opérations non contrôlées servent à calculer cette parité et à la stocker dans le premier bit.</span><span class="sxs-lookup"><span data-stu-id="389f8-201">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="389f8-202">Une fois le premier bit mesuré, nous pouvons récupérer l’identité du demi-espace résultant, ce qui équivaut à mesurer l’opérateur Pauli.</span><span class="sxs-lookup"><span data-stu-id="389f8-202">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="389f8-203">Une remarque supplémentaire : s’il peut être tentant de supposer que la mesure $Z \otimes Z $ est identique à la mesure séquentielle $Z \otimes \mathbb{1 } $, puis à $ \mathbb{1 } \otimes z $ , cette hypothèse est false.</span><span class="sxs-lookup"><span data-stu-id="389f8-203">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="389f8-204">La raison est que la mesure $Z \otimes Z $ projette l’État Quantum dans le eigenstate $ + 1 $ ou $-1 $ de ces opérateurs.</span><span class="sxs-lookup"><span data-stu-id="389f8-204">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="389f8-205">La mesure de $Z \otimes \mathbb{1 } $, puis de $ \Mathbb{1 } \otimes Z $ projette le vecteur d’État Quantum d’abord sur un demi-espace de $Z \otimes \mathbb{1 } $, puis sur un demi-espace de $ \mathbb{1 } \otimes Z $ . Étant donné qu’il y a quatre vecteurs de base de calcul, l’exécution des deux mesures permet de réduire l’État à un quart d’espace et, par conséquent, de la réduire à un vecteur de calcul unique.</span><span class="sxs-lookup"><span data-stu-id="389f8-205">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="389f8-206">Corrélations entre qubits</span><span class="sxs-lookup"><span data-stu-id="389f8-206">Correlations between qubits</span></span>
<span data-ttu-id="389f8-207">Une autre façon d’examiner la mesure des produits tenseur des matrices Pauli, tels que $X \otimes X $ ou $Z \otimes Z, $ est que ces mesures vous permettent de consulter les informations stockées dans les corrélations entre les deux qubits.</span><span class="sxs-lookup"><span data-stu-id="389f8-207">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="389f8-208">La mesure $X \otimes \ID $ vous permet de consulter les informations qui sont stockées localement dans le premier qubit.</span><span class="sxs-lookup"><span data-stu-id="389f8-208">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="389f8-209">Alors que les deux types de mesures sont tout aussi utiles dans Quantum Computing, le premier éclaire la puissance de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="389f8-209">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="389f8-210">Il révèle que dans Quantum Computing, les informations que vous souhaitez apprendre ne sont pas stockées dans un qubit unique mais plutôt stockées non localement dans toutes les qubits en même temps, et par conséquent, uniquement en les examinant par une mesure conjointe (par exemple, $Z \otimes Z $ ). ces informations deviennent manifestes.</span><span class="sxs-lookup"><span data-stu-id="389f8-210">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="389f8-211">Par exemple, dans la correction des erreurs, nous souhaitons souvent savoir quelle erreur s’est produite lors de l’apprentissage de l’état que nous tentons de protéger.</span><span class="sxs-lookup"><span data-stu-id="389f8-211">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="389f8-212">L' [exemple de code de tourne-miroir](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) illustre la manière dont vous pouvez effectuer cette opération à l’aide de mesures telles que $Z \otimes Z \otimes \ID $ et $ \ID \Otimes z \otimes z $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-212">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/master/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$.</span></span>
<!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded. -->

<span data-ttu-id="389f8-213">Les opérateurs Pauli arbitraires tels que $X \otimes Y \Otimes Z \otimes \boldone $ peuvent également être mesurés.</span><span class="sxs-lookup"><span data-stu-id="389f8-213">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="389f8-214">Tous les produits tenseur des opérateurs Pauli n’ont que deux valeurs propres $ \pm 1 $ et les deux eigenspaces représentent des demi-espaces de l’ensemble de l’espace de vecteur.</span><span class="sxs-lookup"><span data-stu-id="389f8-214">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="389f8-215">Ils coïncident donc avec les exigences indiquées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="389f8-215">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="389f8-216">Dans Q #, ces mesures retournent $j $ si la mesure génère un résultat dans le eigenspace du signe $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-216">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="389f8-217">Il est utile de disposer de mesures Pauli en tant que fonctionnalité intégrée dans Q #, car la mesure de ces opérateurs nécessite de longues chaînes de transformations non contrôlées et de base pour décrire l’opération de diagonale $U $ la porte nécessaire pour exprimer l’opération en tant que produit tenseur de $Z $ et $ \ID $ . En étant en mesure de spécifier que vous souhaitez effectuer une de ces mesures prédéfinies, vous n’avez pas besoin de vous soucier de la façon de transformer votre base de manière à ce qu’une mesure de base de calcul fournisse les informations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="389f8-217">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$. By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="389f8-218">Q # gère automatiquement toutes les transformations de base nécessaires.</span><span class="sxs-lookup"><span data-stu-id="389f8-218">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="389f8-219">Pour plus d’informations, consultez [`Measure`](xref:microsoft.quantum.intrinsic.measure) les [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) opérations et.</span><span class="sxs-lookup"><span data-stu-id="389f8-219">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="389f8-220">Le pas de clonage</span><span class="sxs-lookup"><span data-stu-id="389f8-220">The No-Cloning Theorem</span></span>

<span data-ttu-id="389f8-221">Les informations de Quantum sont puissantes.</span><span class="sxs-lookup"><span data-stu-id="389f8-221">Quantum information is powerful.</span></span>
<span data-ttu-id="389f8-222">Cela nous permet de faire des choses étonnantes, telles que les chiffres de facteur de façon exponentielle plus rapide que les algorithmes classiques les plus connus, ou de simuler efficacement des systèmes d’électrons corrélés qui nécessitent un coût exponentiel pour une simulation précise.</span><span class="sxs-lookup"><span data-stu-id="389f8-222">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="389f8-223">Toutefois, il existe des limitations à la puissance de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="389f8-223">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="389f8-224">L’une de ces limitations est donnée par le seuil de *non-clonage*.</span><span class="sxs-lookup"><span data-stu-id="389f8-224">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="389f8-225">Le nom du terme de non-clonage est avec justesse.</span><span class="sxs-lookup"><span data-stu-id="389f8-225">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="389f8-226">Il interdit le clonage d’États de Quantum génériques par un ordinateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="389f8-226">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="389f8-227">La preuve du pas de l’un est remarquablement simple.</span><span class="sxs-lookup"><span data-stu-id="389f8-227">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="389f8-228">Bien qu’une preuve complète de l’qubits de non-clonage soit un peu trop technique pour notre discussion ici, la preuve dans le cas où il n’y a pas d’autres auxiliaires se trouve dans notre étendue (les qubits auxiliaires sont qubits utilisés pour l’espace de travail pendant un calcul et sont faciles à utiliser et à gérer dans Q #, consultez [emprunted qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="389f8-228">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="389f8-229">Pour un tel ordinateur Quantum, l’opération de clonage doit être décrite par une matrice d’unités.</span><span class="sxs-lookup"><span data-stu-id="389f8-229">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="389f8-230">Nous interdisent la mesure, car cela corromprait l’État Quantum que nous essayons de cloner.</span><span class="sxs-lookup"><span data-stu-id="389f8-230">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="389f8-231">Pour simuler l’opération de clonage, nous voulons que la matrice d’unités soit utilisée pour que la propriété soit de $ $ U \ket { \Psi } \ket{0 } = \ket { \Psi } { \ket \Psi}</span><span class="sxs-lookup"><span data-stu-id="389f8-231">To simulate the cloning operation, we want the unitary matrix used to have the property that $$ U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
<span data-ttu-id="389f8-232">$ $ pour tout état $ \ket { \Psi } $.</span><span class="sxs-lookup"><span data-stu-id="389f8-232">$$ for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="389f8-233">La propriété de linéarité de la multiplication de matrice implique alors que pour n’importe quel deuxième État Quantum $ \ket { \Phi } $,</span><span class="sxs-lookup"><span data-stu-id="389f8-233">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

<span data-ttu-id="389f8-234">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-234">$$ \begin{align}</span></span>
    <span data-ttu-id="389f8-235">U \left [\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket { \Psi } \right) \right] \ket{0}</span><span class="sxs-lookup"><span data-stu-id="389f8-235">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="389f8-236">& = \frac{1 } {\sqrt{2 } } U \ket { \Phi } \ket{0}</span><span class="sxs-lookup"><span data-stu-id="389f8-236">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="389f8-237">+ \frac{1 } {\sqrt{2 } } U \ket { \Psi } \ket{0 } \\ \\ & = \frac{1 } {\sqrt{2 } } \left (\ket { \Phi } \ket { \Phi } + \ket { \Psi } { \ket \Psi}</span><span class="sxs-lookup"><span data-stu-id="389f8-237">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\ & = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="389f8-238">\right) \\ \\ & \ne \left (\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket { \Psi } \right) \right) \otimes \left (\frac{1 } {\sqrt{2 } } \left (\ket { \Phi } + \ket { \Psi } \right) \right).</span><span class="sxs-lookup"><span data-stu-id="389f8-238">\right) \\\\ & \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
<span data-ttu-id="389f8-239">\end{align}</span><span class="sxs-lookup"><span data-stu-id="389f8-239">\end{align}</span></span>
$$

<span data-ttu-id="389f8-240">Cela fournit l’intuition fondamentale derrière le principe de non-clonage : tout appareil qui copie un État Quantum inconnu doit provoquer des erreurs au moins dans certains États qu’il copie.</span><span class="sxs-lookup"><span data-stu-id="389f8-240">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="389f8-241">Tandis que l’hypothèse clé selon laquelle le cloner agit de manière linéaire sur l’état d’entrée peut être violée par l’ajout et la mesure des qubits auxiliaires, ces interactions fuient également des informations sur le système via les statistiques de mesure et empêchent le clonage exact dans de tels cas.</span><span class="sxs-lookup"><span data-stu-id="389f8-241">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="389f8-242">Pour obtenir une preuve plus complète du titre de non-clonage, consultez [pour plus d’informations](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="389f8-242">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="389f8-243">Le point de vue de la non-clonage est important pour la compréhension qualitative de l’informatique Quantum, car si vous pouviez cloner des États quantiques de façon inonéreuse, vous bénéficiez d’une capacité proche magique d’apprendre à partir des États quantiques.</span><span class="sxs-lookup"><span data-stu-id="389f8-243">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="389f8-244">En effet, vous pourriez violer le principe d’incertitude vaunted de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="389f8-244">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="389f8-245">Vous pouvez également utiliser un Cloner optimal pour obtenir un échantillon unique à partir d’une distribution de Quantum complexe et découvrir tout ce que vous pourriez savoir sur cette distribution à partir d’un seul exemple.</span><span class="sxs-lookup"><span data-stu-id="389f8-245">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="389f8-246">Cela revient à retourner une pièce et à observer des têtes, puis à dire à un ami à propos du résultat où il répond « Ah, la distribution de cette pièce de monnaie doit être de Bernoulli avec $p = 0.512643 \ ldots $ ! »</span><span class="sxs-lookup"><span data-stu-id="389f8-246">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="389f8-247">Une telle instruction serait non sensée, car un peu d’informations (le résultat des têtes) ne peut pas fournir les nombreux éléments d’informations nécessaires pour encoder la distribution sans aucune information préalable substantielle.</span><span class="sxs-lookup"><span data-stu-id="389f8-247">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="389f8-248">De même, sans informations préalables, nous ne pouvons pas parfaitement cloner un État Quantum, de la même façon que nous ne pouvons pas préparer un ensemble de ces pièces, sans connaître $p $ .</span><span class="sxs-lookup"><span data-stu-id="389f8-248">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="389f8-249">Les informations ne sont pas gratuites dans quantum computing.</span><span class="sxs-lookup"><span data-stu-id="389f8-249">Information is not free in quantum computing.</span></span>
<span data-ttu-id="389f8-250">Chaque qubit mesuré fournit un seul bit d’informations et le principe de non-clonage indique qu’il n’existe pas de porte dérobée pouvant être exploitée pour contourner le compromis fondamental entre les informations acquises sur le système et la perturbation invoquée.</span><span class="sxs-lookup"><span data-stu-id="389f8-250">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
