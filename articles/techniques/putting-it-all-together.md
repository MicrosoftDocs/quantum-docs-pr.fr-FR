---
title: Techniques Q - Mettre tout cela ensemble
description: Promenez-vous dans le cadre d’un programme de base de QMD qui démontre la téléportation quantique.
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 4bd91699017e4c1acd9f4449b8a65e39bd07878e
ms.sourcegitcommit: b6b8459eb654040f1e19f66411b29fc9e48e95c9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82030563"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="a1bd1-103">Mettre tout cela ensemble: Téléportation</span><span class="sxs-lookup"><span data-stu-id="a1bd1-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="a1bd1-104">Revenons à l’exemple du circuit de téléportation défini dans [Les circuits quantiques](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="a1bd1-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="a1bd1-105">Nous allons nous en servir pour illustrer les concepts que nous avons appris jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="a1bd1-106">Une explication de la téléportation quantique est fournie ci-dessous pour ceux qui ne sont pas familiers avec la théorie, suivie d’une procédure pas à pas de l’implémentation du code dans Q.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="a1bd1-107">Téléportation quantique : Théorie</span><span class="sxs-lookup"><span data-stu-id="a1bd1-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="a1bd1-108">La téléportation quantique est une technique pour envoyer un état quantique inconnu (que nous appellerons le «__message__») d’un qubit à un endroit à un qubit dans un autre endroit (nous nous référerons à ces qubits comme «__ici__» et « là »__respectivement).__</span><span class="sxs-lookup"><span data-stu-id="a1bd1-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="a1bd1-109">Nous pouvons représenter notre __message__ comme un vecteur en utilisant la notation Dirac:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="a1bd1-110">$$ 'ket 'psi' 'alpha’ket{0} 'beta 'ket{1} $$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="a1bd1-111">L’état du __message__ qubit est inconnu pour nous car nous ne connaissons pas les valeurs de $alpha$ et $beta$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="a1bd1-112">Étape 1 : Créer un état empêtré</span><span class="sxs-lookup"><span data-stu-id="a1bd1-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="a1bd1-113">Afin d’envoyer le __message__ que nous avons besoin pour le qubit __ici__ pour être empêtré avec le qubit __là-__.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="a1bd1-114">Ceci est réalisé en appliquant une porte Hadamard, suivie d’une porte CNOT.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="a1bd1-115">Regardons les maths derrière ces opérations de porte.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="a1bd1-116">Nous allons commencer avec les qubits __ici__ et{0} __là__ à la fois dans l’état de $ket $.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="a1bd1-117">Après avoir enchevêté ces qubits, ils sont dans l’état:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="a1bd1-118">$$ 'ket 'phi{1}'''''''''''' 'frac 'sqrt'''''{2}(ket{00} ' '{11}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '</span><span class="sxs-lookup"><span data-stu-id="a1bd1-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="a1bd1-119">Étape 2 : Envoyer le message</span><span class="sxs-lookup"><span data-stu-id="a1bd1-119">Step 2: Send the message</span></span>
<span data-ttu-id="a1bd1-120">Pour envoyer le __message,__ nous appliquons d’abord une porte CNOT avec le __qubit message__ et __ici__ qubit comme entrées (le __qubit message__ étant le contrôle et le qubit __ici__ étant le qubit cible, dans ce cas).</span><span class="sxs-lookup"><span data-stu-id="a1bd1-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="a1bd1-121">Cet état d’entrée peut être écrit :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-121">This input state can be written:</span></span>

<span data-ttu-id="a1bd1-122">$$ 'ket 'psi 'ket{0} 'phi '''''''''''''''' (alpha’ket 'beta’ket{00} {11}{1}')(frac{1}'sqrt''''''ket{2}'') $$ $$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="a1bd1-123">Cela s’étend à :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-123">This expands to:</span></span>

<span data-ttu-id="a1bd1-124">$$ 'ket 'psi’ket 'phi{2}'''''''''''''''alpha’sqrt ''ket{000} 'frac 'alpha 'sqrt{2}''ket{011} ''frac{2}'beta 'sqrt ''sqrt{100} ''frac{2}'bêta''{111}</span><span class="sxs-lookup"><span data-stu-id="a1bd1-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="a1bd1-125">Pour rappel, la porte CNOT retourne le qubit cible lorsque le qubit de contrôle est 1.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="a1bd1-126">Ainsi, par exemple, une entrée{000}de $ket $ n’entraînera aucun changement que le premier qubit (le contrôle) est 0.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="a1bd1-127">Cependant, prenez un cas où le premier qubit est 1{100}- par exemple une entrée de $ket $.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="a1bd1-128">Dans ce cas, la sortie{110}est $ket $ que le deuxième qubit (la cible) est renversé par la porte CNOT.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="a1bd1-129">Examinons maintenant notre sortie une fois que la porte CNOT a agi sur nos commentaires ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="a1bd1-130">Le résultat est le suivant :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-130">The result is:</span></span>

<span data-ttu-id="a1bd1-131">$$ 'frac’alpha 'sqrt{2}'{000} 'sqrt ' 'ket 'frac{2}'alpha 'sqrt ''sqrt{011} ''ket{2}'frac{110} 'beta 'sqrt 'sqrt{2}''ket{101} 'frac 'bêta 'sqrt ''ket $$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="a1bd1-132">L’étape suivante pour envoyer le __message__ est d’appliquer une porte Hadamard au __message__ qubit (c’est le premier qubit de chaque terme).</span><span class="sxs-lookup"><span data-stu-id="a1bd1-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="a1bd1-133">Pour rappel, la porte Hadamard fait ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="a1bd1-134">Entrée</span><span class="sxs-lookup"><span data-stu-id="a1bd1-134">Input</span></span> | <span data-ttu-id="a1bd1-135">Output</span><span class="sxs-lookup"><span data-stu-id="a1bd1-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="a1bd1-136">$ket{0}$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-136">$\ket{0}$</span></span>  | <span data-ttu-id="a1bd1-137">$-frac{1}'sqrt{2}'(ket{0} ' 'ket 'ket{1})$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="a1bd1-138">$ket{1}$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-138">$\ket{1}$</span></span>  | <span data-ttu-id="a1bd1-139">$-frac{1}'sqrt{2}'(ket{0} - 'ket{1})$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="a1bd1-140">Si nous appliquons la porte Hadamard au premier qubit de chaque terme de notre sortie ci-dessus, nous obtenons le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="a1bd1-141">{2}$$ 'frac’alpha’sqrt '(frac{1}'sqrt '('sqrt{2}{0} ''''ket 'ket{1}{00} ')'ket 'frac{2}'alpha’sqrt{1}'(frac 'sqrt''('frac 'sqrt''''''ket{2}{0} ''ket{1}{11} ''' 'frac’beta’sqrt{2}'(frac{1}'sqrt'{2}('ket{0} {1}' ' ' ' ' ' ' ' '{10} ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{2}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{1}{2}{0} {1}{01}</span><span class="sxs-lookup"><span data-stu-id="a1bd1-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="a1bd1-142">Notez que chaque terme a{1}deux facteurs{2}de $'frac 'sqrt '$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="a1bd1-143">Nous pouvons multiplier ces en donnant le résultat suivant:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="a1bd1-144">$$ 'frac’alpha'{2}{0} ('ket{1}'ket ''ket{00} ''frac’alpha'{2}('ket{0} {1}'ket{11} ''ket{2}''ket ''frac’beta' ('ket{0} {1}' ' ' ' '{0} {1}{01} {10} {2}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '</span><span class="sxs-lookup"><span data-stu-id="a1bd1-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="a1bd1-145">Le facteur de{1}{2}10 $et de l’est est commun à chaque terme, de sorte que nous pouvons maintenant le prendre en dehors des parenthèses :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="a1bd1-146">$$ 'frac{1}{2}'big['alpha''ket{0} 'ket{1}''ket ''ket{00} 'alpha''ket{11} {0} {1}{10} {0} {1}{01}{0} 'ket 'ket{1}'ket 'ket ' 'beta''ket ' 'ket 'ket 'beta’ket ' 'ket 'ket 'big' $$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="a1bd1-147">Nous pouvons alors multiplier les parenthèses pour chaque terme donnant :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="a1bd1-148">{1}{2}$$ 'frac 'big['alpha’ket{000} 'alpha’ket 'alpha’ket{100} 'alpha’ket{011} 'alpha’ket{111} 'bêta’ket{010} ' ' ' ' ' ' ' ' ' '{110} ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '{001} {101}' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' ' '</span><span class="sxs-lookup"><span data-stu-id="a1bd1-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="a1bd1-149">Étape 3 : Mesurer le résultat</span><span class="sxs-lookup"><span data-stu-id="a1bd1-149">Step 3: Measure the result</span></span>

<span data-ttu-id="a1bd1-150">En raison __d’ici__ et __là__ étant empêtré, toute mesure sur __ici__ affectera l’état de __là__.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="a1bd1-151">Si nous mesurons le premier et le deuxième qubit __(message__ et __ici__) nous pouvons apprendre dans quel état __il ya,__ en raison de cette propriété de l’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="a1bd1-152">Si nous mesurons et obtenons un résultat 00, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="a1bd1-153">C’est $'alpha’ket{000} 'beta’ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="a1bd1-154">Cela peut être refactorisé à{00}$'ket{0} (alpha’ket{1}'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="a1bd1-155">Par conséquent, si nous mesurons le premier et le deuxième qubit __there__à 00, nous savons que{0} le troisième qubit, là , est dans l’état de $(alpha 'ket 'beta 'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="a1bd1-156">Si nous mesurons et obtenons un résultat 01, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="a1bd1-157">C’est $'alpha’ket{011} 'beta’ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="a1bd1-158">Cela peut être refactorisé à{01}$'ket{1} (alpha’ket{0}'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="a1bd1-159">Par conséquent, si nous mesurons le premier et le deuxième qubit pour être 01, nous savons{1} que le troisième{0}qubit, __il__, est dans l’état de $(alpha 'ket 'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="a1bd1-160">Si nous mesurons et obtenons un résultat 10, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="a1bd1-161">C’est $'alpha’ket{100} -beta’ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="a1bd1-162">Cela peut être refactorisé à{10}$'ket{0} (alpha 'ket{1}-'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="a1bd1-163">Par conséquent, si nous mesurons le premier et le deuxième qubit __there__à 10, nous savons que{0} le troisième qubit, il , est dans l’état de $(alpha 'ket - 'beta 'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="a1bd1-164">Si nous mesurons et obtenons un résultat 11, la superposition s’effondre, ne laissant que des termes compatibles avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="a1bd1-165">C’est $'alpha’ket{111} -beta’ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="a1bd1-166">Cela peut être refactorisé à{11}$'ket{1} (alpha 'ket{0}-'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="a1bd1-167">Par conséquent, si nous mesurons le premier et le deuxième qubit pour être 11, nous savons{1} que le troisième{0}qubit, __il__, est dans l’état de $(alpha 'ket - 'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="a1bd1-168">Étape 4 : Interpréter le résultat</span><span class="sxs-lookup"><span data-stu-id="a1bd1-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="a1bd1-169">Pour rappel, le __message__ original que nous voulions envoyer était :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="a1bd1-170">$$ 'ket 'psi' 'alpha’ket{0} 'beta 'ket{1} $$</span><span class="sxs-lookup"><span data-stu-id="a1bd1-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="a1bd1-171">Nous devons mettre le qubit __là__ dans cet état, de sorte que l’état reçu est celui qui était prévu.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="a1bd1-172">Si nous avons mesuré et obtenu un résultat de 00, puis le troisième qubit, __il__, est dans l’état de $(alpha 'ket{0} 'beta 'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="a1bd1-173">Comme il s’agit du __message__prévu, aucune modification n’est nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="a1bd1-174">Si nous avons mesuré et obtenu un résultat de 01, puis le troisième qubit, __il__, est dans l’état de $(alpha 'ket{1} 'beta 'ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="a1bd1-175">Cela diffère du __message__prévu, mais l’application d’une porte PAS{0} nous donne l’état désiré $(alpha 'ket 'beta 'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="a1bd1-176">Si nous avons mesuré et obtenu un résultat de 10, puis le troisième qubit, __il__, est dans l’état de $(alpha -ket{0} - bêta -ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="a1bd1-177">Cela diffère du __message__prévu, mais l’application d’une porte Z{0} nous donne l’état désiré $(alpha 'ket 'beta 'ket{1})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="a1bd1-178">Si nous avons mesuré et obtenu un résultat de 11, puis le troisième qubit, __il__, est dans l’état de $(alpha -ket{1} - bêta -ket{0})$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="a1bd1-179">Cela diffère du __message__prévu, mais l’application d’une porte PAS suivie d’une{0} porte Z nous{1}donne l’état désiré $(alpha -ket 'beta 'ket )$.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="a1bd1-180">Pour résumer, si nous mesurons et le premier qubit est de 1, une porte Z est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="a1bd1-181">Si nous mesurons et le deuxième qubit est 1, une porte PAS est appliquée.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="a1bd1-182">Résumé</span><span class="sxs-lookup"><span data-stu-id="a1bd1-182">Summary</span></span>
<span data-ttu-id="a1bd1-183">Ci-dessous est un circuit quantique de livre de texte qui implémente la téléportation.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="a1bd1-184">En se déplaçant de gauche à droite, vous pouvez voir :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="a1bd1-185">Étape 1 : Enchevêtrement __ici__ et __là__ en appliquant une porte Hadamard et une porte CNOT.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="a1bd1-186">Étape 2 : Envoi du __message__ à l’aide d’une porte CNOT et d’une porte Hadamard.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="a1bd1-187">Étape 3 : Prendre une mesure des premier et deuxième qubits, __du message__ et __ici.__</span><span class="sxs-lookup"><span data-stu-id="a1bd1-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="a1bd1-188">Étape 4 : Appliquer une porte NON ou une porte Z, selon le résultat de la mesure à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

!['Teleport (msg : Qubit, there : Qubit) : Unit'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="a1bd1-190">Téléportation quantique : Code</span><span class="sxs-lookup"><span data-stu-id="a1bd1-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="a1bd1-191">Nous avons notre circuit pour la téléportation quantique :</span><span class="sxs-lookup"><span data-stu-id="a1bd1-191">We have our circuit for quantum teleportation:</span></span>

!['Teleport (msg : Qubit, there : Qubit) : Unit'](~/media/teleportation.svg)

<span data-ttu-id="a1bd1-193">Nous pouvons maintenant traduire chacune des étapes de ce circuit quantique en Q.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="a1bd1-194">Étape 0 : Définition</span><span class="sxs-lookup"><span data-stu-id="a1bd1-194">Step 0: Definition</span></span>
<span data-ttu-id="a1bd1-195">Lorsque nous effectuons la téléportation, nous devons connaître le __message__ que nous voulons envoyer, et où nous voulons l’envoyer __(là).__</span><span class="sxs-lookup"><span data-stu-id="a1bd1-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="a1bd1-196">Pour cette raison, nous commençons par définir une nouvelle opération Teleport `msg` `there`qui est donné deux qubits comme arguments, et:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="a1bd1-197">Nous devons également allouer `here` un qubit `using` que nous réalisons avec un bloc:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="a1bd1-198">Étape 1 : Créer un état empêtré</span><span class="sxs-lookup"><span data-stu-id="a1bd1-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="a1bd1-199">Nous pouvons ensuite créer la `here` `there` paire enchevêtrée entre et en utilisant le et @"microsoft.quantum.intrinsic.h" @"microsoft.quantum.intrinsic.cnot" les opérations:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="a1bd1-200">Étape 2 : Envoyer le message</span><span class="sxs-lookup"><span data-stu-id="a1bd1-200">Step 2: Send the message</span></span>
<span data-ttu-id="a1bd1-201">Nous utilisons ensuite les prochaines portes de $-operatorname-CNOT$ et $H$ pour déplacer notre message qubit:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="a1bd1-202">Étape 3 & 4 : Mesurer et interpréter le résultat</span><span class="sxs-lookup"><span data-stu-id="a1bd1-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="a1bd1-203">Enfin, nous @"microsoft.quantum.intrinsic.m" utilisons pour effectuer les mesures et effectuer les opérations de porte `if` nécessaires pour obtenir l’état souhaité, comme indiqué par les déclarations:</span><span class="sxs-lookup"><span data-stu-id="a1bd1-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

### <a name="step-5-restarting-the-qubit-register"></a><span data-ttu-id="a1bd1-204">Étape 5 : Redémarrage du registre qubit</span><span class="sxs-lookup"><span data-stu-id="a1bd1-204">Step 5: Restarting the qubit register</span></span>

<span data-ttu-id="a1bd1-205">À la fin de chaque opération Q, nous avons besoin de{0}laisser les qubits dans l’état $ket $.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-205">At the end of every Q# operation we need to let the qubits in the state $\ket{0}$.</span></span> <span data-ttu-id="a1bd1-206">Nous pouvons @"microsoft.quantum.intrinsic.reset" utiliser pour redémarrer tous les qubits à l’état zéro et cela finira notre opération.</span><span class="sxs-lookup"><span data-stu-id="a1bd1-206">We can use @"microsoft.quantum.intrinsic.reset" to restart all the qubits to the zero state and this will finish our operation.</span></span>

```qsharp
        Reset(msg);
        Reset(here);
        Reset(there);
    }
}
```


