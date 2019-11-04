---
title: Circuits quantiques | Microsoft Docs
description: Circuits quantiques
author: QuantumWriter
uid: microsoft.quantum.concepts.circuits
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 7c2afa58fd70d893529cf794ae07df480466aaec
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/31/2019
ms.locfileid: "73210652"
---
# <a name="quantum-circuits"></a><span data-ttu-id="987b8-103">Circuits quantiques</span><span class="sxs-lookup"><span data-stu-id="987b8-103">Quantum Circuits</span></span>
<span data-ttu-id="987b8-104">Prenons un moment pour la transformation unitaire $ \text{CNOTIN} _{01}(H\otimes 1) $.</span><span class="sxs-lookup"><span data-stu-id="987b8-104">Consider for a moment the unitary transformation $\text{ CNOT}_{01}(H\otimes 1)$.</span></span>
<span data-ttu-id="987b8-105">Cette séquence de porte-clés revêt une importance fondamentale pour l’informatique quantique, car elle crée un État à deux qubit enchevêtré au maximum :</span><span class="sxs-lookup"><span data-stu-id="987b8-105">This gate sequence is of fundamental significance to quantum computing because it creates a maximally entangled two-qubit state:</span></span>

<span data-ttu-id="987b8-106">$ $ \mathrm{CNOT}_{01}(H\otimes 1) \ket{00} = \frac{1}{\sqrt{2}} \left (\ket{00} + \ket{11} \right), $ $</span><span class="sxs-lookup"><span data-stu-id="987b8-106">$$\mathrm{CNOT}_{01}(H\otimes 1)\ket{00} = \frac{1}{\sqrt{2}} \left(\ket{00} + \ket{11} \right),$$</span></span>

<span data-ttu-id="987b8-107">Les opérations ayant cette complexité ou une complexité accrue sont omniprésentes dans les algorithmes Quantum et la correction des erreurs Quantum. il doit donc s’avérer très utile de disposer d’une méthode simple pour la visualisation appelée *diagramme de circuit quantique*.</span><span class="sxs-lookup"><span data-stu-id="987b8-107">Operations with this or greater complexity are ubiquitous in quantum algorithms and quantum error correction, so it should come as a great relief that there is a simple method for their visualization called a *quantum circuit diagram*.</span></span>
<span data-ttu-id="987b8-108">Le schéma de circuit pour la préparation de cet État Quantum enchevêtré de façon optimisée est le suivant :</span><span class="sxs-lookup"><span data-stu-id="987b8-108">The circuit diagram for preparing this maximally entangled quantum state is:</span></span>

<!--- ![](.\media\1.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/Concepts1.png)

## <a name="quantum-circuit-diagram-conventions"></a><span data-ttu-id="987b8-109">Conventions du diagramme de circuit quantique</span><span class="sxs-lookup"><span data-stu-id="987b8-109">Quantum circuit diagram conventions</span></span>
<span data-ttu-id="987b8-110">Ce langage visuel pour les opérations de Quantum peut être plus facilement compréhensible que l’écriture de sa matrice équivalente une fois que vous comprenez les conventions d’expression d’un circuit quantique.</span><span class="sxs-lookup"><span data-stu-id="987b8-110">This visual language for quantum operations can be more readily digestible than writing down its equivalent matrix once you understand the conventions for expressing a quantum circuit.</span></span>
<span data-ttu-id="987b8-111">Nous allons passer en revue les conventions ci-dessous.</span><span class="sxs-lookup"><span data-stu-id="987b8-111">We review these conventions below.</span></span>

<span data-ttu-id="987b8-112">Dans un schéma de circuit, chaque ligne pleine représente un qubit ou plus généralement un registre qubit.</span><span class="sxs-lookup"><span data-stu-id="987b8-112">In a circuit diagram, each solid line depicts a qubit or more generally a qubit register.</span></span>
<span data-ttu-id="987b8-113">Par Convention, la ligne supérieure est qubit Register $0 $ et le reste sont étiquetés de manière séquentielle.</span><span class="sxs-lookup"><span data-stu-id="987b8-113">By convention, the top line is qubit register $0$ and the remainder are labeled sequentially.</span></span> <span data-ttu-id="987b8-114">Le circuit d’exemple ci-dessus est représenté comme agissant sur deux qubits (ou deux registres équivalents composés d’un qubit).</span><span class="sxs-lookup"><span data-stu-id="987b8-114">The above example circuit is depicted as acting on two qubits (or equivalently two registers consisting of one qubit).</span></span>
<span data-ttu-id="987b8-115">Les portes agissant sur un ou plusieurs registres qubit sont dénotées sous forme de zone.</span><span class="sxs-lookup"><span data-stu-id="987b8-115">Gates acting on one or more qubit registers are denoted as a box.</span></span>
<span data-ttu-id="987b8-116">Par exemple, le symbole</span><span class="sxs-lookup"><span data-stu-id="987b8-116">For example, the symbol</span></span>

<!--- ![](.\media\2.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_2.png)

<span data-ttu-id="987b8-117">est la porte [hadarmard](xref:microsoft.quantum.primitive.h) agissant sur un registre à qubit unique.</span><span class="sxs-lookup"><span data-stu-id="987b8-117">is the [Hadamard](xref:microsoft.quantum.primitive.h) gate acting on a single-qubit register.</span></span>

<span data-ttu-id="987b8-118">Les portes de Quantum sont triées dans l’ordre chronologique avec la porte la plus à gauche à mesure que la porte est appliquée en premier au qubits.</span><span class="sxs-lookup"><span data-stu-id="987b8-118">Quantum gates are ordered in chronological order with the left-most gate as the gate first applied to the qubits.</span></span>
<span data-ttu-id="987b8-119">En d’autres termes, si vous constatez que les câbles sont dépendants de l’État Quantum, les fils importent l’État Quantum par le biais de chacune des portes du diagramme, de gauche à droite.</span><span class="sxs-lookup"><span data-stu-id="987b8-119">In other words, if you picture the wires as holding the quantum state, the wires bring the quantum state through each of the gates in the diagram from left to right.</span></span>
<span data-ttu-id="987b8-120">Autrement dit,</span><span class="sxs-lookup"><span data-stu-id="987b8-120">That is to say</span></span> 

<!--- ![](.\media\3.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_3.png)

<span data-ttu-id="987b8-121">est la matrice d’unités $CBA $.</span><span class="sxs-lookup"><span data-stu-id="987b8-121">is the unitary matrix $CBA$.</span></span>
<span data-ttu-id="987b8-122">La multiplication de matrice obéit à la Convention opposée : la matrice la plus à droite est appliquée en premier.</span><span class="sxs-lookup"><span data-stu-id="987b8-122">Matrix multiplication obeys the opposite convention: the right-most matrix is applied first.</span></span> <span data-ttu-id="987b8-123">Toutefois, dans les diagrammes de circuit Quantum, la porte la plus à gauche est appliquée en premier.</span><span class="sxs-lookup"><span data-stu-id="987b8-123">In quantum circuit diagrams, however, the left-most gate is applied first.</span></span>
<span data-ttu-id="987b8-124">Cette différence peut parfois entraîner une confusion. il est donc important de noter cette différence importante entre la notation algébrique linéaire et les diagrammes de circuit quantique.</span><span class="sxs-lookup"><span data-stu-id="987b8-124">This difference can at times lead to confusion, so it is important to note this significant difference between the linear algebraic notation and quantum circuit diagrams.</span></span>

## <a name="inputs-and-outputs-of-quantum-circuits"></a><span data-ttu-id="987b8-125">Entrées et sorties de circuits quantiques</span><span class="sxs-lookup"><span data-stu-id="987b8-125">Inputs and outputs of quantum circuits</span></span>
<span data-ttu-id="987b8-126">Tous les exemples précédents donnés ont eu exactement le même nombre de fils (qubits) d’entrée à une porte quantique que le nombre de fils de la porte quantique.</span><span class="sxs-lookup"><span data-stu-id="987b8-126">All previous examples given have had precisely the same number of wires (qubits) input to a quantum gate as the number of wires out from the quantum gate.</span></span>
<span data-ttu-id="987b8-127">Il peut sembler raisonnable que les circuits quantiques aient plus ou moins de sorties que d’entrées en général.</span><span class="sxs-lookup"><span data-stu-id="987b8-127">It may at first seem reasonable that quantum circuits could have more, or fewer, outputs than inputs in general.</span></span>
<span data-ttu-id="987b8-128">Toutefois, ce n’est pas possible car toutes les opérations de Quantum, les mesures Save, sont des unités et, par conséquent, réversibles.</span><span class="sxs-lookup"><span data-stu-id="987b8-128">This is impossible, however, because all quantum operations, save measurement, are unitary and hence reversible.</span></span>
<span data-ttu-id="987b8-129">S’ils n’ont pas le même nombre de sorties que les entrées, elles ne sont pas réversibles et, par conséquent, ne sont pas d’une contradiction.</span><span class="sxs-lookup"><span data-stu-id="987b8-129">If they did not have the same number of outputs as inputs they would not be reversible and hence not unitary, which is a contradiction.</span></span>
<span data-ttu-id="987b8-130">Pour cette raison, toute zone dessinée dans un diagramme de circuit doit avoir exactement le même nombre de câbles qui l’entrent comme étant en cours de sortie.</span><span class="sxs-lookup"><span data-stu-id="987b8-130">For this reason any box drawn in a circuit diagram must have precisely the same number of wires entering it as exiting it.</span></span>

<span data-ttu-id="987b8-131">Les diagrammes de circuit à plusieurs qubit suivent des conventions similaires pour les qubit.</span><span class="sxs-lookup"><span data-stu-id="987b8-131">Multi-qubit circuit diagrams follow similar conventions to single-qubit ones.</span></span>
<span data-ttu-id="987b8-132">En guise d’exemple de clarification, nous pouvons définir une opération unitaire à deux qubit $B $ pour être $ (H S\otimes X) $ et exprimer le circuit de façon équivalente</span><span class="sxs-lookup"><span data-stu-id="987b8-132">As a clarifying example, we can define a two-qubit unitary operation $B$ to be $(H S\otimes X)$ and express the circuit equivalently as</span></span>

<!--- ![](.\media\4.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_4.png)

<span data-ttu-id="987b8-133">Nous pouvons également afficher $B $ comme ayant une action sur un seul registre à deux qubit au lieu de registres 2 1-qubit en fonction du contexte dans lequel le circuit est utilisé.</span><span class="sxs-lookup"><span data-stu-id="987b8-133">We can also view $B$ as having an action on a single two-qubit register rather than two one-qubit registers depending on the context in which the circuit is used.</span></span> <span data-ttu-id="987b8-134">La propriété la plus utile de tels diagrammes de circuits abstraits est peut-être qu’ils permettent de décrire des algorithmes Quantum compliqués à un niveau élevé sans avoir à les compiler en portes fondamentales.</span><span class="sxs-lookup"><span data-stu-id="987b8-134">Perhaps the most useful property of such abstract circuit diagrams is that they allow complicated quantum algorithms to be described at a high level without having to compile them down to fundamental gates.</span></span>
<span data-ttu-id="987b8-135">Cela signifie que vous pouvez obtenir une intuition sur le workflow pour un grand algorithme Quantum sans avoir besoin de comprendre tous les détails sur le fonctionnement de chacune des sous-routines de l’algorithme.</span><span class="sxs-lookup"><span data-stu-id="987b8-135">This means that you can get an intuition about the data flow for a large quantum algorithm without needing to understand all the details of how each of the subroutines within the algorithm work.</span></span>

## <a name="controlled-gates"></a><span data-ttu-id="987b8-136">Portes contrôlées</span><span class="sxs-lookup"><span data-stu-id="987b8-136">Controlled gates</span></span>
<span data-ttu-id="987b8-137">L’autre construction intégrée aux diagrammes Quantum à plusieurs qubit est le contrôle.</span><span class="sxs-lookup"><span data-stu-id="987b8-137">The other construct that is built into multi-qubit quantum circuit diagrams is control.</span></span>
<span data-ttu-id="987b8-138">L’action d’une porte à contrôle quantique, dénotée $ \Lambda (G) $, où une valeur de qubit unique contrôle l’application de $G $, peut être comprise en examinant l’exemple suivant d’une entrée d’état de produit $ \Lambda (G) (\alpha \ket{0} + \beta \ket{1}) \ket{\Psi} = \alpha \ket{0} \ket{\Psi} + \beta \ket{1} G\ket {\ psi} $.</span><span class="sxs-lookup"><span data-stu-id="987b8-138">The action of a quantum singly controlled gate, denoted $\Lambda(G)$, where a single qubit's value controls the application of $G$, can be understood by looking at the following example of a product state input $\Lambda(G) (\alpha \ket{0} + \beta \ket{1}) \ket{\psi} = \alpha \ket{0} \ket{\psi} + \beta \ket{1} G\ket{\psi}$.</span></span>
<span data-ttu-id="987b8-139">Autrement dit, la porte contrôlée applique $G $ au registre contenant $ \Psi $ si et seulement si le contrôle qubit prend la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="987b8-139">That is to say, the controlled gate applies $G$ to the register containing $\psi$ if and only if the control qubit takes the value $1$.</span></span>
<span data-ttu-id="987b8-140">En général, nous décrivons ces opérations contrôlées dans des diagrammes de circuit comme</span><span class="sxs-lookup"><span data-stu-id="987b8-140">In general, we describe such controlled operations in circuit diagrams as</span></span>

<!--- ![](.\media\5.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_5.png)

<span data-ttu-id="987b8-141">Ici, le cercle noir désigne le bit Quantum sur lequel la porte est contrôlée et un câble vertical dénote l’unité qui est appliquée lorsque le contrôle qubit prend la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="987b8-141">Here the black circle denotes the quantum bit on which the gate is controlled and a vertical wire denotes the unitary that is applied when the control qubit takes the value $1$.</span></span>
<span data-ttu-id="987b8-142">Dans les cas spéciaux où $G = X $ et $G = Z $ nous introduisons la notation suivante pour décrire la version contrôlée des portes (Notez que la porte contrôlée-X est la [$CNOT $ Gate](xref:microsoft.quantum.primitive.cnot)) :</span><span class="sxs-lookup"><span data-stu-id="987b8-142">For the special cases where $G=X$ and $G=Z$ we introduce the following notation to describe the controlled version of the gates (note that the controlled-X gate is the [$CNOT$ gate](xref:microsoft.quantum.primitive.cnot)):</span></span>

<!--- ![](.\media\6.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_6.png)

<span data-ttu-id="987b8-143">Q # fournit des méthodes pour générer automatiquement la version contrôlée d’une opération, ce qui évite au programmeur d’avoir à coder manuellement ces opérations.</span><span class="sxs-lookup"><span data-stu-id="987b8-143">Q# provides methods to automatically generate the controlled version of an operation, which saves the programmer from having to hand code these operations.</span></span> <span data-ttu-id="987b8-144">Un exemple est illustré ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="987b8-144">An example of this is shown below:</span></span>

```qsharp
operation PrepareSuperposition(qubit : Qubit) : Unit
is Ctl { // Auto-generate the controlled specialization of the operation
    H(qubit);
}
```

## <a name="measurement-operator"></a><span data-ttu-id="987b8-145">Opérateur de mesure</span><span class="sxs-lookup"><span data-stu-id="987b8-145">Measurement operator</span></span>
<span data-ttu-id="987b8-146">L’opération restante à visualiser dans les diagrammes de circuit est la mesure.</span><span class="sxs-lookup"><span data-stu-id="987b8-146">The remaining operation to visualize in circuit diagrams is measurement.</span></span>
<span data-ttu-id="987b8-147">La mesure prend un registre qubit, le mesure et renvoie le résultat sous forme d’informations classiques.</span><span class="sxs-lookup"><span data-stu-id="987b8-147">Measurement takes a qubit register, measures it, and outputs the result as classical information.</span></span>
<span data-ttu-id="987b8-148">Une opération de mesure est indiquée par un symbole de compteur et prend toujours comme entrée un registre qubit (indiqué par une ligne pleine) et renvoie des informations classiques (dénotées par une ligne double).</span><span class="sxs-lookup"><span data-stu-id="987b8-148">A measurement operation is denoted by a meter symbol and always takes as input a qubit register (denoted by a solid line) and outputs classical information (denoted by a double line).</span></span>
<span data-ttu-id="987b8-149">Plus précisément, un sous-circuit similaire à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="987b8-149">Specifically, such a subcircuit looks like:</span></span>

<!--- ![](.\media\7.svg) ---->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
<span data-ttu-id="987b8-150">circuit de mesure ![](~/media/concepts_7.png)</span><span class="sxs-lookup"><span data-stu-id="987b8-150">![Measurement circuit](~/media/concepts_7.png)</span></span>

<span data-ttu-id="987b8-151">Q # implémente un [opérateur de mesure](xref:microsoft.quantum.primitive.measure) à cet effet.</span><span class="sxs-lookup"><span data-stu-id="987b8-151">Q# implements a [Measure operator](xref:microsoft.quantum.primitive.measure) for this purpose.</span></span>
<span data-ttu-id="987b8-152">Pour plus d’informations, consultez la [section sur les mesures](xref:microsoft.quantum.libraries.standard.prelude#measurements) .</span><span class="sxs-lookup"><span data-stu-id="987b8-152">See the [section on measurements](xref:microsoft.quantum.libraries.standard.prelude#measurements) for more information.</span></span>

<span data-ttu-id="987b8-153">De même, le sous-circuit</span><span class="sxs-lookup"><span data-stu-id="987b8-153">Similarly, the subcircuit</span></span>

<!--- ![](.\media\8.svg) --->
<!-- Can't find a way to easily center this... probably an extension needed:  -->
![](~/media/concepts_8.png)

<span data-ttu-id="987b8-154">donne une porte contrôlée de façon classique, où $G $ est appliqué sur le bit de contrôle classique qui est la valeur $1 $.</span><span class="sxs-lookup"><span data-stu-id="987b8-154">gives a classically controlled gate, where $G$ is applied conditioned on the classical control bit being value $1$.</span></span>

## <a name="teleportation-circuit-diagram"></a><span data-ttu-id="987b8-155">Diagramme de circuit de téléportisation</span><span class="sxs-lookup"><span data-stu-id="987b8-155">Teleportation circuit diagram</span></span>
<span data-ttu-id="987b8-156">La [téléportage quantique](xref:microsoft.quantum.techniques.puttingittogether) est peut-être le meilleur algorithme Quantum pour illustrer ces composants.</span><span class="sxs-lookup"><span data-stu-id="987b8-156">[Quantum teleportation](xref:microsoft.quantum.techniques.puttingittogether) is perhaps the best quantum algorithm for illustrating these components.</span></span>
<span data-ttu-id="987b8-157">La téléportage quantique est une méthode permettant de déplacer des données au sein d’un ordinateur quantique (ou même entre des ordinateurs quantiques distants dans un réseau quantique) à l’aide d’un enchevêtrement et d’une mesure.</span><span class="sxs-lookup"><span data-stu-id="987b8-157">Quantum teleportation is a method for moving data within a quantum computer (or even between distant quantum computers in a quantum network) through the use of entanglement and measurement.</span></span>
<span data-ttu-id="987b8-158">Il est intéressant de pouvoir déplacer un État Quantum, disons la valeur d’un qubit donné, d’un qubit à un autre, sans même connaître la valeur de qubit !</span><span class="sxs-lookup"><span data-stu-id="987b8-158">Interestingly, it is actually capable of moving a quantum state, say the value in a given qubit, from one qubit to another, without even knowing what the qubit's value is!</span></span>
<span data-ttu-id="987b8-159">Cela est nécessaire pour que le protocole fonctionne conformément aux lois de la mécanique des quantums.</span><span class="sxs-lookup"><span data-stu-id="987b8-159">This is necessary for the protocol to work according to the laws of quantum mechanics.</span></span>
<span data-ttu-id="987b8-160">Le circuit de téléportage Quantum est indiqué ci-dessous ; Nous fournissons également une version annotée du circuit pour illustrer comment lire le circuit Quantum.</span><span class="sxs-lookup"><span data-stu-id="987b8-160">The quantum teleportation circuit is given below; we also provide an annotated version of the circuit to illustrate how to read the quantum circuit.</span></span>

<!--- ![](.\media\tp2.svg){ width=50% } --->
![](~/media/concepts_tp2.png)
