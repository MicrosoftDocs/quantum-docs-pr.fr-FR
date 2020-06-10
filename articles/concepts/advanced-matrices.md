---
title: Concepts de matrices avancés
description: En savoir plus sur les exponentiels vecteurs propres, valeurs propres et Matrix, les outils fondamentaux utilisés pour décrire et simuler des algorithmes Quantum.
author: QuantumWriter
uid: microsoft.quantum.concepts.matrix-advanced
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
ms.openlocfilehash: 8d3c646715f13c454e51b9295cbfdabf6a236ffc
ms.sourcegitcommit: e23178d32b316d05784a02ba3cd6166dad177e89
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84630146"
---
# <a name="advanced-matrix-concepts"></a><span data-ttu-id="f9136-103">Concepts avancés de la matrice</span><span class="sxs-lookup"><span data-stu-id="f9136-103">Advanced Matrix Concepts</span></span> #

<span data-ttu-id="f9136-104">Nous étendons maintenant notre manipulation de matrices à [*valeurs propres, vecteurs propres*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) et [*exponentiels*](https://en.wikipedia.org/wiki/Matrix_exponential) , qui constituent un ensemble fondamental d’outils dont nous avons besoin pour décrire et implémenter des algorithmes Quantum.</span><span class="sxs-lookup"><span data-stu-id="f9136-104">We now extend our manipulation of Matrices to [*Eigenvalues, Eigenvectors*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) and [*Exponentials*](https://en.wikipedia.org/wiki/Matrix_exponential) which form a fundamental set of tools we need to describe and implement quantum algorithms.</span></span>

## <a name="eigenvalues-and-eigenvectors"></a><span data-ttu-id="f9136-105">Valeurs propres et vecteurs propres</span><span class="sxs-lookup"><span data-stu-id="f9136-105">Eigenvalues and Eigenvectors</span></span> ##

<span data-ttu-id="f9136-106">Laissez $M $ être une matrice carrée et $v $ être un vecteur qui n’est pas le vecteur de zéros tous (c’est-à-dire, le vecteur avec toutes les entrées égales à $0 $ ).</span><span class="sxs-lookup"><span data-stu-id="f9136-106">Let $M$ be a square matrix and $v$ be a vector that is not the all zeros vector (i.e., the vector with all entries equal to $0$).</span></span>

<span data-ttu-id="f9136-107">Nous disons que $v $ est un [*extraction*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $M $ si $MV = cv $ pour un nombre $c $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-107">We say $v$ is an [*eigenvector*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) of  $M$ if $Mv = cv$ for some number $c$.</span></span> <span data-ttu-id="f9136-108">Nous disons $c $ est le [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondant à la $v extraction $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-108">We say $c$ is the [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) corresponding to the eigenvector $v$.</span></span> <span data-ttu-id="f9136-109">En général, une matrice $M $ peut transformer un vecteur en un autre vecteur, mais un extraction est spécial, car il reste inchangé, sauf s’il est multiplié par un nombre.</span><span class="sxs-lookup"><span data-stu-id="f9136-109">In general a matrix $M$ may transform a vector into any other vector, but an eigenvector is special because it is left unchanged except for being multiplied by a number.</span></span> <span data-ttu-id="f9136-110">Notez que si $v $ est un extraction avec eigenvalue $c $ , $AV $ est également un extraction (pour toute $a différente de zéro $ ) avec le même eigenvalue.</span><span class="sxs-lookup"><span data-stu-id="f9136-110">Note that if $v$ is an eigenvector with eigenvalue $c$, then $av$ is also an eigenvector (for any nonzero $a$) with the same eigenvalue.</span></span>

<span data-ttu-id="f9136-111">Par exemple, pour la matrice d’identité, chaque vecteur $v $ est un extraction avec eigenvalue $1 $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-111">For example, for the identity matrix, every vector $v$ is an eigenvector with eigenvalue $1$.</span></span>

<span data-ttu-id="f9136-112">En guise d’autre exemple, considérez une [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D $ qui n’a que des entrées autres que zéro sur la diagonale :</span><span class="sxs-lookup"><span data-stu-id="f9136-112">As another example, consider a [*diagonal matrix*](https://en.wikipedia.org/wiki/Diagonal_matrix) $D$ which only has nonzero entries on the diagonal:</span></span>

<span data-ttu-id="f9136-113">$ $ \begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="f9136-113">$$ \begin{bmatrix}</span></span>
<span data-ttu-id="f9136-114">d_1 & 0 & 0 \\ \\ 0 & d_2 & 0 \\ \\ 0 & 0 & D_3 \end{ bmatrix } .</span><span class="sxs-lookup"><span data-stu-id="f9136-114">d_1 & 0 & 0 \\\\ 0 & d_2 & 0 \\\\ 0 & 0 & d_3 \end{bmatrix}.</span></span>
$$

<span data-ttu-id="f9136-115">Les vecteurs</span><span class="sxs-lookup"><span data-stu-id="f9136-115">The vectors</span></span>

<span data-ttu-id="f9136-116">$ $ \begin{ bmatrix } 1 \\ \\ 0 \\ \\ 0 \end{ bmatrix } , \begin{ bmatrix } 0 \\ \\ 1 \\ \\ 0 \end { bmatrix } et \begin{ bmatrix } 0 \\ \\ 0 \\ \\ 1 \end {bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="f9136-116">$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix}, \begin{bmatrix}0 \\\\ 1 \\\\ 0\end{bmatrix} and \begin{bmatrix}0 \\\\ 0 \\\\ 1\end{bmatrix}$$</span></span>

<span data-ttu-id="f9136-117">sont vecteurs propres de cette matrice avec valeurs propres $d _ 1 $ , $d _2 $ et $d _3 $ , respectivement.</span><span class="sxs-lookup"><span data-stu-id="f9136-117">are eigenvectors of this matrix with eigenvalues  $d_1$, $d_2$, and $d_3$, respectively.</span></span> <span data-ttu-id="f9136-118">Si $d _ 1 $ , $d _2 $ et $d _3 $ sont des nombres distincts, ces vecteurs (et leurs multiples) sont les seuls vecteurs propres de la matrice $D $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-118">If $d_1$, $d_2$, and $d_3$ are distinct numbers, then these vectors (and their multiples) are the only eigenvectors of the matrix $D$.</span></span> <span data-ttu-id="f9136-119">En général, pour une matrice diagonale, il est facile de lire les valeurs propres et les vecteurs propres.</span><span class="sxs-lookup"><span data-stu-id="f9136-119">In general, for a diagonal matrix it is easy to read off the eigenvalues and eigenvectors.</span></span> <span data-ttu-id="f9136-120">Les valeurs propres sont tous des nombres apparaissant sur la diagonale, et leurs vecteurs propres respectifs sont les vecteurs d’unité avec une entrée égale à $1 $ et les entrées restantes égales à $0 $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-120">The eigenvalues are all the numbers appearing on the diagonal, and their respective eigenvectors are the unit vectors with one entry equal to $1$ and the remaining entries equal to $0$.</span></span>

<span data-ttu-id="f9136-121">Notez dans l’exemple ci-dessus que le vecteurs propres de $D $ forment une base pour les $ vecteurs $3 dimensionnels.</span><span class="sxs-lookup"><span data-stu-id="f9136-121">Note in the above example that the eigenvectors of $D$ form a basis for $3$-dimensional vectors.</span></span> <span data-ttu-id="f9136-122">Une base est un ensemble de vecteurs, de sorte que tout vecteur peut être écrit comme une combinaison linéaire de ces vecteurs.</span><span class="sxs-lookup"><span data-stu-id="f9136-122">A basis is a set of vectors such that any vector can be written as a linear combination of them.</span></span> <span data-ttu-id="f9136-123">Plus explicitement, $v _ 1 $ , $v _2 $ et $v _3 $ forment une base si une $v $ de vecteur peut être écrite en tant que $v = A_1 V_1 + a_2 V_2 + A_3 v_3 $ pour certains nombres $a _ 1 $ , $a _2 $ et $a _3 $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-123">More explicitly, $v_1$, $v_2$, and $v_3$ form a basis if any vector $v$ can be written as $v=a_1 v_1 + a_2 v_2 + a_3 v_3$ for some numbers $a_1$, $a_2$, and $a_3$.</span></span>

<span data-ttu-id="f9136-124">Rappelez-vous qu’une matrice Hermitian (également appelée autojoint) est une matrice carrée complexe égale à son propre conjugué complexe, tandis qu’une matrice d’unités est une matrice carrée complexe dont l’inverse est égal à son conjugué complexe.</span><span class="sxs-lookup"><span data-stu-id="f9136-124">Recall that a Hermitian matrix (also called self-adjoint) is a complex square matrix equal to its own complex conjugate, while a unitary matrix is a complex square matrix whose inverse is equal to its complex conjugate.</span></span>
<span data-ttu-id="f9136-125">Pour les matrices Hermitian et Unit, qui sont essentiellement les seules matrices rencontrées dans Quantum Computing, il existe un résultat général connu sous le nom d’un type d’unité de commande [*spectrale*](https://en.wikipedia.org/wiki/Spectral_theorem), qui déclare les éléments suivants : pour une matrice de Hermitian ou d’unité $M $ , il existe un $U unitaire, $ $M = u ^ \dagger D $ pour certains $D de matrice diagonale $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-125">For Hermitian and unitary matrices, which are essentially the only matrices encountered in quantum computing, there is a general result known as the [*spectral theorem*](https://en.wikipedia.org/wiki/Spectral_theorem), which asserts the following: For any Hermitian or unitary matrix $M$, there exists a unitary $U$ such that $M=U^\dagger D U$ for some diagonal matrix $D$.</span></span> <span data-ttu-id="f9136-126">En outre, les entrées diagonales de $D $ seront valeurs propres de $M $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-126">Furthermore, the diagonal entries of $D$ will be the eigenvalues of $M$.</span></span>

<span data-ttu-id="f9136-127">Nous savons déjà comment calculer le valeurs propres et le vecteurs propres d’une matrice diagonale $D $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-127">We already know how to compute the eigenvalues and eigenvectors of a diagonal matrix $D$.</span></span> <span data-ttu-id="f9136-128">À l’aide de cette aide, nous savons que si $v $ est un extraction de $D $ avec eigenvalue $c $ , c’est-à-dire $DV = CV $ , $U ^ \dagger v sera $ un extraction de $M $ avec eigenvalue $c $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-128">Using this theorem we know that if $v$ is an eigenvector of $D$ with eigenvalue $c$, i.e., $Dv = cv$, then $U^\dagger v$ will be an eigenvector of $M$ with eigenvalue $c$.</span></span> <span data-ttu-id="f9136-129">Cela est dû au fait que</span><span class="sxs-lookup"><span data-stu-id="f9136-129">This is because</span></span>

<span data-ttu-id="f9136-130">$ $M (U ^ \dagger v) = U ^ \dagger D U (U ^ \dagger v) = U ^ \dagger D (U U ^ \dagger) v = U ^ \dagger D v = c U ^ \dagger v. $ $</span><span class="sxs-lookup"><span data-stu-id="f9136-130">$$M(U^\dagger v) = U^\dagger D U  (U^\dagger v) =U^\dagger D (U  U^\dagger) v = U^\dagger D v = c U^\dagger v.$$</span></span>

## <a name="matrix-exponentials"></a><span data-ttu-id="f9136-131">Exponentiels de la matrice</span><span class="sxs-lookup"><span data-stu-id="f9136-131">Matrix Exponentials</span></span>
<span data-ttu-id="f9136-132">Une [*matrice exponentielle*](https://en.wikipedia.org/wiki/Matrix_exponential) peut également être définie en analogie exacte avec la fonction exponentielle.</span><span class="sxs-lookup"><span data-stu-id="f9136-132">A [*matrix exponential*](https://en.wikipedia.org/wiki/Matrix_exponential) can also be defined in exact analogy to the exponential function.</span></span>  <span data-ttu-id="f9136-133">La matrice exponentielle d’un $A de matrice $ peut être exprimée sous la forme</span><span class="sxs-lookup"><span data-stu-id="f9136-133">The matrix exponential of a matrix $A$ can be expressed as</span></span>

<span data-ttu-id="f9136-134">$ $ e ^ A = \boldone + a + \frac{A ^ 2 } {2 !} + \frac{A ^ 3 } {3 !} + \cdots $ $</span><span class="sxs-lookup"><span data-stu-id="f9136-134">$$ e^A=\boldone + A + \frac{A^2}{2!}+\frac{A^3}{3!}+\cdots $$</span></span>

<span data-ttu-id="f9136-135">Cela est important, car l’évolution du temps de Quantum mécanique est décrite par une matrice d’unités sous la forme $e ^ {iB } $ pour la matrice Hermitian $B $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-135">This is important because quantum mechanical time evolution is described by a unitary matrix of the form $e^{iB}$ for Hermitian matrix $B$.</span></span>  <span data-ttu-id="f9136-136">C’est la raison pour laquelle l’exécution de la matrice exponentielles est une partie fondamentale de l’informatique Quantum et, comme Q #, elle offre des routines intrinsèques pour décrire ces opérations.</span><span class="sxs-lookup"><span data-stu-id="f9136-136">For this reason, performing matrix exponentials is a fundamental part of quantum computing and as such Q# offers intrinsic routines for describing these operations.</span></span>
<span data-ttu-id="f9136-137">Il existe de nombreuses façons de calculer un exponentiel de matrice sur un ordinateur classique, et en général, une approximation approximative d’un tel exponentiel est chargée avec les risques.</span><span class="sxs-lookup"><span data-stu-id="f9136-137">There are many ways in practice to compute a matrix exponential on a classical computer, and in general numerically approximating such an exponential is fraught with peril.</span></span>  <span data-ttu-id="f9136-138">Consultez [*Cleve mole et Charles Van Loan. « Dix-neuf façons douteuse de calculer l’exponentiel d’une matrice. » SIAM révision 20,4 (1978) : 801-836*](https://doi.org/10.1137/S00361445024180) pour plus d’informations sur les défis impliqués.</span><span class="sxs-lookup"><span data-stu-id="f9136-138">See [*Cleve Moler and Charles Van Loan. "Nineteen dubious ways to compute the exponential of a matrix." SIAM review 20.4 (1978): 801-836*](https://doi.org/10.1137/S00361445024180) for more information about the challenges involved.</span></span>

<span data-ttu-id="f9136-139">Le moyen le plus simple de comprendre comment calculer l’exponentiel d’une matrice consiste à utiliser les valeurs propres et les vecteurs propres de cette matrice.</span><span class="sxs-lookup"><span data-stu-id="f9136-139">The easiest way to understand how to compute the exponential of a matrix is through the eigenvalues and eigenvectors of that matrix.</span></span>  <span data-ttu-id="f9136-140">Plus précisément, le point de vue spectral évoqué ci-dessus indique que pour chaque Hermitian ou matrice d’unités $A $ il existe une matrice d’unités $U $ et une matrice diagonale $D $ telle que $A = u ^ \dagger D $ .  En raison des propriétés de unitarity, nous avons $A ^ 2 = U ^ \dagger D ^ 2 U $ et de la même façon pour toute $p d’alimentation $ $A ^ p = u ^ \dagger D ^ p u $ .  Si nous le remplaçons par la définition d’opérateur de l’opérateur exponentiel, nous obtenons :</span><span class="sxs-lookup"><span data-stu-id="f9136-140">Specifically, the spectral theorem discussed above says that for every Hermitian or unitary matrix $A$ there exists a unitary matrix $U$ and a diagonal matrix $D$ such that $A=U^\dagger D U$.  Because of the properties of unitarity we have that $A^2 = U^\dagger D^2 U$ and similarly for any power $p$ $A^p = U^\dagger D^p U$.  If we substitute this into the operator definition of the operator exponential we obtain:</span></span>

<span data-ttu-id="f9136-141">$ $ e ^ A = U ^ \dagger \left (\boldone + D + \frac{D ^ 2 } {2 !} + \cdots \right) U = u ^ \dagger \begin{ bmatrix } \exp (d_ {11 } ) & 0 & \cdots &0 \\\\ 0 & \exp (d_ {22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0&0 & \cdots & \exp (d_ {NN } ) \end{ bmatrix } U. $ $</span><span class="sxs-lookup"><span data-stu-id="f9136-141">$$ e^A= U^\dagger \left(\boldone +D +\frac{D^2}{2!}+\cdots \right)U= U^\dagger \begin{bmatrix}\exp(D_{11}) & 0 &\cdots &0\\\\ 0 & \exp(D_{22})&\cdots& 0\\\\ \vdots &\vdots &\ddots &\vdots\\\\ 0&0&\cdots&\exp(D_{NN}) \end{bmatrix} U. $$</span></span>

<span data-ttu-id="f9136-142">En d’autres termes, si vous transformez le eigenbasis de la matrice $A le $ calcul de la matrice exponentielle est équivalent au calcul de la valeur exponentielle ordinaire du valeurs propres de la matrice.</span><span class="sxs-lookup"><span data-stu-id="f9136-142">In other words, if you transform to the eigenbasis of the matrix $A$ then computing the matrix exponential is equivalent to computing the ordinary exponential of the eigenvalues of the matrix.</span></span>  <span data-ttu-id="f9136-143">Dans la mesure où de nombreuses opérations dans quantum computing impliquent l’exécution de matrices exponentielles, cette astuce de transformation en eigenbasis d’une matrice pour simplifier l’exécution de l’opérateur exponentiel apparaît fréquemment et constitue la base de nombreux algorithmes Quantum tels que les méthodes de simulation de quantum de type Trotter – Suzuki décrites plus loin dans ce guide.</span><span class="sxs-lookup"><span data-stu-id="f9136-143">As many operations in quantum computing involve performing matrix exponentials, this trick of transforming into the eigenbasis of a matrix to simplify performing the operator exponential appears frequently and is the basis behind many quantum algorithms such as Trotter–Suzuki-style quantum simulation methods discussed later in this guide.</span></span>

<span data-ttu-id="f9136-144">Une autre propriété utile est si $B $ est unitaire et Hermitian, c’est-à-dire $B = B ^ {-1 } = b ^ \dagger $ puis $B ^ 2 = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="f9136-144">Another useful property is if $B$ is both unitary and Hermitian, i.e., $B=B^{-1}=B^\dagger$ then $B^2=\boldone$.</span></span> <span data-ttu-id="f9136-145">En appliquant cette règle à l’expansion ci-dessus de la matrice exponentielle et en regroupant les termes $ \boldone $ et $B $ ensemble, vous pouvez constater que pour n’importe quelle valeur réelle $x $ l’identité</span><span class="sxs-lookup"><span data-stu-id="f9136-145">By applying this rule to the above expansion of the matrix exponential and by grouping the $\boldone$ and the $B$ terms together, it can be see that for any real value $x$ the identity</span></span>

<span data-ttu-id="f9136-146">$ $e ^ {iBx } = \boldone \cos (x) + iB\sin (x) $ $</span><span class="sxs-lookup"><span data-stu-id="f9136-146">$$e^{iBx}=\boldone \cos(x)+ iB\sin(x)$$</span></span>


<span data-ttu-id="f9136-147">comprend.</span><span class="sxs-lookup"><span data-stu-id="f9136-147">holds.</span></span> <span data-ttu-id="f9136-148">Cette astuce est particulièrement utile, car elle permet de tenir compte des actions exponentielles de la matrice, même si la dimension de $B $ est exponentiellement importante, dans le cas particulier où $B est à la $ fois uniténelle et Hermitian.</span><span class="sxs-lookup"><span data-stu-id="f9136-148">This trick is especially useful because it allows to reason about the actions matrix exponentials have, even if the dimension of $B$ is exponentially large, for the special case when $B$ is both unitary and Hermitian.</span></span>
