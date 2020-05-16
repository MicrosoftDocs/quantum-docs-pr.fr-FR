---
title: Circuits de quantum
description: Découvrez comment représenter visuellement des opérations quantiques simples et complexes avec des diagrammes de circuit quantique.
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 43f14d67db76dabda34bf881ccbfae0bfd1784ff
ms.sourcegitcommit: 2317473fdf2b80de58db0f43b9fcfb57f56aefff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83426625"
---
# <a name="quantum-circuits"></a><span data-ttu-id="036e0-103">Circuits quantiques</span><span class="sxs-lookup"><span data-stu-id="036e0-103">Quantum Circuits</span></span>
<span data-ttu-id="036e0-104">Prenons un moment pour la transformation unitaire $ \text{CNOTIN} _ {01} (H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="036e0-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="036e0-105">Cette séquence de porte-clés revêt une importance fondamentale pour l’informatique quantique, car elle crée un État à deux qubit enchevêtré au maximum :</span><span class="sxs-lookup"><span data-stu-id="036e0-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="036e0-106">$ $ \mathrm{CNOT}_ {01} (H\otimes 1) \ket {00} = \frac {1} {\sqrt {2} } \left (\ket {00} + \ket {11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="036e0-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="036e0-107">Les opérations ayant cette complexité ou une complexité accrue sont omniprésentes dans les algorithmes Quantum et la correction des erreurs Quantum. il doit donc s’avérer très utile de disposer d’une méthode simple pour la visualisation appelée *diagramme de circuit quantique*.</span><span class="sxs-lookup"><span data-stu-id="036e0-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="036e0-108">Le schéma de circuit pour la préparation de cet État Quantum enchevêtré de façon optimisée est le suivant :</span><span class="sxs-lookup"><span data-stu-id="036e0-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-109">![Diagramme de circuit pour un État à deux qubit enchevêtré](~/media/1.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-109">![Circuit diagram for a maximally entangled two-qubit state](~/media/1.svg)</span></span>

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="036e0-110">Conventions du diagramme de circuit quantique</span><span class="sxs-lookup"><span data-stu-id="036e0-110">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="036e0-111">Ce langage visuel pour les opérations de Quantum peut être plus facilement compréhensible que l’écriture de sa matrice équivalente une fois que vous comprenez les conventions d’expression d’un circuit quantique.</span><span class="sxs-lookup"><span data-stu-id="036e0-111">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="036e0-112">Nous allons passer en revue les conventions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="036e0-112">We review these conventions below.</span></span>

<span data-ttu-id="036e0-113">Dans un schéma de circuit, chaque ligne pleine représente un qubit ou plus généralement un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="036e0-113">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="036e0-114">Par Convention, la ligne supérieure est qubit Register $0 $ et le reste sont étiquetés de manière séquentielle.</span><span class="sxs-lookup"><span data-stu-id="036e0-114">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="036e0-115">Le circuit d’exemple ci-dessus est représenté comme agissant sur deux qubits (ou deux registres équivalents composés d’un qubit).</span><span class="sxs-lookup"><span data-stu-id="036e0-115">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="036e0-116">Les portes agissant sur un ou plusieurs registres qubit sont dénotées sous forme de zone.</span><span class="sxs-lookup"><span data-stu-id="036e0-116">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="036e0-117">Par exemple, le symbole</span><span class="sxs-lookup"><span data-stu-id="036e0-117">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-118">![Symbole pour une opération Hadarmard agissant sur un registre à qubit unique](~/media/2.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-118">![Symbol for a Hadamard operation acting on a single-qubit register](~/media/2.svg)</span></span>

<span data-ttu-id="036e0-119">est une opération [hadarmard](xref:microsoft.quantum.intrinsic.h) agissant sur un registre à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="036e0-119">is a [Hadamard](xref:microsoft.quantum.intrinsic.h) operation acting on a single-qubit register.</span></span>

<span data-ttu-id="036e0-120">Les portes de Quantum sont triées dans l’ordre chronologique avec la porte la plus à gauche à mesure que la porte est appliquée en premier au qubits.</span><span class="sxs-lookup"><span data-stu-id="036e0-120">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="036e0-121">En d’autres termes, si vous constatez que les câbles sont dépendants de l’État Quantum, les fils importent l’État Quantum par le biais de chacune des portes du diagramme, de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="036e0-121">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="036e0-122">Autrement dit,</span><span class="sxs-lookup"><span data-stu-id="036e0-122">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-123">![Diagramme des portes de Quantum appliquées de gauche à droite](~/media/3.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-123">![Diagram of quantum gates being applied left-to-right](~/media/3.svg)</span></span>

<span data-ttu-id="036e0-124">est la matrice d’unités $CBA $.</span><span class="sxs-lookup"><span data-stu-id="036e0-124">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="036e0-125">La multiplication de matrice obéit à la Convention opposée : la matrice la plus à droite est appliquée en premier.</span><span class="sxs-lookup"><span data-stu-id="036e0-125">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="036e0-126">Toutefois, dans les diagrammes de circuit Quantum, la porte la plus à gauche est appliquée en premier.</span><span class="sxs-lookup"><span data-stu-id="036e0-126">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="036e0-127">Cette différence peut parfois entraîner une confusion. il est donc important de noter cette différence importante entre la notation algébrique linéaire et les diagrammes de circuit quantique.</span><span class="sxs-lookup"><span data-stu-id="036e0-127">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="036e0-128">Entrées et sorties de circuits quantiques</span><span class="sxs-lookup"><span data-stu-id="036e0-128">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="036e0-129">Tous les exemples précédents donnés ont eu exactement le même nombre de fils (qubits) d’entrée à une porte quantique que le nombre de fils de la porte quantique.</span><span class="sxs-lookup"><span data-stu-id="036e0-129">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="036e0-130">Il peut sembler raisonnable que les circuits quantiques aient plus ou moins de sorties que d’entrées en général.</span><span class="sxs-lookup"><span data-stu-id="036e0-130">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="036e0-131">Toutefois, ce n’est pas possible car toutes les opérations de Quantum, les mesures Save, sont des unités et, par conséquent, réversibles.</span><span class="sxs-lookup"><span data-stu-id="036e0-131">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="036e0-132">S’ils n’ont pas le même nombre de sorties que les entrées, elles ne sont pas réversibles et, par conséquent, ne sont pas d’une contradiction.</span><span class="sxs-lookup"><span data-stu-id="036e0-132">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="036e0-133">Pour cette raison, toute zone dessinée dans un diagramme de circuit doit avoir exactement le même nombre de câbles qui l’entrent comme étant en cours de sortie.</span><span class="sxs-lookup"><span data-stu-id="036e0-133">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="036e0-134">Les diagrammes de circuit à plusieurs qubit suivent des conventions similaires pour les qubit.</span><span class="sxs-lookup"><span data-stu-id="036e0-134">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="036e0-135">En guise d’exemple de clarification, nous pouvons définir une opération unitaire à deux qubit $B $ pour être $ (H S\otimes X) $ et exprimer le circuit de façon équivalente</span><span class="sxs-lookup"><span data-stu-id="036e0-135">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-136">![Diagramme de circuit d’une opération unitaire à deux qubit](~/media/4.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-136">![Circuit diagram of a two-qubit unitary operation](~/media/4.svg)</span></span>

<span data-ttu-id="036e0-137">Nous pouvons également afficher $B $ comme ayant une action sur un seul registre à deux qubit au lieu de registres 2 1-qubit en fonction du contexte dans lequel le circuit est utilisé.</span><span class="sxs-lookup"><span data-stu-id="036e0-137">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="036e0-138">La propriété la plus utile de tels diagrammes de circuits abstraits est peut-être qu’ils permettent de décrire des algorithmes Quantum compliqués à un niveau élevé sans avoir à les compiler en portes fondamentales.</span><span class="sxs-lookup"><span data-stu-id="036e0-138">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="036e0-139">Cela signifie que vous pouvez obtenir une intuition sur le workflow pour un grand algorithme Quantum sans avoir besoin de comprendre tous les détails sur le fonctionnement de chacune des sous-routines de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="036e0-139">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="036e0-140">Portes contrôlées</span><span class="sxs-lookup"><span data-stu-id="036e0-140">Controlled gates</span></span>
<span data-ttu-id="036e0-141">L’autre construction intégrée aux diagrammes Quantum à plusieurs qubit est le contrôle.</span><span class="sxs-lookup"><span data-stu-id="036e0-141">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="036e0-142">L’action d’une porte à contrôle quantique, dénotée $ \Lambda (G) $, où une valeur de qubit unique contrôle l’application de $G $, peut être comprise en examinant l’exemple suivant d’une entrée d’état de produit $ \Lambda (G) (\alpha \ket {0} + \beta \ket {1} ) \ket{\Psi} = \alpha \ket {0} \ket{\Psi} + \beta \ket G\ket {1} {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="036e0-142">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="036e0-143">Autrement dit, la porte contrôlée applique $G $ au registre contenant $ \Psi $ si et seulement si le contrôle qubit prend la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="036e0-143">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="036e0-144">En général, nous décrivons ces opérations contrôlées dans des diagrammes de circuit comme</span><span class="sxs-lookup"><span data-stu-id="036e0-144">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-145">![Diagramme de circuit d’une porte contrôlée de façon unique](~/media/5.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-145">![Circuit diagram of a singly controlled gate](~/media/5.svg)</span></span>

<span data-ttu-id="036e0-146">Ici, le cercle noir désigne le bit Quantum sur lequel la porte est contrôlée et un câble vertical dénote l’unité qui est appliquée lorsque le contrôle qubit prend la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="036e0-146">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="036e0-147">Dans les cas spéciaux où $G = X $ et $G = Z $ nous introduisons la notation suivante pour décrire la version contrôlée des portes (Notez que la porte contrôlée-X est la [$CNOT $ Gate](xref:microsoft.quantum.intrinsic.cnot)) :</span><span class="sxs-lookup"><span data-stu-id="036e0-147">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.intrinsic.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-148">![Diagramme de circuit pour des cas spéciaux de portes contrôlées](~/media/6.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-148">![Circuit diagram for special cases of controlled gates](~/media/6.svg)</span></span>

<span data-ttu-id="036e0-149">Q # fournit des méthodes pour générer automatiquement la version contrôlée d’une opération, ce qui évite au programmeur d’avoir à coder manuellement ces opérations.</span><span class="sxs-lookup"><span data-stu-id="036e0-149">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="036e0-150">Un exemple est illustré ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="036e0-150">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="036e0-151">Opérateur de mesure</span><span class="sxs-lookup"><span data-stu-id="036e0-151">Measurement operator</span></span>
<span data-ttu-id="036e0-152">L’opération restante à visualiser dans les diagrammes de circuit est la mesure.</span><span class="sxs-lookup"><span data-stu-id="036e0-152">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="036e0-153">La mesure prend un registre qubit, le mesure et renvoie le résultat sous forme d’informations classiques.</span><span class="sxs-lookup"><span data-stu-id="036e0-153">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="036e0-154">Une opération de mesure est indiquée par un symbole de compteur et prend toujours comme entrée un registre qubit (indiqué par une ligne pleine) et renvoie des informations classiques (dénotées par une ligne double).</span><span class="sxs-lookup"><span data-stu-id="036e0-154">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="036e0-155">Plus précisément, un sous-circuit similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="036e0-155">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-156">![Symbole représentant une opération de mesure](~/media/7.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-156">![Symbol representing a measurement operation](~/media/7.svg)</span></span>

<span data-ttu-id="036e0-157">Q # implémente un [opérateur de mesure](xref:microsoft.quantum.intrinsic.measure) à cet effet.</span><span class="sxs-lookup"><span data-stu-id="036e0-157">Q# implements a [Measure operator](xref:microsoft.quantum.intrinsic.measure) for this purpose.</span></span>
<span data-ttu-id="036e0-158">Pour plus d’informations, consultez la [section sur les mesures](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="036e0-158">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="036e0-159">De même, le sous-circuit</span><span class="sxs-lookup"><span data-stu-id="036e0-159">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="036e0-160">![Diagramme de circuit représentant une opération contrôlée](~/media/8.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-160">![Circuit diagram representing a controlled operation](~/media/8.svg)</span></span>

<span data-ttu-id="036e0-161">donne une porte contrôlée de façon classique, où $G $ est appliqué sur le bit de contrôle classique qui est la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="036e0-161">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="036e0-162">Diagramme de circuit de téléportisation</span><span class="sxs-lookup"><span data-stu-id="036e0-162">Teleportation circuit diagram</span></span>
<span data-ttu-id="036e0-163">La téléportage quantique est peut-être le meilleur algorithme Quantum pour illustrer ces composants.</span><span class="sxs-lookup"><span data-stu-id="036e0-163">Quantum teleportation is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="036e0-164">Vous pouvez apprendre à utiliser le quantum [Kata](xref:microsoft.quantum.overview.katas) Quantum teleportage pour déplacer des données au sein d’un ordinateur Quantum (ou même entre des ordinateurs quantiques distants dans un réseau quantique) à l’aide d’un enchevêtrement et d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="036e0-164">You can learn hands-on with the corresponding [Quantum Kata](xref:microsoft.quantum.overview.katas) Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="036e0-165">Il est intéressant de pouvoir déplacer un État Quantum, disons la valeur d’un qubit donné, d’un qubit à un autre, sans même connaître la valeur de qubit !</span><span class="sxs-lookup"><span data-stu-id="036e0-165">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="036e0-166">Cela est nécessaire pour que le protocole fonctionne conformément aux lois de la mécanique des quantums.</span><span class="sxs-lookup"><span data-stu-id="036e0-166">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="036e0-167">Le circuit de téléportage Quantum est indiqué ci-dessous ; Nous fournissons également une version annotée du circuit pour illustrer comment lire le circuit Quantum.</span><span class="sxs-lookup"><span data-stu-id="036e0-167">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
<span data-ttu-id="036e0-168">![Circuit de téléportage quantique](~/media/tp2.svg)</span><span class="sxs-lookup"><span data-stu-id="036e0-168">![Quantum teleportation circuit](~/media/tp2.svg)</span></span>
