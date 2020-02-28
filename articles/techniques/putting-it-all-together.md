---
title: 'Q # techniques-rassembler tout'
description: 'Parcourez un programme Q # de base qui illustre la téléportage quantique.'
uid: microsoft.quantum.techniques.puttingittogether
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 6c988f77ef6e433945dbf21dfb41204c74bdda3e
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906829"
---
# <a name="putting-it-all-together-teleportation"></a><span data-ttu-id="ed12b-103">Ensemble : téléportage</span><span class="sxs-lookup"><span data-stu-id="ed12b-103">Putting It All Together: Teleportation</span></span> #
<span data-ttu-id="ed12b-104">Revenons à l’exemple du circuit de téléportage défini dans [circuits quantiques](xref:microsoft.quantum.concepts.circuits).</span><span class="sxs-lookup"><span data-stu-id="ed12b-104">Let's return to the example of the teleportation circuit defined in [Quantum Circuits](xref:microsoft.quantum.concepts.circuits).</span></span> <span data-ttu-id="ed12b-105">Nous allons l’utiliser pour illustrer les concepts que nous avons appris jusqu’à présent.</span><span class="sxs-lookup"><span data-stu-id="ed12b-105">We're going to use this to illustrate the concepts we've learned so far.</span></span> <span data-ttu-id="ed12b-106">Une explication de la téléportage quantique est fournie ci-dessous pour ceux qui ne sont pas familiarisés avec la théorie, suivis d’une procédure pas à pas de l’implémentation de code dans Q #.</span><span class="sxs-lookup"><span data-stu-id="ed12b-106">An explanation of quantum teleportation is provided below for those who are unfamiliar with the theory, followed by a walkthrough of the code implementation in Q#.</span></span> 

## <a name="quantum-teleportation-theory"></a><span data-ttu-id="ed12b-107">Teleportage quantique : théorie</span><span class="sxs-lookup"><span data-stu-id="ed12b-107">Quantum Teleportation: Theory</span></span>
<span data-ttu-id="ed12b-108">La téléportage quantique est une technique permettant d’envoyer un État Quantum inconnu (que nous appelons «__message__») à partir d’un qubit dans un emplacement vers un qubit dans un autre emplacement (nous faisons référence à ces qubits__comme suit,__ respectivement).</span><span class="sxs-lookup"><span data-stu-id="ed12b-108">Quantum teleportation is a technique for sending an unknown quantum state (which we'll refer to as the '__message__') from a qubit in one location to a qubit in another location (we'll refer to these qubits as '__here__' and '__there__', respectively).</span></span> <span data-ttu-id="ed12b-109">Nous pouvons représenter notre __message__ sous forme de vecteur à l’aide de la notation Dirac :</span><span class="sxs-lookup"><span data-stu-id="ed12b-109">We can represent our __message__ as a vector using Dirac notation:</span></span> 

<span data-ttu-id="ed12b-110">$ $ \ket{\Psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-110">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="ed12b-111">L’état du __message__ qubit est inconnu, car nous ne connaissons pas les valeurs de $ \alpha $ et $ \beta $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-111">The __message__ qubit's state is unknown to us as we do not know the values of $\alpha$ and $\beta$.</span></span>

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="ed12b-112">Étape 1 : créer un État enchevêtré</span><span class="sxs-lookup"><span data-stu-id="ed12b-112">Step 1: Create an entangled state</span></span>
<span data-ttu-id="ed12b-113">Afin d’envoyer le __message__ dont nous avons besoin pour que le qubit soit associé à __l’qubit__ __ici__ .</span><span class="sxs-lookup"><span data-stu-id="ed12b-113">In order to send the __message__ we need for the qubit __here__ to be entangled with the qubit __there__.</span></span> <span data-ttu-id="ed12b-114">Cela est possible en appliquant une porte Hadarmard, suivie d’une porte CNOTIN.</span><span class="sxs-lookup"><span data-stu-id="ed12b-114">This is achieved by applying a Hadamard gate, followed by a CNOT gate.</span></span> <span data-ttu-id="ed12b-115">Examinons les mathématiques qui se trouvent derrière ces opérations de la porte.</span><span class="sxs-lookup"><span data-stu-id="ed12b-115">Let's look at the math behind these gate operations.</span></span>

<span data-ttu-id="ed12b-116">Nous allons commencer par le qubits __ici__ et __dans__ l’État $ \ket{0}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-116">We will begin with the qubits __here__ and __there__ both in the $\ket{0}$ state.</span></span> <span data-ttu-id="ed12b-117">Une fois ces qubits, ils sont dans l’État :</span><span class="sxs-lookup"><span data-stu-id="ed12b-117">After entangling these qubits, they are in the state:</span></span>

<span data-ttu-id="ed12b-118">$ $ \ket{\Phi ^ +} = \frac{1}{\sqrt{2}} (\ket{00} + \ket{11}) $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-118">$$ \ket{\phi^+} = \frac{1}{\sqrt{2}}(\ket{00} + \ket{11}) $$</span></span>

### <a name="step-2-send-the-message"></a><span data-ttu-id="ed12b-119">Étape 2 : envoyer le message</span><span class="sxs-lookup"><span data-stu-id="ed12b-119">Step 2: Send the message</span></span>
<span data-ttu-id="ed12b-120">Pour envoyer le __message__ , nous appliquons d’abord une porte cnotin avec le __message__ qubit et __ici__ qubit en tant qu’entrées (le __message__ qubit est le contrôle et le __ici__ qubit est le qubit cible, dans cette instance).</span><span class="sxs-lookup"><span data-stu-id="ed12b-120">To send the __message__ we first apply a CNOT gate with the __message__ qubit and __here__ qubit as inputs (the __message__ qubit being the control and the __here__ qubit being the target qubit, in this instance).</span></span> <span data-ttu-id="ed12b-121">Cet état d’entrée peut être écrit :</span><span class="sxs-lookup"><span data-stu-id="ed12b-121">This input state can be written:</span></span>

<span data-ttu-id="ed12b-122">$ $ \ket{\Psi}\ket{\Phi ^ +} = (\alpha\ket{0} + \beta\ket{1}) (\frac{1}{\sqrt{2}} (\ket{00} + \ket{11})) $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-122">$$ \ket{\psi}\ket{\phi^+} = (\alpha\ket{0} + \beta\ket{1})(\frac{1}{\sqrt{2}}(\ket{00} + \ket{11})) $$</span></span>

<span data-ttu-id="ed12b-123">Cela se développe en :</span><span class="sxs-lookup"><span data-stu-id="ed12b-123">This expands to:</span></span>

<span data-ttu-id="ed12b-124">$ $ \ket{\Psi}\ket{\Phi ^ +} = \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{100} + \frac{\beta}{\sqrt{2}} \ket{111} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-124">$$ \ket{\psi}\ket{\phi^+} = \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{100} + \frac{\beta}{\sqrt{2}}\ket{111} $$</span></span>

<span data-ttu-id="ed12b-125">En guise de rappel, la porte CNOTIN retourne le qubit cible lorsque le qubit de contrôle est 1.</span><span class="sxs-lookup"><span data-stu-id="ed12b-125">As a reminder, the CNOT gate flips the target qubit when the control qubit is 1.</span></span> <span data-ttu-id="ed12b-126">Ainsi, par exemple, une entrée de $ \ket{000}$ n’entraîne aucune modification, car le premier qubit (le contrôle) est 0.</span><span class="sxs-lookup"><span data-stu-id="ed12b-126">So for example, an input of $\ket{000}$ will result in no change as the first qubit (the control) is 0.</span></span> <span data-ttu-id="ed12b-127">Toutefois, prenez le cas où le premier qubit est 1, par exemple une entrée de $ \ket{100}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-127">However, take a case where the first qubit is 1 - for example an input of $\ket{100}$.</span></span> <span data-ttu-id="ed12b-128">Dans ce cas, la sortie est $ \ket{110}$, car la deuxième qubit (la cible) est retournée par la porte CNOTIN.</span><span class="sxs-lookup"><span data-stu-id="ed12b-128">In this instance, the output is $\ket{110}$ as the second qubit (the target) is flipped by the CNOT gate.</span></span>

<span data-ttu-id="ed12b-129">Nous allons maintenant examiner notre sortie une fois que la porte CNOTIN a agi sur notre entrée ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="ed12b-129">Let's now consider our output once the CNOT gate has acted on our input above.</span></span> <span data-ttu-id="ed12b-130">Le résultat est le suivant :</span><span class="sxs-lookup"><span data-stu-id="ed12b-130">The result is:</span></span>

<span data-ttu-id="ed12b-131">$ $ \frac{\alpha}{\sqrt{2}} \ket{000} + \frac{\alpha}{\sqrt{2}} \ket{011} + \frac{\beta}{\sqrt{2}} \ket{110} + \frac{\beta}{\sqrt{2}} \ket{101} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-131">$$ \frac{\alpha}{\sqrt{2}}\ket{000} + \frac{\alpha}{\sqrt{2}}\ket{011} + \frac{\beta}{\sqrt{2}}\ket{110} + \frac{\beta}{\sqrt{2}}\ket{101} $$</span></span>

<span data-ttu-id="ed12b-132">L’étape suivante pour envoyer le __message__ consiste à appliquer une porte hadarmard au __message__ qubit (il s’agit du premier qubit de chaque terme).</span><span class="sxs-lookup"><span data-stu-id="ed12b-132">The next step to send the __message__ is to apply a Hadamard gate to the __message__ qubit (that's the first qubit of each term).</span></span> 

<span data-ttu-id="ed12b-133">En guise de rappel, la porte Hadarmard effectue les opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="ed12b-133">As a reminder, the Hadamard gate does the following:</span></span>

<span data-ttu-id="ed12b-134">Entrée</span><span class="sxs-lookup"><span data-stu-id="ed12b-134">Input</span></span> | <span data-ttu-id="ed12b-135">Output</span><span class="sxs-lookup"><span data-stu-id="ed12b-135">Output</span></span>
---------------------------| ---------------------------------------------------------------
<span data-ttu-id="ed12b-136">$ \ket{0}$</span><span class="sxs-lookup"><span data-stu-id="ed12b-136">$\ket{0}$</span></span>  | <span data-ttu-id="ed12b-137">$ \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="ed12b-137">$\frac{1}{\sqrt{2}}(\ket{0} + \ket{1})$</span></span>
<span data-ttu-id="ed12b-138">$ \ket{1}$</span><span class="sxs-lookup"><span data-stu-id="ed12b-138">$\ket{1}$</span></span>  | <span data-ttu-id="ed12b-139">$ \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}) $</span><span class="sxs-lookup"><span data-stu-id="ed12b-139">$\frac{1}{\sqrt{2}}(\ket{0} - \ket{1})$</span></span>

<span data-ttu-id="ed12b-140">Si nous appliquons la porte Hadarmard au premier qubit de chaque terme de la sortie ci-dessus, nous obtenons le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="ed12b-140">If we apply the Hadamard gate to the first qubit of each term of our output above, we get the following result:</span></span>

<span data-ttu-id="ed12b-141">$ $ \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{00} + \frac{\alpha}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0} + \ket{1})) \ket{11} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{10} + \frac{\beta}{\sqrt{2}} (\frac{1}{\sqrt{2}} (\ket{0}-\ket{1})) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-141">$$ \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{00} + \frac{\alpha}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} + \ket{1}))\ket{11} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{10} + \frac{\beta}{\sqrt{2}}(\frac{1}{\sqrt{2}}(\ket{0} - \ket{1}))\ket{01} $$</span></span>

<span data-ttu-id="ed12b-142">Notez que chaque terme a des facteurs $2 \frac{1}{\sqrt{2}} $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-142">Note that each term has two $\frac{1}{\sqrt{2}}$ factors.</span></span> <span data-ttu-id="ed12b-143">Nous pouvons multiplier ces valeurs pour obtenir le résultat suivant :</span><span class="sxs-lookup"><span data-stu-id="ed12b-143">We can multiply these out giving the following result:</span></span>

<span data-ttu-id="ed12b-144">$ $ \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1}) \ket{11} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{10} + \frac{\beta}{2}(\ket{0}-\ket{1}) \ket{01} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-144">$$ \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{00} + \frac{\alpha}{2}(\ket{0} + \ket{1})\ket{11} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{10} + \frac{\beta}{2}(\ket{0} - \ket{1})\ket{01} $$</span></span>

<span data-ttu-id="ed12b-145">Le{1}$ \frac {2}$ Factor est commun à chaque terme afin que nous puissions le prendre en dehors des crochets :</span><span class="sxs-lookup"><span data-stu-id="ed12b-145">The  $\frac{1}{2}$ factor is common to each term so we can now take it outside the brackets:</span></span>

<span data-ttu-id="ed12b-146">$ $ \frac{1}{2}\big [\alpha (\ket{0} + \ket{1}) \ket{00} + \alpha (\ket{0} + \ket{1}) \ket{11} + \beta (\ket{0}-\ket{1}) \ket{10} + \beta (\ket{0}-\ket{1}) \ket{01}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-146">$$ \frac{1}{2}\big[\alpha(\ket{0} + \ket{1})\ket{00} + \alpha(\ket{0} + \ket{1})\ket{11} + \beta(\ket{0} - \ket{1})\ket{10} + \beta(\ket{0} - \ket{1})\ket{01}\big] $$</span></span>

<span data-ttu-id="ed12b-147">Nous pouvons ensuite multiplier les crochets pour chaque terme en donnant :</span><span class="sxs-lookup"><span data-stu-id="ed12b-147">We can then multiply out the brackets for each term giving:</span></span>

<span data-ttu-id="ed12b-148">$ $ \frac{1}{2}\big [\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010}-\beta\ket{110} + \beta\ket{001}-\beta\ket{101}\big] $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-148">$$ \frac{1}{2}\big[\alpha\ket{000} + \alpha\ket{100} + \alpha\ket{011} + \alpha\ket{111} + \beta\ket{010} - \beta\ket{110} + \beta\ket{001} - \beta\ket{101}\big] $$</span></span>

### <a name="step-3-measure-the-result"></a><span data-ttu-id="ed12b-149">Étape 3 : mesurer le résultat</span><span class="sxs-lookup"><span data-stu-id="ed12b-149">Step 3: Measure the result</span></span>

<span data-ttu-id="ed12b-150">En raison __de cette situation et de__ l’enchevêtrement, toute mesure sur __cet__ __objet affecte__ l' __État de cet emplacement.__</span><span class="sxs-lookup"><span data-stu-id="ed12b-150">Due to __here__ and __there__ being entangled, any measurement on __here__ will affect the state of __there__.</span></span> <span data-ttu-id="ed12b-151">Si nous mesurons le premier et le second qubit (__message__ et __ici__), nous pouvons découvrir l’État dans lequel __il__ se trouve, en raison de cette propriété d’enchevêtrement.</span><span class="sxs-lookup"><span data-stu-id="ed12b-151">If we measure the first and second qubit (__message__ and __here__) we can learn what state __there__ is in, due to this property of entanglement.</span></span> 

* <span data-ttu-id="ed12b-152">Si nous mesurons et obtenons le résultat 00, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="ed12b-152">If we measure and get a result 00, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ed12b-153">C’est $ \alpha\ket{000} + \beta\ket{001}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-153">That's $\alpha\ket{000} +\beta\ket{001}$.</span></span> <span data-ttu-id="ed12b-154">Cela peut être refactorisé en $ \ket{00}(\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-154">This can be refactored to $\ket{00}(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="ed12b-155">Par conséquent, si nous mesurons le premier et le second qubit à 00, nous savons que le troisième qubit, __ici__, est dans l’État $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-155">Therefore if we measure the first and second qubit to be 00, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ed12b-156">Si nous mesurons et obtenons le résultat 01, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="ed12b-156">If we measure and get a result 01, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ed12b-157">C’est $ \alpha\ket{011} + \beta\ket{010}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-157">That's $\alpha\ket{011} +\beta\ket{010}$.</span></span> <span data-ttu-id="ed12b-158">Cela peut être refactorisé en $ \ket{01}(\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-158">This can be refactored to $\ket{01}(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="ed12b-159">Par conséquent, si nous mesurons le premier et le second qubit à 01, nous savons que le troisième qubit, __ici__, est dans l’État $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-159">Therefore if we measure the first and second qubit to be 01, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span>
* <span data-ttu-id="ed12b-160">Si nous mesurons et obtenons le résultat 10, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="ed12b-160">If we measure and get a result 10, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ed12b-161">Il s’agit de $ \alpha\ket{100}-\beta\ket{101}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-161">That's $\alpha\ket{100} -\beta\ket{101}$.</span></span> <span data-ttu-id="ed12b-162">Cela peut être refactorisé en $ \ket{10}(\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-162">This can be refactored to $\ket{10}(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="ed12b-163">Par conséquent, si nous mesurons le premier et le second qubit à 10, nous savons que le troisième qubit, à __savoir, est__dans l’État $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-163">Therefore if we measure the first and second qubit to be 10, we know that the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span>
* <span data-ttu-id="ed12b-164">Si nous mesurons et obtenons le résultat 11, la superposition se réduit, en laissant uniquement les termes cohérents avec ce résultat.</span><span class="sxs-lookup"><span data-stu-id="ed12b-164">If we measure and get a result 11, the superposition collapses, leaving only terms consistent with this result.</span></span> <span data-ttu-id="ed12b-165">Il s’agit de $ \alpha\ket{111}-\beta\ket{110}$.</span><span class="sxs-lookup"><span data-stu-id="ed12b-165">That's $\alpha\ket{111} -\beta\ket{110}$.</span></span> <span data-ttu-id="ed12b-166">Cela peut être refactorisé en $ \ket{11}(\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-166">This can be refactored to $\ket{11}(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="ed12b-167">Par conséquent, si nous mesurons le premier et le second qubit sur 11, nous savons que le troisième qubit, à __savoir, est__dans l’État $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-167">Therefore if we measure the first and second qubit to be 11, we know that the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span>

### <a name="step-4-interpret-the-result"></a><span data-ttu-id="ed12b-168">Étape 4 : interpréter le résultat</span><span class="sxs-lookup"><span data-stu-id="ed12b-168">Step 4: Interpret the result</span></span>

<span data-ttu-id="ed12b-169">En guise de rappel, le __message__ d’origine que nous souhaitions envoyer était :</span><span class="sxs-lookup"><span data-stu-id="ed12b-169">As a reminder, the original __message__ we wished to send was:</span></span>

<span data-ttu-id="ed12b-170">$ $ \ket{\Psi} = \alpha\ket{0} + \beta\ket{1} $ $</span><span class="sxs-lookup"><span data-stu-id="ed12b-170">$$ \ket{\psi} = \alpha\ket{0} + \beta\ket{1} $$</span></span>

<span data-ttu-id="ed12b-171">Nous devons faire en sorte qu' __il__ qubit cet État, afin que l’état reçu soit celui prévu.</span><span class="sxs-lookup"><span data-stu-id="ed12b-171">We need to get the __there__ qubit into this state, so that the received state is the one that was intended.</span></span> 

* <span data-ttu-id="ed12b-172">Si nous avons mesuré et obtenu le résultat 00, alors le troisième __qubit, qui__se trouve dans l’État $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-172">If we measured and got a result of 00, then the third qubit, __there__, is in the state $(\alpha\ket{0} +\beta\ket{1})$.</span></span> <span data-ttu-id="ed12b-173">Comme il s’agit du __message__souhaité, aucune modification n’est requise.</span><span class="sxs-lookup"><span data-stu-id="ed12b-173">As this is the intended __message__, no alteration is required.</span></span>
* <span data-ttu-id="ed12b-174">Si nous avons mesuré et obtenu un résultat de 01, alors le troisième qubit, __il__se trouve dans l’État $ (\alpha\ket{1} + \beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-174">If we measured and got a result of 01, then the third qubit, __there__, is in the state $(\alpha\ket{1} +\beta\ket{0})$.</span></span> <span data-ttu-id="ed12b-175">Cela diffère du __message__prévu, mais l’application d’une porte non nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-175">This differs from the intended __message__, however applying a NOT gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ed12b-176">Si nous avons mesuré et obtenu un résultat de 10, alors le troisième qubit __, qui__se trouve dans l’État $ (\alpha\ket{0}-\beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-176">If we measured and got a result of 10, then the third qubit, __there__, is in the state $(\alpha\ket{0} -\beta\ket{1})$.</span></span> <span data-ttu-id="ed12b-177">Cela diffère du __message__prévu, mais l’application d’une porte Z nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-177">This differs from the intended __message__, however applying a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>
* <span data-ttu-id="ed12b-178">Si nous avons mesuré et obtenu le résultat __11, alors__le troisième qubit est dans l’État $ (\alpha\ket{1}-\beta\ket{0}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-178">If we measured and got a result of 11, then the third qubit, __there__, is in the state $(\alpha\ket{1} -\beta\ket{0})$.</span></span> <span data-ttu-id="ed12b-179">Cela diffère du __message__prévu, mais l’application d’une porte non suivie d’une porte Z nous donne l’état souhaité $ (\alpha\ket{0} + \beta\ket{1}) $.</span><span class="sxs-lookup"><span data-stu-id="ed12b-179">This differs from the intended __message__, however applying a NOT gate followed by a Z gate gives us the desired state $(\alpha\ket{0} +\beta\ket{1})$.</span></span>

<span data-ttu-id="ed12b-180">Pour résumer, si nous mesurons et que le premier qubit est 1, une porte Z est appliquée.</span><span class="sxs-lookup"><span data-stu-id="ed12b-180">To summarize, if we measure and the first qubit is 1, a Z gate is applied.</span></span> <span data-ttu-id="ed12b-181">Si nous mesurons et que le second qubit est 1, une porte non est appliquée.</span><span class="sxs-lookup"><span data-stu-id="ed12b-181">If we measure and the second qubit is 1, a NOT gate is applied.</span></span>

### <a name="summary"></a><span data-ttu-id="ed12b-182">Résumé</span><span class="sxs-lookup"><span data-stu-id="ed12b-182">Summary</span></span>
<span data-ttu-id="ed12b-183">Vous trouverez ci-dessous un circuit de quantum de livre de texte qui implémente la téléportation.</span><span class="sxs-lookup"><span data-stu-id="ed12b-183">Shown below is a text-book quantum circuit that implements the teleportation.</span></span> <span data-ttu-id="ed12b-184">En vous déplaçant de gauche à droite, vous pouvez voir :</span><span class="sxs-lookup"><span data-stu-id="ed12b-184">Moving from left to right you can see:</span></span>
- <span data-ttu-id="ed12b-185">Étape 1 : __application de la__ porte __hadarmard et de__ la porte cnotin.</span><span class="sxs-lookup"><span data-stu-id="ed12b-185">Step 1: Entangling __here__ and __there__ by applying a Hadamard gate and CNOT gate.</span></span>
- <span data-ttu-id="ed12b-186">Étape 2 : envoi du __message__ à l’aide d’une porte cnotin et d’une porte hadarmard.</span><span class="sxs-lookup"><span data-stu-id="ed12b-186">Step 2: Sending the __message__ using a CNOT gate and a Hadamard gate.</span></span>
- <span data-ttu-id="ed12b-187">Étape 3 : exécution d’une mesure du premier et du deuxième qubits, du __message__ et __ici__.</span><span class="sxs-lookup"><span data-stu-id="ed12b-187">Step 3: Taking a measurement of the first and second qubits, __message__ and __here__.</span></span>
- <span data-ttu-id="ed12b-188">Étape 4 : application d’une porte non ou d’une porte Z, en fonction du résultat de la mesure à l’étape 3.</span><span class="sxs-lookup"><span data-stu-id="ed12b-188">Step 4: Applying a NOT gate or a Z gate, depending on the result of the measurement in step 3.</span></span>

![' (MSG : qubit, IT : qubit) : unit'](~/media/teleportation.svg)

## <a name="quantum-teleportation-code"></a><span data-ttu-id="ed12b-190">Teleportage quantique : code</span><span class="sxs-lookup"><span data-stu-id="ed12b-190">Quantum Teleportation: Code</span></span>

<span data-ttu-id="ed12b-191">Nous disposons de notre circuit pour la téléportage quantique :</span><span class="sxs-lookup"><span data-stu-id="ed12b-191">We have our circuit for quantum teleportation:</span></span>

![' (MSG : qubit, IT : qubit) : unit'](~/media/teleportation.svg)

<span data-ttu-id="ed12b-193">Nous pouvons maintenant traduire chacune des étapes de ce circuit Quantum en Q #.</span><span class="sxs-lookup"><span data-stu-id="ed12b-193">We can now translate each of the steps in this quantum circuit into Q#.</span></span>

### <a name="step-0-definition"></a><span data-ttu-id="ed12b-194">Étape 0 : définition</span><span class="sxs-lookup"><span data-stu-id="ed12b-194">Step 0: Definition</span></span>
<span data-ttu-id="ed12b-195">Lorsque nous effectuons une télétransmission, nous devons connaître le __message__ que nous souhaitons envoyer et l’endroit où nous voulons l’envoyer (__ici__).</span><span class="sxs-lookup"><span data-stu-id="ed12b-195">When we perform teleportation, we must know the __message__ we wish to send, and where we wish to send it (__there__).</span></span> <span data-ttu-id="ed12b-196">Pour cette raison, nous commençons par définir une nouvelle opération de redémarrage qui reçoit deux qubits comme arguments, `msg` et `there`:</span><span class="sxs-lookup"><span data-stu-id="ed12b-196">For this reason, we begin by defining a new Teleport operation that is given two qubits as arguments, `msg` and `there`:</span></span>

```qsharp
operation Teleport(msg : Qubit, there : Qubit) : Unit {
```

<span data-ttu-id="ed12b-197">Nous devons également allouer un `here` qubit que nous obtenons avec un bloc `using` :</span><span class="sxs-lookup"><span data-stu-id="ed12b-197">We also need to allocate a qubit `here` which we achieve with a `using` block:</span></span>

```qsharp
    using (here = Qubit()) {
```

### <a name="step-1-create-an-entangled-state"></a><span data-ttu-id="ed12b-198">Étape 1 : créer un État enchevêtré</span><span class="sxs-lookup"><span data-stu-id="ed12b-198">Step 1: Create an entangled state</span></span>
<span data-ttu-id="ed12b-199">Nous pouvons ensuite créer la paire enchevêtrée entre `here` et `there` à l’aide des opérations @"microsoft.quantum.intrinsic.h" et @"microsoft.quantum.intrinsic.cnot" :</span><span class="sxs-lookup"><span data-stu-id="ed12b-199">We can then create the entangled pair between `here` and `there` by using the @"microsoft.quantum.intrinsic.h" and @"microsoft.quantum.intrinsic.cnot" operations:</span></span>

```qsharp
        H(here);
        CNOT(here, there);
```

### <a name="step-2-send-the-message"></a><span data-ttu-id="ed12b-200">Étape 2 : envoyer le message</span><span class="sxs-lookup"><span data-stu-id="ed12b-200">Step 2: Send the message</span></span>
<span data-ttu-id="ed12b-201">Nous utilisons ensuite les \operatorname{CNOT} $ et $H $ Gates suivants pour déplacer notre qubit de message :</span><span class="sxs-lookup"><span data-stu-id="ed12b-201">We then use the next $\operatorname{CNOT}$ and $H$ gates to move our message qubit:</span></span>

```qsharp
        CNOT(msg, here);
        H(msg);
```

### <a name="step-3--4-measuring-and-interpreting-the-result"></a><span data-ttu-id="ed12b-202">Étape 3 & 4 : mesure et interprétation du résultat</span><span class="sxs-lookup"><span data-stu-id="ed12b-202">Step 3 & 4: Measuring and interpreting the result</span></span>
<span data-ttu-id="ed12b-203">Enfin, nous utilisons @"microsoft.quantum.intrinsic.m" pour effectuer les mesures et effectuer les opérations de la porte nécessaire pour atteindre l’état souhaité, comme indiqué par les instructions `if` :</span><span class="sxs-lookup"><span data-stu-id="ed12b-203">Finally, we use @"microsoft.quantum.intrinsic.m" to perform the measurements and perform the necessary gate operations to get the desired state, as denoted by `if` statements:</span></span>

```qsharp
        // Measure out the entanglement
        if (M(msg) == One)  { Z(there); }
        if (M(here) == One) { X(there); }
```

<span data-ttu-id="ed12b-204">Cela termine la définition de notre opérateur de téléportage. nous pouvons donc désallouer `here`, terminer le corps et terminer l’opération.</span><span class="sxs-lookup"><span data-stu-id="ed12b-204">This finishes the definition of our teleportation operator, so we can deallocate `here`, end the body, and end the operation.</span></span>

```qsharp
    }
}
```
