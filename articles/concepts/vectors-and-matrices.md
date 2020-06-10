---
title: Vecteurs et matrices dans l’informatique quantique
description: Découvrez les principes de base de l’utilisation des vecteurs et des matrices.
author: QuantumWriter
uid: microsoft.quantum.concepts.vectors
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
ms.openlocfilehash: 6c09531cd8bee8f5efb472c95c575daed04d3040
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630204"
---
# <a name="vectors-and-matrices"></a><span data-ttu-id="67cd4-103">Vecteurs et matrices</span><span class="sxs-lookup"><span data-stu-id="67cd4-103">Vectors and Matrices</span></span>

<span data-ttu-id="67cd4-104">Une certaine connaissance des vecteurs et des matrices est essentielle pour comprendre l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="67cd4-104">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="67cd4-105">Nous fournissons une brève présentation ci-dessous et les lecteurs intéressés sont recommandés pour lire une référence standard sur l’algèbre linéaire telle que *Strang, G. (1993). Présentation de l’algèbre linéaire (vol. 3). Wellesley, MA : Wellesley-Cambridge Press* ou une référence en ligne telle que [algébrique linéaire](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="67cd4-105">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="67cd4-106">Un vecteur de colonne (ou simplement [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v $ de dimension (ou taille) $n $ est une collection de $ nombres complexes $n $ (V_1, V_2, \ldots, V_n) $ organisée en tant que colonne :</span><span class="sxs-lookup"><span data-stu-id="67cd4-106">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="67cd4-107">$ $v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-107">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-108">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-108">v_1\\\\</span></span>
<span data-ttu-id="67cd4-109">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-109">v_2\\\\</span></span>
<span data-ttu-id="67cd4-110">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-110">\vdots\\\\</span></span>
<span data-ttu-id="67cd4-111">v_n \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="67cd4-111">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="67cd4-112">La norme d’un vecteur $v $ est définie sous la forme $ \sqrt { \sum \_ i | v \_ i | 2 } $.</span><span class="sxs-lookup"><span data-stu-id="67cd4-112">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="67cd4-113">Un vecteur est considéré comme une norme d’unité (ou il est également appelé vecteur d' [*unité*](https://en.wikipedia.org/wiki/Unit_vector)) si sa norme est $1 $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-113">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="67cd4-114">Le [*voisin d’un vecteur*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v $ est indiqué $v ^ \dagger $ et est défini comme étant le vecteur de ligne suivant où $ $ désigne \* le conjugué complexe.</span><span class="sxs-lookup"><span data-stu-id="67cd4-114">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="67cd4-115">$ $ \begin{ bmatrix } V_1 \\ \\ \vdots \\ \\ V_n \end{ bmatrix } ^ \dagger = \begin{ bmatrix } V_1 ^ \* & \cdots & V_n ^ \* \end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="67cd4-115">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="67cd4-116">La méthode la plus courante pour multiplier deux vecteurs ensemble est le [*produit interne*](https://en.wikipedia.org/wiki/Inner_product_space), également connu sous le nom de produit scalaire.</span><span class="sxs-lookup"><span data-stu-id="67cd4-116">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="67cd4-117">Le produit interne donne la projection d’un vecteur sur un autre et est très utile pour décrire comment exprimer un vecteur comme somme d’autres vecteurs plus simples.</span><span class="sxs-lookup"><span data-stu-id="67cd4-117">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="67cd4-118">Le produit interne entre $u $ et $v $ , désigné par $ \left \langle u, v, \right \rangle $ est défini comme</span><span class="sxs-lookup"><span data-stu-id="67cd4-118">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

<span data-ttu-id="67cd4-119">$ $ \langle u, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="67cd4-119">$$ \langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="67cd4-120">Cette notation permet également d’écrire la norme d’un vecteur $v $ sous la forme $ \sqrt { \langle v, v \rangle } $.</span><span class="sxs-lookup"><span data-stu-id="67cd4-120">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="67cd4-121">Nous pouvons multiplier un vecteur par un nombre $c $ pour former un nouveau vecteur dont les entrées sont multipliées par $c $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-121">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="67cd4-122">Nous pouvons également ajouter deux vecteurs $u $ et $v $ pour former un nouveau vecteur dont les entrées sont la somme des entrées de $u $ et $v $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-122">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="67cd4-123">Ces opérations sont décrites ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="67cd4-123">These operations are depicted below:</span></span>

<span data-ttu-id="67cd4-124">$ $ \mathrm{If } ~ u = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-124">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-125">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-125">u_1\\\\</span></span>
<span data-ttu-id="67cd4-126">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-126">u_2\\\\</span></span>
<span data-ttu-id="67cd4-127">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-127">\vdots\\\\</span></span>
<span data-ttu-id="67cd4-128">u_n \end{ bmatrix } ~ \mathrm{and } ~ v = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-128">u_n \end{bmatrix}~\mathrm{and}~ v =\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-129">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-129">v_1\\\\</span></span>
    <span data-ttu-id="67cd4-130">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-130">v_2\\\\</span></span>
    <span data-ttu-id="67cd4-131">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-131">\vdots\\\\</span></span>
    <span data-ttu-id="67cd4-132">V_n \end{ bmatrix } , ~ \mathrm{Then } ~ au + BV = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-132">v_n \end{bmatrix},~\mathrm{then}~ au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-133">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-133">au_1+bv_1\\\\</span></span>
<span data-ttu-id="67cd4-134">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-134">au_2+bv_2\\\\</span></span>
<span data-ttu-id="67cd4-135">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-135">\vdots\\\\</span></span>
<span data-ttu-id="67cd4-136">au_n + bv_n \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="67cd4-136">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="67cd4-137">Une [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de taille $m \times n $ est une collection de $mn $ nombres complexes organisés en $m $ lignes et $n $ colonnes, comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="67cd4-137">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="67cd4-138">$ $M = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-138">$$M = \begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-139">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-139">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="67cd4-140">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {mn } \\ \\ \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="67cd4-140">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\ \end{bmatrix}.$$</span></span>

<span data-ttu-id="67cd4-141">Notez qu’un vecteur de dimension $n $ est simplement une matrice de taille $n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-141">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="67cd4-142">Comme pour les vecteurs, nous pouvons multiplier une matrice par un nombre $c $ pour obtenir une nouvelle matrice où chaque entrée est multipliée par $c $ , et nous pouvons ajouter deux matrices de même taille pour produire une nouvelle matrice dont les entrées sont la somme des entrées respectives des deux matrices.</span><span class="sxs-lookup"><span data-stu-id="67cd4-142">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="67cd4-143">Produits de multiplication de matrice et tenseur</span><span class="sxs-lookup"><span data-stu-id="67cd4-143">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="67cd4-144">Nous pouvons également multiplier deux matrices $M $ de la dimension $m \times n $ et $N $ de dimension $n \times p $ pour obtenir une nouvelle $P de matrice $m $ \times p $ comme suit :</span><span class="sxs-lookup"><span data-stu-id="67cd4-144">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

<span data-ttu-id="67cd4-145">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-145">\begin{align}</span></span>
<span data-ttu-id="67cd4-146">& \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-146">&\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-147">M_ {11 } ~ ~ m_ {12 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ m_ {21 } ~ ~ m_ {22 } ~ ~ \cdots ~ ~ m_ {2n } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-147">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\ M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\ \ddots\\\\</span></span>
    <span data-ttu-id="67cd4-148">M_ {M1 } ~ ~ m_ {m2 } ~ ~ \cdots ~ ~ m_ {mn}</span><span class="sxs-lookup"><span data-stu-id="67cd4-148">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
<span data-ttu-id="67cd4-149">effetbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-149">\end{bmatrix}</span></span>
<span data-ttu-id="67cd4-150">commencerbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-150">\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-151">N_ {11 } ~ ~ n_ {12 } ~ ~ \cdots ~ ~ n_ {1P } \\ \\ n_ {21 } ~ ~ n_ {22 } ~ ~ \cdots ~ ~ n_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-151">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\ N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="67cd4-152">N_ {N1 } ~ ~ n_ {N2 } ~ ~ \cdots ~ ~ n_ {NP}</span><span class="sxs-lookup"><span data-stu-id="67cd4-152">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
<span data-ttu-id="67cd4-153">\end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-153">\end{bmatrix}=\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-154">P_ {11 } ~ ~ P_ {12 } ~ ~ \cdots ~ ~ P_ {1P } \\ \\ P_ {21 } ~ ~ P_ {22 } ~ ~ \cdots ~ ~ P_ {2p } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-154">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\ P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\ \ddots\\\\</span></span>
<span data-ttu-id="67cd4-155">P_ {M1 } ~ ~ P_ {m2 } ~ ~ \cdots ~ ~ P_ {MP}</span><span class="sxs-lookup"><span data-stu-id="67cd4-155">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
<span data-ttu-id="67cd4-156">effetbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-156">\end{bmatrix}</span></span>
<span data-ttu-id="67cd4-157">\end{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-157">\end{align}</span></span>

<span data-ttu-id="67cd4-158">où les entrées de $P $ sont $P _ {ik } = \ sum_j m_ {ij} n_ {JK } $.</span><span class="sxs-lookup"><span data-stu-id="67cd4-158">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="67cd4-159">Par exemple, l’entrée $P _ {11 } $ est le produit interne de la première ligne de $M $ avec la première colonne de $N $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-159">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$.</span></span> <span data-ttu-id="67cd4-160">Notez que dans la mesure où un vecteur est simplement un cas particulier d’une matrice, cette définition s’étend à la multiplication de vecteurs de matrice.</span><span class="sxs-lookup"><span data-stu-id="67cd4-160">Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="67cd4-161">Toutes les matrices que nous considérons sont des matrices carrées, où le nombre de lignes et de colonnes est égal, ou vecteurs, qui correspond uniquement à $1 $ colonne.</span><span class="sxs-lookup"><span data-stu-id="67cd4-161">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="67cd4-162">Une matrice carrée spéciale est la [*matrice d’identité*](https://en.wikipedia.org/wiki/Identity_matrix), dénotée $ \boldone $ , dont tous les éléments diagonales sont égaux à $1 $ et les éléments restants égaux à $0 $ :</span><span class="sxs-lookup"><span data-stu-id="67cd4-162">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

<span data-ttu-id="67cd4-163">$ $ \boldone = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-163">$$\boldone=\begin{bmatrix}</span></span>
<span data-ttu-id="67cd4-164">1 ~ ~ 0 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-164">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="67cd4-165">0 ~ ~ 1 ~ ~ \cdots ~ ~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-165">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="67cd4-166">~ ~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-166">~~ \ddots\\\\</span></span>
<span data-ttu-id="67cd4-167">0 ~ ~ 0 ~ ~ \cdots ~ ~ 1 \end{ bmatrix } . $ $</span><span class="sxs-lookup"><span data-stu-id="67cd4-167">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="67cd4-168">Pour un $A de matrice carrée $ , nous disons qu’une matrice $B $ est son [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) si $AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-168">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="67cd4-169">L’inverse d’une matrice n’a pas besoin d’exister, mais lorsqu’elle existe, elle est unique et nous la dénotarons $A ^ {-1 } $.</span><span class="sxs-lookup"><span data-stu-id="67cd4-169">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="67cd4-170">Pour les $M de matrices $ , la transpose de $M voisine ou conjuguée $ est une matrice $N $ telle que $N _ {IJ } = m_ {ji } ^ \* $.</span><span class="sxs-lookup"><span data-stu-id="67cd4-170">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="67cd4-171">Le voisint de $M $ est généralement indiqué $M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-171">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="67cd4-172">Nous disons qu’un $U de matrice $ est [*unitaire*](https://en.wikipedia.org/wiki/Unitary_matrix) si $uu ^ \dagger = U ^ \dagger U = \boldone $ ou équivalent, $U ^ {-1 } = u ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-172">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="67cd4-173">La propriété la plus importante des matrices unitaires est peut-être qu’elle conserve la norme d’un vecteur.</span><span class="sxs-lookup"><span data-stu-id="67cd4-173">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="67cd4-174">Cela se produit car</span><span class="sxs-lookup"><span data-stu-id="67cd4-174">This happens because</span></span> 

<span data-ttu-id="67cd4-175">$ $ \langle v, v \rangle = v ^ \dagger v = v ^ \dagger U ^ {-1 } u v = v ^ \Dagger u ^ \Dagger u v = \Langle u v, u v \rangle . $ $</span><span class="sxs-lookup"><span data-stu-id="67cd4-175">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="67cd4-176">Une $M de matrice $ est dite [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $M = M ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="67cd4-176">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="67cd4-177">Enfin, le [*produit tenseur*](https://en.wikipedia.org/wiki/Tensor_product) (ou le produit Kronecker) de deux matrices $M $ de taille $m \times n $ et $N $ de taille $p \times q $ est une matrice plus grande $P = M \otimes n $ de taille $mp \times nq $ et est obtenue à partir de $M $ et $N $ comme suit :</span><span class="sxs-lookup"><span data-stu-id="67cd4-177">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

<span data-ttu-id="67cd4-178">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-178">\begin{align}</span></span>
    <span data-ttu-id="67cd4-179">M \otimes N &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-179">M \otimes N &= \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-180">M_ {11 } ~ ~ \cdots ~ ~ m_ {1N } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-180">M_{11} ~~ \cdots ~~ M_{1n} \\\\ \ddots\\\\</span></span>
        <span data-ttu-id="67cd4-181">M_ {M1 } ~ ~ \cdots ~ ~ m_ {mn}</span><span class="sxs-lookup"><span data-stu-id="67cd4-181">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    <span data-ttu-id="67cd4-182">effetbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-182">\end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-183">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-183">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-184">N_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-184">N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="67cd4-185">N_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ}</span><span class="sxs-lookup"><span data-stu-id="67cd4-185">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    <span data-ttu-id="67cd4-186">\end{ bmatrix } \\ \\ &= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-186">\end{bmatrix}\\\\ &= \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-187">M_ {11 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{ bmatrix } ~ ~ \cdots ~ ~ m_ {1N } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{ bmatrix } \\ \\ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="67cd4-187">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\ \ddots\\\\</span></span>
        <span data-ttu-id="67cd4-188">M_ {M1 } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{~ ~ bmatrix } \cdots ~ ~ m_ {mn } \begin{ bmatrix } n_ {11 } ~ ~ \cdots ~ ~ n_ {1t } \\ \\ \ddots \\\\ n_ {P1 } ~ ~ \cdots ~ ~ n_ {PQ } \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-188">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~ M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-189">\end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="67cd4-189">\end{bmatrix}.</span></span>
<span data-ttu-id="67cd4-190">\end{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-190">\end{align}</span></span>

<span data-ttu-id="67cd4-191">Cette solution est mieux illustrée par des exemples :</span><span class="sxs-lookup"><span data-stu-id="67cd4-191">This is better demonstrated with some examples:</span></span>

<span data-ttu-id="67cd4-192">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-192">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-193">a \\ \\ b \end{ bmatrix } \otimes \begin{ bmatrix } c \\ \\ d \\ \\ e \end{ bmatrix } = \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-193">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} = \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-194">\begin{ bmatrix } c \\ \\ d \\ \\ \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-194">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="67cd4-195">\\\\[1.5 em] b \begin{ bmatrix } c \\ \\ d \\ \\ e \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-195">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-196">effetbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-196">\end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-197">= \begin{ bmatrix } a c a \\ \\ d a \\ \\ e \\ \\ b c \\ \\ b is \\ \\ \end {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-197">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="67cd4-198">et</span><span class="sxs-lookup"><span data-stu-id="67cd4-198">and</span></span>

<span data-ttu-id="67cd4-199">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-199">$$ \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-200">a \ b \\ \\ c \ d \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-200">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-201">\otimes \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-201">\otimes \begin{bmatrix}</span></span>
        <span data-ttu-id="67cd4-202">e \ f \\ \\ v \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-202">e\ f\\\\g\ h \end{bmatrix}</span></span>
     <span data-ttu-id="67cd4-203">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-203">= \begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-204">a \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-204">a\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-205">e \ f \\\\ v \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-205">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-206">b \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-206">b\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-207">e \ f \\\\ v \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-207">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-208">\\\\[1em] c \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-208">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-209">e \ f \\\\ v \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-209">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-210">d \begin {bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-210">d\begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-211">e \ f \\\\ v \ h \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-211">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-212">effetbmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-212">\end{bmatrix}</span></span>
    <span data-ttu-id="67cd4-213">= \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="67cd4-213">= \begin{bmatrix}</span></span>
    <span data-ttu-id="67cd4-214">AE \ AF \ est \ BF \\ \\ AG \ Ah \ BG \ BH \\ \\ ce \ CF \ de \ DF \\ \\ CG \ ch \ DG \ DH \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="67cd4-214">ae\ af\ be\ bf \\\\ ag\ ah\ bg\ bh \\\\ ce\ cf\ de\ df \\\\ cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="67cd4-215">La dernière convention de notation utile entourant les produits tenseur est que, pour n’importe quel vecteur $v $ ou $M de matrice $ , $v ^ {\otimes n } $ ou $M ^ {\otimes n } $ est la main pour un $ produit tenseur répété $n.</span><span class="sxs-lookup"><span data-stu-id="67cd4-215">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="67cd4-216">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="67cd4-216">For example:</span></span>

<span data-ttu-id="67cd4-217">\begin{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-217">\begin{align}</span></span>
<span data-ttu-id="67cd4-218">& \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 1 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \qquad \begin { bmatrix } 1 \\ \\ -1 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 1 \\ \\ -1 \\ \\ -1 \\ \\ \end{ bmatrix } , \\ \\ & \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 1 } = \begin{ bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } , \qquad \begin { bmatrix } 0 & 1 \\ \\ 1 & 0 \end{ bmatrix } ^ {\otimes 2 } = \begin{ bmatrix } 0 &0&0&1 0 &0&1&0 0 &\\ \\ \\ \\ 1&0&0 \\\\ 1 &0&0&0 \end { bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="67cd4-218">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\ &\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}    0& 1 \\\\ 1& 0  \end{bmatrix},  \qquad\begin{bmatrix} 0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
<span data-ttu-id="67cd4-219">\end{align}</span><span class="sxs-lookup"><span data-stu-id="67cd4-219">\end{align}</span></span>
