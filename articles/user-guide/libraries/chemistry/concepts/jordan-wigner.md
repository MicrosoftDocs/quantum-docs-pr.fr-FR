---
title: Jordanie-représentation Wigner
description: En savoir plus sur la représentation Jordanie-Wigner, qui met en correspondance les opérateurs Hamilton et les matrices unitaires qui peuvent être plus facilement implémentées sur un ordinateur quantique.
author: nathanwiebe2
ms.author: nawiebe@microsoft.com
ms.date: 10/09/2017
ms.topic: article-type-from-white-list
uid: microsoft.quantum.chemistry.concepts.jordanwigner
ms.openlocfilehash: 17cb473c6d33e3356d5da886f47985c3828d4d1f
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85275099"
---
# <a name="jordan-wigner-representation"></a><span data-ttu-id="62f68-103">Jordanie-représentation Wigner</span><span class="sxs-lookup"><span data-stu-id="62f68-103">Jordan-Wigner Representation</span></span>

<span data-ttu-id="62f68-104">Tandis que les deuxième Hamiltonians quantifiés sont facilement représentées en termes de $a ^ \dagger $ (création) et $a $ (annihilation), ces opérations ne sont pas des opérations fondamentales sur les ordinateurs quantiques.</span><span class="sxs-lookup"><span data-stu-id="62f68-104">While second quantized Hamiltonians are conveniently represented in terms of $a^\dagger$ (creation) and $a$ (annihilation), these operations are not fundamental operations in quantum computers.</span></span>
<span data-ttu-id="62f68-105">Par conséquent, si nous souhaitons qu’il les implémente sur un ordinateur quantique, nous devons mapper les opérateurs aux matrices unitaires qui peuvent être implémentées sur un ordinateur quantique.</span><span class="sxs-lookup"><span data-stu-id="62f68-105">As a result, if we wish it implement them on a quantum computer we need to map the operators to unitary matrices that can be implemented on a quantum computer.</span></span>
<span data-ttu-id="62f68-106">La représentation Jordanie – Wigner fournit une telle carte.</span><span class="sxs-lookup"><span data-stu-id="62f68-106">The Jordan–Wigner representation gives one such map.</span></span>
<span data-ttu-id="62f68-107">Toutefois, d’autres, telles que la représentation Bravyi – kitaev, existent également et présentent leurs propres avantages et inconvénients.</span><span class="sxs-lookup"><span data-stu-id="62f68-107">However, others such as the Bravyi–Kitaev representation also exist and have their own relative advantages and disadvantages.</span></span>
<span data-ttu-id="62f68-108">Le principal avantage de la représentation Jordanie-Wigner est sa simplicité.</span><span class="sxs-lookup"><span data-stu-id="62f68-108">The main advantage of the Jordan-Wigner representation is its simplicity.</span></span>

<span data-ttu-id="62f68-109">La représentation Jordanie-Wigner est simple à dériver.</span><span class="sxs-lookup"><span data-stu-id="62f68-109">The Jordan-Wigner representation is straight forward to derive.</span></span>
<span data-ttu-id="62f68-110">Rappelez-vous qu’un État $ \ket {0} _J $ implique que spin orbital $j $ est vide et $ \ket {1} _J $ signifie qu’il est occupé.</span><span class="sxs-lookup"><span data-stu-id="62f68-110">Recall that a state $\ket{0}_j$ implies that spin orbital $j$ is empty and $\ket{1}_j$ implies that it is occupied.</span></span>
<span data-ttu-id="62f68-111">Cela signifie que qubits peut naturellement stocker l’occupation d’un spin orbital donné.</span><span class="sxs-lookup"><span data-stu-id="62f68-111">This means that qubits can naturally store the occupation of a given spin orbital.</span></span>
<span data-ttu-id="62f68-112">Nous avons ensuite cette $a ^ \ dagger_j \ket {0} _J = \ket {1} _J $ et $a ^ \ dagger_j \ket {1} _J = $0.</span><span class="sxs-lookup"><span data-stu-id="62f68-112">We then have that $a^\dagger_j \ket{0}_j = \ket{1}_j$ and $a^\dagger_j \ket{1}_j = 0$.</span></span>
<span data-ttu-id="62f68-113">Il est facile de vérifier que \begin{align} a ^ \ dagger_j &= \begin{bmatrix}0 & 0 \\ \ 1 &0 \end{bmatrix} = \frac{X_j-iY_j} {2} , \nonumber \\ \\ a_j &= \begin{bmatrix}0 & 1 \\ \ 0 &0 \end{bmatrix} = \frac{X_j + iY_j} {2} , \end{align} où $X _J $ et $Y _J $ sont les opérateurs Pauli-$X $ et-$Y $ agissant sur qubit $j $.</span><span class="sxs-lookup"><span data-stu-id="62f68-113">It is easy to verify that \begin{align} a^\dagger_j &= \begin{bmatrix}0 & 0 \\\ 1 &0 \end{bmatrix}=\frac{X_j - iY_j}{2}, \nonumber\\\\ a_j &= \begin{bmatrix}0 & 1 \\\ 0 &0 \end{bmatrix}=\frac{X_j + iY_j}{2}, \end{align} where $X_j$ and $Y_j$ are the Pauli-$X$ and -$Y$ operators acting on qubit $j$.</span></span>

>[!NOTE]
> <span data-ttu-id="62f68-114">Dans Q # l’État $ \ket {0} $ représente le + 1 eigenstate de l’opérateur $Z $.</span><span class="sxs-lookup"><span data-stu-id="62f68-114">In Q# the $\ket{0}$ state represents the +1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="62f68-115">Dans certaines zones de physique, $ \ket {0} $ représente l’état de la terre faible-énergie et donc la-1 eigenstate de l' $Z $ Operator.</span><span class="sxs-lookup"><span data-stu-id="62f68-115">In some areas of physics $\ket{0}$ represents the low-energy ground state and thus the -1 eigenstate of the $Z$ operator.</span></span> <span data-ttu-id="62f68-116">Par conséquent, certaines formules peuvent différer de la documentation populaire.</span><span class="sxs-lookup"><span data-stu-id="62f68-116">Therefore some formulas might differ from popular literature.</span></span>

<span data-ttu-id="62f68-117">Dans la bibliothèque chimie, nous utilisons $ \ket {0} $ pour représenter un spin-orbital inoccupé.</span><span class="sxs-lookup"><span data-stu-id="62f68-117">In the chemistry library we use $\ket{0}$ to represent an unoccupied spin-orbital.</span></span>
<span data-ttu-id="62f68-118">Cela montre que pour un seul spin orbital, il est facile de représenter des opérateurs de création et de annihilation en termes de matrices unitaires que les ordinateurs quantiques comprennent.</span><span class="sxs-lookup"><span data-stu-id="62f68-118">This shows that for a single spin orbital it is easy to represent creation and annihilation operators in terms of unitary matrices that quantum computers understand.</span></span>
<span data-ttu-id="62f68-119">Notez que si $X $ et $Y $ sont des $a unitaires ^ \dagger $ et $a $ ne le sont pas.</span><span class="sxs-lookup"><span data-stu-id="62f68-119">Note that while $X$ and $Y$ are unitary $a^\dagger$ and $a$ are not.</span></span>
<span data-ttu-id="62f68-120">Nous verrons plus tard que cela ne pose pas de problème pour la simulation.</span><span class="sxs-lookup"><span data-stu-id="62f68-120">We will see later that this does not pose a challenge for simulation.</span></span>

<span data-ttu-id="62f68-121">L’un des problèmes restants, c’est que même si la construction ci-dessus fonctionne pour un seul spin orbital, elle échoue pour les systèmes avec deux orbites ou plus.</span><span class="sxs-lookup"><span data-stu-id="62f68-121">One problem that remains is that while the above construction works for a single spin orbital, it fails for systems with two or more spin orbitals.</span></span>
<span data-ttu-id="62f68-122">Étant donné que fermions est antisymmetic, nous savons que $a ^ \ dagger_j un ^ \ dagger_k =-a ^ \ dagger_k a ^ \ dagger_j $ pour tout $j $ et $k $.</span><span class="sxs-lookup"><span data-stu-id="62f68-122">Since Fermions are antisymmetic, we know that $a^\dagger_j a^\dagger_k = - a^\dagger_k a^\dagger_j$ for any $j$ and $k$.</span></span>
<span data-ttu-id="62f68-123">Toutefois, $ $ \left (\frac{X_j-iY_j} {2} \right) \left (\frac{X_k-iY_k} {2} \right) = \left (\frac{X_k-iY_k} {2} \right) \left (\frac{X_j-iY_j} {2} \right).</span><span class="sxs-lookup"><span data-stu-id="62f68-123">However, $$ \left(\frac{X_j - iY_j}{2}\right)\left(\frac{X_k - iY_k}{2}\right) = \left(\frac{X_k - iY_k}{2}\right) \left(\frac{X_j - iY_j}{2}\right).</span></span>
<span data-ttu-id="62f68-124">$ $ En d’autres termes, les deux opérateurs de création ne sont pas anti-muets si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="62f68-124">$$ In other words, the two creation operators do not anti-commute as required.</span></span>
<span data-ttu-id="62f68-125">Cela peut être résolu de manière simple, si ce n’est pas élégant.</span><span class="sxs-lookup"><span data-stu-id="62f68-125">This can be remedied though in a straightforward, if inelegant fashion.</span></span>
<span data-ttu-id="62f68-126">Le correctif est de noter que les opérateurs Pauli sont naturellement anti-muet.</span><span class="sxs-lookup"><span data-stu-id="62f68-126">The fix is to note that Pauli operators naturally anti-commute.</span></span>
<span data-ttu-id="62f68-127">En particulier, $XZ =-ZX $ et $YZ =-ZY $.</span><span class="sxs-lookup"><span data-stu-id="62f68-127">In particular, $XZ = -ZX$ and $YZ=-ZY$.</span></span>
<span data-ttu-id="62f68-128">Par conséquent, par interspersing $Z $ Operators dans la construction de l’opérateur, nous pouvons émuler l’anti-mutation correcte.</span><span class="sxs-lookup"><span data-stu-id="62f68-128">Thus, by interspersing $Z$ operators into the construction of the operator, we can emulate the correct anti-commutation.</span></span>
<span data-ttu-id="62f68-129">La construction complète est la suivante :</span><span class="sxs-lookup"><span data-stu-id="62f68-129">The full construction is as follows:</span></span> 

<span data-ttu-id="62f68-130">\begin{align} a ^ \ dagger_1 &= \left (\frac{X-iY} {2} \right) \otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1, \\ \\ un ^ \ dagger_2 &= Z\otimes\left (\frac{X-Iy} {2} \right) \otimes 1 \ otimes 1 \otimes \cdots \otimes 1, \\ \\ a ^ \ dagger_3 &= Z\otimes Z\otimes \left (\frac{X-Iy} \right {2} ) \otimes 1 \otimes \cdots \otimes 1, \\ \\ & \Vdots \\ \\ a ^ \ dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left (\frac{X-Iy} {2} \right).</span><span class="sxs-lookup"><span data-stu-id="62f68-130">\begin{align} a^\dagger_1 &= \left(\frac{X-iY}{2}\right)\otimes 1 \otimes 1 \otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_2 &= Z\otimes\left(\frac{X-iY}{2}\right)\otimes 1\otimes 1 \otimes \cdots \otimes 1,\\\\ a^\dagger_3 &= Z\otimes Z\otimes \left(\frac{X-iY}{2}\right)\otimes 1 \otimes \cdots \otimes 1,\\\\ &\vdots\\\\ a^\dagger_N &= Z\otimes Z\otimes Z\otimes Z \otimes \cdots \otimes Z\otimes \left(\frac{X-iY}{2}\right).</span></span> <span data-ttu-id="62f68-131">\label{EQ : JW} \end{align}</span><span class="sxs-lookup"><span data-stu-id="62f68-131">\label{eq:JW} \end{align}</span></span>

<span data-ttu-id="62f68-132">Il est également pratique d’exprimer les opérateurs numériques, $n _j $, en termes d’opérateurs Pauli.</span><span class="sxs-lookup"><span data-stu-id="62f68-132">It is also convenient to express the number operators, $n_j$, in terms of Pauli operators.</span></span>
<span data-ttu-id="62f68-133">Heureusement, les chaînes de $Z $ Operators (appelées chaînes Jordanie-Wigner) annulent à l’issue de cette substitution.</span><span class="sxs-lookup"><span data-stu-id="62f68-133">Thankfully, the strings of $Z$ operators (known as Jordan-Wigner strings) cancel after one makes this substitution.</span></span>
<span data-ttu-id="62f68-134">Après avoir effectué cette sortie (et rappelant que $X _jY_j = iZ_j $), nous avons \begin{Equation} n_j = a ^ \ dagger_j a_j = \frac{(1-Z_j)} {2} .</span><span class="sxs-lookup"><span data-stu-id="62f68-134">After carrying this out (and recalling that $X_jY_j=iZ_j$), we have \begin{equation} n_j = a^\dagger_j a_j = \frac{(1-Z_j)}{2}.</span></span>
<span data-ttu-id="62f68-135">\end{equation}</span><span class="sxs-lookup"><span data-stu-id="62f68-135">\end{equation}</span></span>


## <a name="constructing-hamiltonians-in-jordan-wigner-representation"></a><span data-ttu-id="62f68-136">Construction de Hamiltonians dans la représentation Jordanie-Wigner</span><span class="sxs-lookup"><span data-stu-id="62f68-136">Constructing Hamiltonians in Jordan-Wigner Representation</span></span>

<span data-ttu-id="62f68-137">Une fois que nous avons appelé la représentation Jordanie-Wigner qui traduit le Hamilton en une somme d’opérateurs Pauli est simple.</span><span class="sxs-lookup"><span data-stu-id="62f68-137">Once we have invoked the Jordan-Wigner representation translating the Hamiltonian to a sum of Pauli operators is straight forward.</span></span>
<span data-ttu-id="62f68-138">Il suffit de remplacer chacun des opérateurs $a ^ \dagger $ et $a $ dans le Fermionic Hamilton par les chaînes des opérateurs Pauli ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="62f68-138">One simply has to replace each of the $a^\dagger$ and $a$ operators in the Fermionic Hamiltonian with the strings of Pauli-operators given above.</span></span>
<span data-ttu-id="62f68-139">Lorsqu’une de ces substitutions est effectuée, il n’y a que cinq classes de termes au sein de la partie Hamilton.</span><span class="sxs-lookup"><span data-stu-id="62f68-139">When one performs this substitution, there are only five classes of terms within the Hamiltonian.</span></span>
<span data-ttu-id="62f68-140">Ces cinq classes correspondent aux différentes façons dont nous pouvons choisir les $p, q $ et $p, q, r, s $ dans le corps et les deux termes dans le même corps.</span><span class="sxs-lookup"><span data-stu-id="62f68-140">These five classes correspond to the different ways we can pick the $p,q$ and $p,q,r,s$ in the one-body and the two-body terms in the Hamiltonian.</span></span>
<span data-ttu-id="62f68-141">Ces cinq classes, pour le cas où $p>q>r>s $ et des orbites à valeur réelle, sont</span><span class="sxs-lookup"><span data-stu-id="62f68-141">These five classes, for the case where $p>q>r>s$ and real-valued orbitals, are</span></span>

<span data-ttu-id="62f68-142">\begin{align} H_ {pp} a_p ^ \dagger a_p &= \ sum_p \frac{H_ {pp}} {2} (1-Z_p) \\ \\ H_ {PQ} (a_p ^ \dagger a_q + a ^ \ dagger_q a_p) &= \frac{H_ {PQ}} {2} \left (\ prod_ {j = q + 1} ^ {p-1} Z_j \right) \left (X_pX_q + Y_pY_q \right) \\ \\ H_ {pqqp} n_P n_q &= \frac{H_ {pqqp}} {4} \left (1-Z_p-Z_q + Z_pZ_q \right) \\ \\ H_ {pqqr} &= \frac{H_ {pqqr}} {2} \left (\ prod_ {j = r + 1} ^ {p-1} Z_j \right) \left (X_pX_r + Y_pY_r \right) \left (\frac{1-Z_q} {2} \right) \\ \\ H_ {PQRS} &= \frac{H_ {PQRS}} {8} \ prod_ {j = s + 1} ^ {r-1} Z_j \ prod_ {k = q + 1} ^ {p-1} Z_k \big (xxxx-xxyy + XYXY\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + YXXY + YXYX-YYXX\nonumber \\ \\ & \qquad\qquad\qquad\qquad\qquad + XYYX + YYYY\Big) \end{align}</span><span class="sxs-lookup"><span data-stu-id="62f68-142">\begin{align} h_{pp}a_p^\dagger a_p &= \sum_p \frac{h_{pp}}{2}(1 - Z_p)\\\\ h_{pq}(a_p^\dagger a_q + a^\dagger_q a_p) &= \frac{h_{pq}}{2}\left(\prod_{j=q+1}^{p-1} Z_j \right)\left( X_pX_q + Y_pY_q\right)\\\\ h_{pqqp} n_p n_q &=  \frac{h_{pqqp}}{4}\left(1-Z_p - Z_q +Z_pZ_q \right)\\\\ H_{pqqr} &= \frac{h_{pqqr}}{2}\left(\prod_{j=r+1}^{p-1} Z_j \right)\left( X_pX_r + Y_pY_r\right)\left(\frac{1-Z_q}{2}\right)\\\\ H_{pqrs} &= \frac{h_{pqrs}}{8}\prod_{j=s+1}^{r-1} Z_j\prod_{k=q+1}^{p-1} Z_k \Big(XXXX - XXYY+XYXY\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+YXXY+YXYX-YYXX\nonumber\\\\ &\qquad\qquad\qquad\qquad\qquad+XYYX+YYYY\Big) \end{align}</span></span>

<span data-ttu-id="62f68-143">Bien que la génération de tels Hamiltonians uniquement nécessite l’application de ces règles de remplacement, cela serait irréalisable pour les molécules de grande taille qui peuvent se composer de millions de termes de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="62f68-143">While generating such Hamiltonians by hand only requires applying these replacement rules, doing so would be infeasible for large molecules which can consist of millions of Hamiltonian terms.</span></span>
<span data-ttu-id="62f68-144">En guise d’alternative, nous pouvons construire automatiquement le à `JordanWignerEncoding` partir `FermionHamiltonian` d’une représentation du lieu de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="62f68-144">As an alternative, we can automatically construct the `JordanWignerEncoding` given a `FermionHamiltonian` representation of the Hamiltonian.</span></span>

```csharp
    // We load the namespace containing fermion and Pauli objects. 
    using Microsoft.Quantum.Chemistry.Fermion;
    using Microsoft.Quantum.Chemistry.Pauli;
    
    // We create an example `FermionHamiltonian` instance.
    var fermionHamiltonian = new FermionHamiltonian();

    // We convert this Fermion Hamiltonian to a Jordan-Wigner representation.
    var jordanWignerEncoding = fermionHamiltonian.ToPauliHamiltonian(QubitEncoding.JordanWigner);
```

<span data-ttu-id="62f68-145">Une fois les Hamiltonians construits sous cette forme, nous pouvons utiliser un hôte d’algorithmes de simulation quantique pour compiler la dynamique générée par $e ^ {-iHt} $ dans une séquence de portes élémentaires (dans une certaine tolérance d’erreur définissable par l’utilisateur).</span><span class="sxs-lookup"><span data-stu-id="62f68-145">Once the Hamiltonians are constructed in this form, we can use a host of quantum simulation algorithms to compile the dynamics generated by $e^{-iHt}$ into a sequence of elementary gates (within some user definable error tolerance).</span></span>
<span data-ttu-id="62f68-146">Nous aborderons les deux méthodes les plus populaires pour les formules de simulation quantique, qubitization et Trotter – Suzuki, dans la documentation algorithmique.</span><span class="sxs-lookup"><span data-stu-id="62f68-146">We discuss the two most popular methods for quantum simulation, qubitization and Trotter–Suzuki formulas, in the algorithmic documentation.</span></span> <span data-ttu-id="62f68-147">Nous fournissons des implémentations pour les deux méthodes dans la bibliothèque de simulations de la Hamilton.</span><span class="sxs-lookup"><span data-stu-id="62f68-147">We provide implementations for both methods in the Hamiltonian simulation library.</span></span>