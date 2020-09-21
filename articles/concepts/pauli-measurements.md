---
<span data-ttu-id="a4a24-101">titre : Pauli mesures Description : Apprenez à utiliser des opérations de mesure Pauli à qubit unique et à plusieurs.</span><span class="sxs-lookup"><span data-stu-id="a4a24-101">title: Pauli Measurements description: Learn how to work with single- and multi-qubit Pauli measurement operations.</span></span>
<span data-ttu-id="a4a24-102">Auteur : bradben UID : Microsoft. Quantum. concepts. Pauli ms. Author : v-benbra ms. Date : 12/11/2017 ms. topic : article No-Loc :</span><span class="sxs-lookup"><span data-stu-id="a4a24-102">author: bradben uid: microsoft.quantum.concepts.pauli ms.author: v-benbra ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="a4a24-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="a4a24-103">"Q#"</span></span>
- <span data-ttu-id="a4a24-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="a4a24-104">"$$v"</span></span>
- <span data-ttu-id="a4a24-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-105">"$$"</span></span>
- <span data-ttu-id="a4a24-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-106">"$$"</span></span>
- <span data-ttu-id="a4a24-107">"$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-107">"$"</span></span>
- <span data-ttu-id="a4a24-108">"$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-108">"$"</span></span>
- <span data-ttu-id="a4a24-109">"$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-109">"$"</span></span>
- <span data-ttu-id="a4a24-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="a4a24-110">"$$"</span></span>
- <span data-ttu-id="a4a24-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="a4a24-111">"\cdots"</span></span>
- <span data-ttu-id="a4a24-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="a4a24-112">"bmatrix"</span></span>
- <span data-ttu-id="a4a24-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="a4a24-113">"\ddots"</span></span>
- <span data-ttu-id="a4a24-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="a4a24-114">"\equiv"</span></span>
- <span data-ttu-id="a4a24-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="a4a24-115">"\sum"</span></span>
- <span data-ttu-id="a4a24-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="a4a24-116">"\begin"</span></span>
- <span data-ttu-id="a4a24-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="a4a24-117">"\end"</span></span>
- <span data-ttu-id="a4a24-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="a4a24-118">"\sqrt"</span></span>
- <span data-ttu-id="a4a24-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="a4a24-119">"\otimes"</span></span>
- <span data-ttu-id="a4a24-120">"{"</span><span class="sxs-lookup"><span data-stu-id="a4a24-120">"{"</span></span>
- <span data-ttu-id="a4a24-121">"}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-121">"}"</span></span>
- <span data-ttu-id="a4a24-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="a4a24-122">"\text"</span></span>
- <span data-ttu-id="a4a24-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="a4a24-123">"\phi"</span></span>
- <span data-ttu-id="a4a24-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="a4a24-124">"\kappa"</span></span>
- <span data-ttu-id="a4a24-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="a4a24-125">"\psi"</span></span>
- <span data-ttu-id="a4a24-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="a4a24-126">"\alpha"</span></span>
- <span data-ttu-id="a4a24-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="a4a24-127">"\beta"</span></span>
- <span data-ttu-id="a4a24-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="a4a24-128">"\gamma"</span></span>
- <span data-ttu-id="a4a24-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="a4a24-129">"\delta"</span></span>
- <span data-ttu-id="a4a24-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="a4a24-130">"\omega"</span></span>
- <span data-ttu-id="a4a24-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="a4a24-131">"\bra"</span></span>
- <span data-ttu-id="a4a24-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="a4a24-132">"\ket"</span></span>
- <span data-ttu-id="a4a24-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="a4a24-133">"\boldone"</span></span>
- <span data-ttu-id="a4a24-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="a4a24-134">"\\\\"</span></span>
- <span data-ttu-id="a4a24-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="a4a24-135">"\\"</span></span>
- <span data-ttu-id="a4a24-136">"="</span><span class="sxs-lookup"><span data-stu-id="a4a24-136">"="</span></span>
- <span data-ttu-id="a4a24-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="a4a24-137">"\frac"</span></span>
- <span data-ttu-id="a4a24-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="a4a24-138">"\text"</span></span>
- <span data-ttu-id="a4a24-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="a4a24-139">"\mapsto"</span></span>
- <span data-ttu-id="a4a24-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="a4a24-140">"\dagger"</span></span>
- <span data-ttu-id="a4a24-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="a4a24-141">"\to"</span></span>
- <span data-ttu-id="a4a24-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-142">"\begin{cases}"</span></span>
- <span data-ttu-id="a4a24-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-143">"\end{cases}"</span></span>
- <span data-ttu-id="a4a24-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="a4a24-144">"\operatorname"</span></span>
- <span data-ttu-id="a4a24-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="a4a24-145">"\braket"</span></span>
- <span data-ttu-id="a4a24-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="a4a24-146">"\id"</span></span>
- <span data-ttu-id="a4a24-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="a4a24-147">"\expect"</span></span>
- <span data-ttu-id="a4a24-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="a4a24-148">"\defeq"</span></span>
- <span data-ttu-id="a4a24-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="a4a24-149">"\variance"</span></span>
- <span data-ttu-id="a4a24-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="a4a24-150">"\dd"</span></span>
- <span data-ttu-id="a4a24-151">"&"</span><span class="sxs-lookup"><span data-stu-id="a4a24-151">"&"</span></span>
- <span data-ttu-id="a4a24-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-152">"\begin{align}"</span></span>
- <span data-ttu-id="a4a24-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-153">"\end{align}"</span></span>
- <span data-ttu-id="a4a24-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="a4a24-154">"\Lambda"</span></span>
- <span data-ttu-id="a4a24-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="a4a24-155">"\lambda"</span></span>
- <span data-ttu-id="a4a24-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="a4a24-156">"\Omega"</span></span>
- <span data-ttu-id="a4a24-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="a4a24-157">"\mathrm"</span></span>
- <span data-ttu-id="a4a24-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="a4a24-158">"\left"</span></span>
- <span data-ttu-id="a4a24-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="a4a24-159">"\right"</span></span>
- <span data-ttu-id="a4a24-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="a4a24-160">"\qquad"</span></span>
- <span data-ttu-id="a4a24-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="a4a24-161">"\times"</span></span>
- <span data-ttu-id="a4a24-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="a4a24-162">"\big"</span></span>
- <span data-ttu-id="a4a24-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="a4a24-163">"\langle"</span></span>
- <span data-ttu-id="a4a24-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="a4a24-164">"\rangle"</span></span>
- <span data-ttu-id="a4a24-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="a4a24-165">"\bigg"</span></span>
- <span data-ttu-id="a4a24-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="a4a24-166">"\Big"</span></span>
- <span data-ttu-id="a4a24-167">"|"</span><span class="sxs-lookup"><span data-stu-id="a4a24-167">"|"</span></span>
- <span data-ttu-id="a4a24-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="a4a24-168">"\mathbb"</span></span>
- <span data-ttu-id="a4a24-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="a4a24-169">"\vec"</span></span>
- <span data-ttu-id="a4a24-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="a4a24-170">"\in"</span></span>
- <span data-ttu-id="a4a24-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="a4a24-171">"\texttt"</span></span>
- <span data-ttu-id="a4a24-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="a4a24-172">"\ne"</span></span>
- <span data-ttu-id="a4a24-173">"<"</span><span class="sxs-lookup"><span data-stu-id="a4a24-173">"<"</span></span>
- <span data-ttu-id="a4a24-174">">"</span><span class="sxs-lookup"><span data-stu-id="a4a24-174">">"</span></span>
- <span data-ttu-id="a4a24-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="a4a24-175">"\leq"</span></span>
- <span data-ttu-id="a4a24-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="a4a24-176">"\geq"</span></span>
- <span data-ttu-id="a4a24-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="a4a24-177">"~~"</span></span>
- <span data-ttu-id="a4a24-178">"~"</span><span class="sxs-lookup"><span data-stu-id="a4a24-178">"~"</span></span>
- <span data-ttu-id="a4a24-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="a4a24-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="a4a24-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="a4a24-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="a4a24-181">"\_"</span></span>

---

# <a name="pauli-measurements"></a><span data-ttu-id="a4a24-182">Mesures Pauli</span><span class="sxs-lookup"><span data-stu-id="a4a24-182">Pauli Measurements</span></span>

<span data-ttu-id="a4a24-183">Dans les discussions précédentes, nous nous sommes concentrés sur les mesures de base de calcul.</span><span class="sxs-lookup"><span data-stu-id="a4a24-183">In the previous discussions, we have focused on computational basis measurements.</span></span>
<span data-ttu-id="a4a24-184">En fait, il existe d’autres mesures courantes qui se produisent dans quantum computing qui, du point de vue de la notation, sont pratiques pour exprimer en termes de mesures de la base de calcul.</span><span class="sxs-lookup"><span data-stu-id="a4a24-184">In fact, there are other common measurements that occur in quantum computing that, from a notational perspective, are convenient to express in terms of computational basis measurements.</span></span>
<span data-ttu-id="a4a24-185">À mesure que vous travaillez avec Q# , le type de mesure le plus courant dans lequel vous allez être exécuté sera probablement des *mesures Pauli*, qui généralisent les mesures de base de calcul pour inclure des mesures dans d’autres bases et de la parité entre différents qubits.</span><span class="sxs-lookup"><span data-stu-id="a4a24-185">As you work with Q#, the most common kind of measurements that you'll run into will likely be *Pauli measurements*, which generalize computational basis measurements to include measurements in other bases, and of parity between different qubits.</span></span>
<span data-ttu-id="a4a24-186">Dans ce cas, il est courant d’examiner la mesure d’un opérateur Pauli, en général un opérateur tel que $ X, Y, z $ ou $ z \otimes z, x \otimes x, x \otimes Y $ , etc.</span><span class="sxs-lookup"><span data-stu-id="a4a24-186">In such cases, it is common to discuss measuring a Pauli operator, in general an operator such as $X,Y,Z$ or $Z\otimes Z, X\otimes X, X\otimes Y$, and so forth.</span></span>

> [!TIP]
<span data-ttu-id="a4a24-187">> Dans Q# , les opérateurs Pauli multi-qubit sont généralement représentés par des tableaux de type `Pauli[]` .</span><span class="sxs-lookup"><span data-stu-id="a4a24-187">> In Q#, multi-qubit Pauli operators are generally represented by arrays of type `Pauli[]`.</span></span>
<span data-ttu-id="a4a24-188">> Par exemple, pour représenter $ X \otimes Z \otimes Y $ , vous pouvez utiliser le tableau `[PauliX, PauliZ, PauliY]` .</span><span class="sxs-lookup"><span data-stu-id="a4a24-188">> For example, to represent $X \otimes Z \otimes Y$, you can use the array `[PauliX, PauliZ, PauliY]`.</span></span>

<span data-ttu-id="a4a24-189">L’étude des mesures en termes d’opérateurs Pauli est particulièrement courante dans le sous-champ de la correction des erreurs Quantum.</span><span class="sxs-lookup"><span data-stu-id="a4a24-189">Discussing measurement in terms of Pauli operators is especially common in the subfield of quantum error correction.</span></span>
<span data-ttu-id="a4a24-190">Dans Q# , nous suivons une convention similaire. nous expliquons maintenant cette vue alternative des mesures.</span><span class="sxs-lookup"><span data-stu-id="a4a24-190">In Q#, we follow a similar convention; we now explain this alternative view of measurements.</span></span>

<span data-ttu-id="a4a24-191">Avant de plonger dans les détails sur la façon de considérer une mesure Pauli, il est utile de réfléchir à la mesure d’un qubit unique dans un ordinateur quantique à l’État Quantum.</span><span class="sxs-lookup"><span data-stu-id="a4a24-191">Before delving into the details of how to think of a Pauli measurement, it is useful to think about what measuring a single qubit inside a quantum computer does to the quantum state.</span></span>
<span data-ttu-id="a4a24-192">Imaginez que nous avons un $ $ État Quantum n-qubit, puis que la mesure d’un qubit règle immédiatement la moitié des $ 2 ^ n possibilités de l' $ État.</span><span class="sxs-lookup"><span data-stu-id="a4a24-192">Imagine that we have an $n$-qubit quantum state; then measuring one qubit immediately rules out half of the $2^n$ possibilities that state could be in.</span></span>
<span data-ttu-id="a4a24-193">En d’autres termes, la mesure projette l’État Quantum sur l’un des deux demi-espaces.</span><span class="sxs-lookup"><span data-stu-id="a4a24-193">In other words, the measurement projects the quantum state onto one of two half-spaces.</span></span>
<span data-ttu-id="a4a24-194">Nous pouvons généraliser la façon dont nous pensons à la mesure pour refléter cette intuition.</span><span class="sxs-lookup"><span data-stu-id="a4a24-194">We can generalize the way we think about measurement to reflect this intuition.</span></span>

<span data-ttu-id="a4a24-195">Pour identifier ces sous-espaces de manière concise, nous avons besoin d’un langage pour les décrire.</span><span class="sxs-lookup"><span data-stu-id="a4a24-195">In order to concisely identify these subspaces, we need a language for describing them.</span></span>
<span data-ttu-id="a4a24-196">Une façon de décrire les deux sous-espaces consiste à les spécifier à l’aide d’une matrice qui a simplement deux valeurs propres uniques, pris par convention comme $ \pm 1 $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-196">One way to describe the two subspaces is by specifying them through a matrix that just has two unique eigenvalues, taken by convention to be $\pm 1$.</span></span>
<span data-ttu-id="a4a24-197">Pour obtenir un exemple simple de description des sous-espaces de cette manière, utilisez $ Z $ :</span><span class="sxs-lookup"><span data-stu-id="a4a24-197">For a simple example of describing subspaces in this way, consider $Z$:</span></span>

$$
\begin{align}
  <span data-ttu-id="a4a24-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a4a24-198">Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="a4a24-199">En lisant les éléments diagonales de la matrice Pauli- $ Z $ , nous voyons que $ Z $ a deux vecteurs propres, $ \ket { 0 } $ et $ \ket { 1 } $ , avec le valeurs propres $ \pm 1 correspondant $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-199">By reading the diagonal elements of the Pauli-$Z$ matrix, we can see that $Z$ has two eigenvectors, $\ket{0}$ and $\ket{1}$, with corresponding eigenvalues $\pm 1$.</span></span>
<span data-ttu-id="a4a24-200">Ainsi, si nous mesurons qubit et obtenons `Zero` (correspondant à l’état $ \ket { 0 } $ ), nous savons que l’état de notre qubit est $ + 1 $ eigenstate de l' $ $ opérateur Z.</span><span class="sxs-lookup"><span data-stu-id="a4a24-200">Thus, if we measure the qubit and obtain `Zero` (corresponding to the state $\ket{0}$), we know that the state of our qubit is a $+1$ eigenstate of the $Z$ operator.</span></span>
<span data-ttu-id="a4a24-201">De même, si nous obtenons `One` , nous savons que l’état de notre qubit est $ -1 $ eigenstate de $ Z $ . Ce processus est appelé dans le langage des mesures de Pauli comme « mesurant Pauli $ Z $ » et est entièrement équivalent à l’exécution d’une mesure de base de calcul.</span><span class="sxs-lookup"><span data-stu-id="a4a24-201">Similarly, if we obtain `One`, we know that the state of our qubit is a $-1$ eigenstate of $Z$. This process is referred to in the language of Pauli measurements as "measuring Pauli $Z$," and is entirely equivalent to performing a computational basis measurement.</span></span>

<span data-ttu-id="a4a24-202">Toute $ \times matrice 2 2 $ qui est une transformation unitaire de $ Z $ répond également à ce critère.</span><span class="sxs-lookup"><span data-stu-id="a4a24-202">Any $2\times 2$ matrix that is a unitary transformation of $Z$ also satisfies this criteria.</span></span>
<span data-ttu-id="a4a24-203">Autrement dit, nous pourrions également utiliser une matrice $ a = u ^ \dagger Z u $ , où $ U $ est une autre matrice unitaire, pour fournir une matrice qui définit les deux résultats d’une mesure dans son $ \pm 1 $ vecteurs propres.</span><span class="sxs-lookup"><span data-stu-id="a4a24-203">That is, we could also use a matrix $A=U^\dagger Z U$, where $U$ is any other unitary matrix, to give a matrix that defines the two outcomes of a measurement in its $\pm 1$ eigenvectors.</span></span>
<span data-ttu-id="a4a24-204">La notation des mesures Pauli fait référence à cette équivalence unitaire en identifiant les $ mesures X, Y, Z $ comme des mesures équivalentes qu’il est possible d’obtenir pour obtenir des informations à partir d’un qubit.</span><span class="sxs-lookup"><span data-stu-id="a4a24-204">The notation of Pauli measurements references this unitary equivalence by identifying $X,Y,Z$ measurements as equivalent measurements that one could do to gain information from a qubit.</span></span>
<span data-ttu-id="a4a24-205">Ces mesures sont fournies ci-dessous pour des raisons pratiques.</span><span class="sxs-lookup"><span data-stu-id="a4a24-205">These measurements are given below for convenience.</span></span>


<span data-ttu-id="a4a24-206">|Transformation d’unité de mesure Pauli ||</span><span class="sxs-lookup"><span data-stu-id="a4a24-206">|Pauli Measurement  |Unitary transformation  |</span></span>
|-------------------|------------------------|
<span data-ttu-id="a4a24-207">|$ $ Z |               $\boldone$             |</span><span class="sxs-lookup"><span data-stu-id="a4a24-207">| $Z$               | $\boldone$             |</span></span>
<span data-ttu-id="a4a24-208">|$ $ X | $H               $                    |</span><span class="sxs-lookup"><span data-stu-id="a4a24-208">| $X$               | $H$                    |</span></span>
<span data-ttu-id="a4a24-209">|$ $ Y | $HS ^               {\dagger}$         |</span><span class="sxs-lookup"><span data-stu-id="a4a24-209">| $Y$               | $HS^{\dagger}$         |</span></span>

<span data-ttu-id="a4a24-210">Autrement dit, l’utilisation de ce langage, « Measure $ Y $ » équivaut à appliquer HS ^, puis à $ \dagger $ mesurer la base de calcul, où [`S`](xref:microsoft.quantum.intrinsic.s) est une opération quantique intrinsèque parfois appelée « porte-phase » et peut être simulée par la matrice d’unités</span><span class="sxs-lookup"><span data-stu-id="a4a24-210">That is, using this language, "measure $Y$" is equivalent to applying $HS^\dagger$ and then measuring in the computational basis, where [`S`](xref:microsoft.quantum.intrinsic.s) is an intrinsic quantum operation sometimes called the "phase gate," and can be simulated by the unitary matrix</span></span>

$$
\begin{align}
    <span data-ttu-id="a4a24-211">S =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a4a24-211">S = \begin{bmatrix}</span></span>
        <span data-ttu-id="a4a24-212">1 & 0 \\\\ 0 & i \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a4a24-212">1 & 0 \\\\ 0 & i \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="a4a24-213">Cela équivaut également à appliquer $ HS ^ \dagger $ au vecteur d’État Quantum, puis à mesurer $ Z $ , de telle sorte que l’opération suivante soit équivalente à `Measure([PauliY], [q])` :</span><span class="sxs-lookup"><span data-stu-id="a4a24-213">It is also equivalent to applying $HS^\dagger$ to the quantum state vector and then measuring $Z$, such that the following operation is equivalent to `Measure([PauliY], [q])`:</span></span>

```Q#
operation MeasureY(qubit : Qubit) : Result {
    mutable result = Zero;
    within {
        Adjoint S(q);
        H(q);
    } apply {
        set result = M(q);
    }
    return result;
}
```

<span data-ttu-id="a4a24-214">L’état correct est ensuite trouvé en transformant la base de calcul, ce qui correspond à l’application de $ SH $ au vecteur d’État Quantum. dans l’extrait de code ci-dessus, la transformation en retour à la base de calcul est gérée automatiquement par l’utilisation du `within … apply` bloc.</span><span class="sxs-lookup"><span data-stu-id="a4a24-214">The correct state would then be found by transforming back to the computational basis, which amounts to applying $SH$ to the quantum state vector; in the above snippet, the transformation back to the computational basis is handled automatically by the use of the `within … apply` block.</span></span>

<span data-ttu-id="a4a24-215">Dans Q# , nous disons le résultat---autrement dit, les informations classiques extraites de l’interaction avec l’État---sont données par une `Result` valeur $ j \in \\ { \texttt { zéro } , l' \texttt { une } \\ } $ indiquant si le résultat se trouve dans le $ (-1) ^ j $ eigenspace de l’opérateur Pauli mesuré.</span><span class="sxs-lookup"><span data-stu-id="a4a24-215">In Q#, we say the outcome---that is, the classical information extracted from interacting with the state---is given by a `Result` value $j \in \\{\texttt{Zero}, \texttt{One}\\}$ indicating if the result is in the $(-1)^j$ eigenspace of the Pauli operator measured.</span></span>


## <a name="multiple-qubit-measurements"></a><span data-ttu-id="a4a24-216">Mesures à plusieurs qubit</span><span class="sxs-lookup"><span data-stu-id="a4a24-216">Multiple-qubit measurements</span></span>

<span data-ttu-id="a4a24-217">Les mesures des opérateurs Pauli à plusieurs qubit sont définies de la même manière, comme le montre l’exemple suivant :</span><span class="sxs-lookup"><span data-stu-id="a4a24-217">Measurements of multi-qubit Pauli operators are defined similarly, as seen from:</span></span>

$$
<span data-ttu-id="a4a24-218">Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.</span><span class="sxs-lookup"><span data-stu-id="a4a24-218">Z\otimes Z = \begin{bmatrix}1 &0 &0&0\\\\  0&-1&0&0\\\\ 0&0&-1&0\\\\ 0&0&0&1\end{bmatrix}.</span></span>
$$

<span data-ttu-id="a4a24-219">Ainsi, les produits tenseur de deux opérateurs Pauli- $ Z $ forment une matrice composée de deux espaces composés de $ + 1 $ et $ -1 $ valeurs propres.</span><span class="sxs-lookup"><span data-stu-id="a4a24-219">Thus the tensor products of two Pauli-$Z$ operators forms a matrix composed of two spaces consisting of $+1$ and $-1$ eigenvalues.</span></span>
<span data-ttu-id="a4a24-220">Comme avec le cas qubit, les deux constituent un demi-espace, ce qui signifie que la moitié de l’espace de vecteur accessible appartient au $ + 1 $ eigenspace et la moitié restante à la $ eigenspace-1 $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-220">As with the single-qubit case, both constitute a half-space meaning that half of the accessible vector space belongs to the $+1$ eigenspace and the remaining half to the $-1$ eigenspace.</span></span>
<span data-ttu-id="a4a24-221">En général, il est facile de voir à partir de la définition du produit tenseur que tout produit tenseur d’opérateurs Pauli- $ Z $ et l’identité en obéissent également.</span><span class="sxs-lookup"><span data-stu-id="a4a24-221">In general, it is easy to see from the definition of the tensor product that any tensor product of Pauli-$Z$ operators and the identity also obeys this.</span></span>
<span data-ttu-id="a4a24-222">Par exemple,</span><span class="sxs-lookup"><span data-stu-id="a4a24-222">For example,</span></span>

$$
\begin{align}
    <span data-ttu-id="a4a24-223">\otimes \boldone Z =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="a4a24-223">Z \otimes \boldone = \begin{bmatrix}</span></span>
        <span data-ttu-id="a4a24-224">1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-224">1 &  0 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="a4a24-225">0 &  1 &  0 &  0 \\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-225">0 &  1 &  0 &  0 \\\\</span></span>
        <span data-ttu-id="a4a24-226">0 & & -1 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-226">0 &  0 & -1 &  0 \\\\</span></span>
        <span data-ttu-id="a4a24-227">0 0 0 & & & -1 \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="a4a24-227">0 &  0 &  0 & -1 \end{bmatrix}.</span></span>
\end{align}
$$

<span data-ttu-id="a4a24-228">Comme précédemment, toute transformation unitaire de ces matrices décrit également deux demi-espaces étiquetés par $ \pm 1 $ valeurs propres.</span><span class="sxs-lookup"><span data-stu-id="a4a24-228">As before, any unitary transformation of such matrices also describes two half-spaces labeled by $\pm 1$ eigenvalues.</span></span>
<span data-ttu-id="a4a24-229">Par exemple, $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  à partir de l’identité $ Z = HxH $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-229">For example, $X\otimes X = H\otimes H(Z\otimes Z)H\otimes H$  from the identity that $Z=HXH$.</span></span>
<span data-ttu-id="a4a24-230">Comme dans le cas d’une qubit, toutes les mesures Pauli à deux qubit peuvent être écrites en u $ ^ \dagger (Z \otimes \id ) u $ pour $ 4 \times 4 $ matrices unitaires $ u $ . Nous énumérons les transformations dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="a4a24-230">Similar to the one-qubit case, all two-qubit Pauli-measurements can be written as $U^\dagger (Z\otimes \id) U$ for $4\times 4$ unitary matrices $U$. We enumerate the transformations in the following table.</span></span>

> [!NOTE]
<span data-ttu-id="a4a24-231">>Dans le tableau ci-dessous, nous utilisons $ \operatorname { swap } $ pour indiquer la matrice >$$</span><span class="sxs-lookup"><span data-stu-id="a4a24-231">> In the table below, we use $\operatorname{SWAP}$ to indicate the matrix > $$</span></span>
<span data-ttu-id="a4a24-232">> \begin{align}</span><span class="sxs-lookup"><span data-stu-id="a4a24-232">> \begin{align}</span></span>
<span data-ttu-id="a4a24-233">>     \operatorname{ÉCHANGE } &=</span><span class="sxs-lookup"><span data-stu-id="a4a24-233">>     \operatorname{SWAP} & =</span></span>
<span data-ttu-id="a4a24-234">>     \left( \begin { matrice}</span><span class="sxs-lookup"><span data-stu-id="a4a24-234">>     \left(\begin{matrix}</span></span>
<span data-ttu-id="a4a24-235">>1 & 0 & 0 0 &\\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-235">>         1 & 0 & 0 & 0 \\\\</span></span>
<span data-ttu-id="a4a24-236">>         0 & 0 & 1 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-236">>         0 & 0 & 1 & 0 \\\\</span></span>
<span data-ttu-id="a4a24-237">>         0 & 1 & 0 & 0 \\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-237">>         0 & 1 & 0 & 0 \\\\</span></span>
<span data-ttu-id="a4a24-238">>0 0 0 & & & 1 > \end { matrice } \right ) >     \end{align}</span><span class="sxs-lookup"><span data-stu-id="a4a24-238">>         0 & 0 & 0 & 1 >     \end{matrix}\right) > \end{align}</span></span>
<span data-ttu-id="a4a24-239">> $$</span><span class="sxs-lookup"><span data-stu-id="a4a24-239">> $$</span></span>
<span data-ttu-id="a4a24-240">> utilisé pour simuler l’opération intrinsèque [`SWAP`](xref:microsoft.quantum.intrinsic) .</span><span class="sxs-lookup"><span data-stu-id="a4a24-240">> used to simulate the intrinsic operation [`SWAP`](xref:microsoft.quantum.intrinsic).</span></span>

<span data-ttu-id="a4a24-241">|Transformation d’unité de mesure Pauli ||</span><span class="sxs-lookup"><span data-stu-id="a4a24-241">|Pauli Measurement     |Unitary transformation  |</span></span>
|----------------------|------------------------|
<span data-ttu-id="a4a24-242">|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|</span><span class="sxs-lookup"><span data-stu-id="a4a24-242">| $Z\otimes \boldone$ | $\boldone\otimes \boldone$ |</span></span>
<span data-ttu-id="a4a24-243">|$ \otimes \boldone X $ | $ \otimes \boldone H $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-243">| $X\otimes \boldone$ | $H\otimes \boldone$ |</span></span>
<span data-ttu-id="a4a24-244">|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-244">| $Y\otimes \boldone$ | $HS^\dagger\otimes \boldone$ |</span></span>
<span data-ttu-id="a4a24-245">|$\boldone \otimes $ | $ \operatorname { échange } Z $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-245">| $\boldone \otimes Z$ | $\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="a4a24-246">|$\boldone \otimes $ | $ \otimes \boldone \operatorname { échange } X (H $ )|</span><span class="sxs-lookup"><span data-stu-id="a4a24-246">| $\boldone \otimes X$ | $(H\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="a4a24-247">|$\boldone \otimes $ | $ \dagger \otimes \boldone \operatorname { échange } Y $ (HS ^)|</span><span class="sxs-lookup"><span data-stu-id="a4a24-247">| $\boldone \otimes Y$ | $(HS^\dagger\otimes \boldone)\operatorname{SWAP}$ |</span></span>
<span data-ttu-id="a4a24-248">|$Z \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-248">| $Z\otimes Z$ | $\operatorname{CNOT}\_{10}$ |</span></span>
<span data-ttu-id="a4a24-249">|$X \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } (H \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-249">| $X\otimes Z$ | $\operatorname{CNOT}\_{10}(H\otimes \boldone)$ |</span></span>
<span data-ttu-id="a4a24-250">|$Y \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-250">| $Y\otimes Z$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes \boldone)$ |</span></span>
<span data-ttu-id="a4a24-251">|$Z \otimes X $ | $ \operatorname { cnotin } \_ { 10 } ( \boldone \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-251">| $Z\otimes X$ | $\operatorname{CNOT}\_{10}(\boldone\otimes H)$ |</span></span>
<span data-ttu-id="a4a24-252">|$X \otimes X $ | $ \operatorname { cnotin } \_ { 10 } (h \otimes h) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-252">| $X\otimes X$ | $\operatorname{CNOT}\_{10}(H\otimes H)$ |</span></span>
<span data-ttu-id="a4a24-253">|$Y \otimes X $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes H) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-253">| $Y\otimes X$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes H)$ |</span></span>
<span data-ttu-id="a4a24-254">|$Z \otimes O $ | $ \operatorname { cnotin } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-254">| $Z\otimes Y$ | $\operatorname{CNOT}\_{10}(\boldone \otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="a4a24-255">|$X \otimes O $ | $ \operatorname { cnotin } \_ { 10 } (H \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-255">| $X\otimes Y$ | $\operatorname{CNOT}\_{10}(H\otimes HS^\dagger)$ |</span></span>
<span data-ttu-id="a4a24-256">|$Y \otimes O $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|</span><span class="sxs-lookup"><span data-stu-id="a4a24-256">| $Y\otimes Y$ | $\operatorname{CNOT}\_{10}(HS^\dagger\otimes HS^\dagger)$ |</span></span>

<span data-ttu-id="a4a24-257">Ici, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) opération s’affiche pour la raison suivante.</span><span class="sxs-lookup"><span data-stu-id="a4a24-257">Here, the [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) operation appears for the following reason.</span></span>
<span data-ttu-id="a4a24-258">Chaque mesure Pauli qui n’inclut pas la $ \boldone $ matrice est équivalente à une unité à $ z \otimes z $ par le raisonnement ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a4a24-258">Each Pauli measurement that does not include the $\boldone$ matrix is equivalent up to a unitary to $Z\otimes Z$ by the above reasoning.</span></span>
<span data-ttu-id="a4a24-259">Le valeurs propres de $ z \otimes z $ dépend uniquement de la parité des qubits qui composent chaque vecteur de base de calcul, et les opérations non contrôlées servent à calculer cette parité et à la stocker dans le premier bit.</span><span class="sxs-lookup"><span data-stu-id="a4a24-259">The eigenvalues of $Z\otimes Z$ only depend on the parity of the qubits that comprise each computational basis vector, and the controlled-not operations serve to compute this parity and store it in the first bit.</span></span>
<span data-ttu-id="a4a24-260">Une fois le premier bit mesuré, nous pouvons récupérer l’identité du demi-espace résultant, ce qui équivaut à mesurer l’opérateur Pauli.</span><span class="sxs-lookup"><span data-stu-id="a4a24-260">Then once the first bit is measured, we can recover the identity of the resultant half-space, which is equivalent to measuring the Pauli operator.</span></span>

<span data-ttu-id="a4a24-261">Une remarque supplémentaire : s’il peut être tentant de supposer que la mesure $ z \otimes z $ est identique à la mesure séquentielle de $ z \otimes \mathbb { 1, } $ puis à $ \mathbb { 1 } \otimes z $ , cette hypothèse est fausse.</span><span class="sxs-lookup"><span data-stu-id="a4a24-261">One additional note: while it may be tempting to assume that measuring $Z\otimes Z$ is the same as sequentially measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$, this assumption would be false.</span></span>
<span data-ttu-id="a4a24-262">La raison est que la mesure $ z \otimes z $ projette l’État Quantum dans le $ eigenstate + 1 $ ou $ -1 $ de ces opérateurs.</span><span class="sxs-lookup"><span data-stu-id="a4a24-262">The reason is that measuring $Z\otimes Z$ projects the quantum state into either the $+1$ or $-1$ eigenstate of these operators.</span></span>
<span data-ttu-id="a4a24-263">La mesure de $ z \otimes \mathbb { 1 } $ , puis de $ \mathbb { 1 } \otimes Z $ projette le vecteur d’État Quantum tout d’abord sur un demi-espace de $ z \otimes \mathbb { 1 } $ , puis sur un demi-espace de $ \mathbb { 1 } \otimes z $ . Étant donné qu’il y a quatre vecteurs de base de calcul, l’exécution des deux mesures permet de réduire l’État à un quart d’espace et, par conséquent, de la réduire à un vecteur de calcul unique.</span><span class="sxs-lookup"><span data-stu-id="a4a24-263">Measuring $Z\otimes \mathbb{1}$ and then $\mathbb{1} \otimes Z$ projects the quantum state vector first onto a half space of $Z\otimes \mathbb{1}$ and then onto a half space of $\mathbb{1} \otimes Z$. As there are four computational basis vectors, performing both measurements reduces the state to a quarter-space and hence reduces it to a single computational basis vector.</span></span>

## <a name="correlations-between-qubits"></a><span data-ttu-id="a4a24-264">Corrélations entre qubits</span><span class="sxs-lookup"><span data-stu-id="a4a24-264">Correlations between qubits</span></span>
<span data-ttu-id="a4a24-265">Une autre façon d’examiner la mesure des produits tenseur des matrices Pauli, tels que $ x \otimes x $ ou $ z \otimes z, $ est que ces mesures vous permettent de consulter les informations stockées dans les corrélations entre les deux qubits.</span><span class="sxs-lookup"><span data-stu-id="a4a24-265">Another way of looking at measuring tensor products of Pauli matrices such as $X\otimes X$ or $Z\otimes Z$ is that these measurements let you look at information stored in the correlations between the two qubits.</span></span>
<span data-ttu-id="a4a24-266">$La mesure X \otimes \id $ vous permet de consulter les informations qui sont stockées localement dans le premier qubit.</span><span class="sxs-lookup"><span data-stu-id="a4a24-266">Measuring $X\otimes \id$ lets you look at information that is locally stored in the first qubit.</span></span>
<span data-ttu-id="a4a24-267">Alors que les deux types de mesures sont tout aussi utiles dans Quantum Computing, le premier éclaire la puissance de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="a4a24-267">While both types of measurements are equally valuable in quantum computing, the former illuminates the power of quantum computing.</span></span>
<span data-ttu-id="a4a24-268">Il révèle que, dans Quantum Computing, les informations que vous souhaitez apprendre ne sont pas stockées dans un qubit unique mais plutôt stockées non localement dans toutes les qubits en même temps, et par conséquent uniquement en les examinant par une mesure conjointe (p. ex. $ z \otimes z $ ). ces informations deviennent manifestes.</span><span class="sxs-lookup"><span data-stu-id="a4a24-268">It reveals that in quantum computing, often the information you wish to learn is not stored in any single qubit but rather stored non-locally in all the qubits at once, and therefore only by looking at it through a joint measurement (e.g. $Z\otimes Z$) does this information become manifest.</span></span>

<span data-ttu-id="a4a24-269">Par exemple, dans la correction des erreurs, nous souhaitons souvent savoir quelle erreur s’est produite lors de l’apprentissage de l’état que nous tentons de protéger.</span><span class="sxs-lookup"><span data-stu-id="a4a24-269">For example, in error correction, we often wish to learn what error occurred while learning nothing about the state that we're trying to protect.</span></span>
<span data-ttu-id="a4a24-270">L' [exemple de code de retournement de bits](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) montre un exemple de la façon dont vous pouvez effectuer cette opération à l’aide de mesures telles que $ z z et z \otimes \otimes \id $ $ \id \otimes \otimes z $ . < --TODO : remplacez ceci par un lien vers le navigateur Samples dès que l’exemple de code de retournement de bits est intégré.</span><span class="sxs-lookup"><span data-stu-id="a4a24-270">The [bit-flip code sample](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) shows an example of how you can do that using measurements like $Z \otimes Z \otimes \id$ and $\id \otimes Z \otimes Z$. <!-- TODO: change this to a link to the samples browser as soon as the bit-flip code sample is on-boarded.</span></span> -->

<span data-ttu-id="a4a24-271">Les opérateurs Pauli arbitraires tels que $ X \otimes Y \otimes Z \otimes \boldone $ peuvent également être mesurés.</span><span class="sxs-lookup"><span data-stu-id="a4a24-271">Arbitrary Pauli operators such as $X\otimes Y \otimes Z \otimes \boldone$ can also be measured.</span></span>
<span data-ttu-id="a4a24-272">Tous les produits tenseur des opérateurs Pauli n’ont que deux valeurs propres $ \pm 1 $ et les deux eigenspaces constituent des demi-espaces de l’ensemble de l’espace de vecteur.</span><span class="sxs-lookup"><span data-stu-id="a4a24-272">All such tensor products of Pauli operators have only two eigenvalues $\pm 1$ and both eigenspaces constitute half-spaces of the entire vector space.</span></span>
<span data-ttu-id="a4a24-273">Ils coïncident donc avec les exigences indiquées ci-dessus.</span><span class="sxs-lookup"><span data-stu-id="a4a24-273">Thus they coincide with the requirements stated above.</span></span>

<span data-ttu-id="a4a24-274">Dans Q# , ces mesures retournent $ j $ si la mesure produit un résultat dans le eigenspace du signe $ (-1) ^ j $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-274">In Q#, such measurements return $j$ if the measurement yields a result in the eigenspace of sign $(-1)^j$.</span></span>
<span data-ttu-id="a4a24-275">Avoir des mesures Pauli comme fonctionnalité intégrée dans Q# est utile, car la mesure de ces opérateurs nécessite des chaînes longues de transformations de base et non contrôlées pour décrire le $ portail U de diagonale $ nécessaire pour exprimer l’opération en tant que produit tenseur de $ Z $ et $ \id $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-275">Having Pauli measurements as a built-in feature in Q# is helpful because measuring such operators requires long chains of controlled-NOT gates and basis transformations to describe the diagonalizing $U$ gate needed to express the operation as a tensor product of $Z$ and $\id$.</span></span>
<span data-ttu-id="a4a24-276">En étant en mesure de spécifier que vous souhaitez effectuer une de ces mesures prédéfinies, vous n’avez pas besoin de vous soucier de la façon de transformer votre base de manière à ce qu’une mesure de base de calcul fournisse les informations nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a4a24-276">By being able to specify that you wish to do one of these pre-defined measurements, you don't need to worry about how to transform your basis such that a computational basis measurement provides the necessary information.</span></span>
<span data-ttu-id="a4a24-277">Q# gère automatiquement toutes les transformations de base nécessaires.</span><span class="sxs-lookup"><span data-stu-id="a4a24-277">Q# handles all the necessary basis transformations for you automatically.</span></span>
<span data-ttu-id="a4a24-278">Pour plus d’informations, consultez [`Measure`](xref:microsoft.quantum.intrinsic.measure) les [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) opérations et.</span><span class="sxs-lookup"><span data-stu-id="a4a24-278">For more information, see the [`Measure`](xref:microsoft.quantum.intrinsic.measure) and [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) operations.</span></span>

## <a name="the-no-cloning-theorem"></a><span data-ttu-id="a4a24-279">Le pas de clonage</span><span class="sxs-lookup"><span data-stu-id="a4a24-279">The No-Cloning Theorem</span></span>

<span data-ttu-id="a4a24-280">Les informations de Quantum sont puissantes.</span><span class="sxs-lookup"><span data-stu-id="a4a24-280">Quantum information is powerful.</span></span>
<span data-ttu-id="a4a24-281">Cela nous permet de faire des choses étonnantes, telles que les chiffres de facteur de façon exponentielle plus rapide que les algorithmes classiques les plus connus, ou de simuler efficacement des systèmes d’électrons corrélés qui nécessitent un coût exponentiel pour une simulation précise.</span><span class="sxs-lookup"><span data-stu-id="a4a24-281">It enables us to do amazing things such as factor numbers exponentially faster than the best known classical algorithms, or efficiently simulate correlated electron systems that classically require exponential cost to simulate accurately.</span></span>
<span data-ttu-id="a4a24-282">Toutefois, il existe des limitations à la puissance de quantum computing.</span><span class="sxs-lookup"><span data-stu-id="a4a24-282">However, there are limitations to the power of quantum computing.</span></span>
<span data-ttu-id="a4a24-283">L’une de ces limitations est donnée par le seuil de *non-clonage*.</span><span class="sxs-lookup"><span data-stu-id="a4a24-283">One such limitation is given by the *No-Cloning Theorem*.</span></span>

<span data-ttu-id="a4a24-284">Le nom du terme de non-clonage est avec justesse.</span><span class="sxs-lookup"><span data-stu-id="a4a24-284">The No-Cloning Theorem is aptly named.</span></span>
<span data-ttu-id="a4a24-285">Il interdit le clonage d’États de Quantum génériques par un ordinateur Quantum.</span><span class="sxs-lookup"><span data-stu-id="a4a24-285">It disallows cloning of generic quantum states by a quantum computer.</span></span>
<span data-ttu-id="a4a24-286">La preuve du pas de l’un est remarquablement simple.</span><span class="sxs-lookup"><span data-stu-id="a4a24-286">The proof of the theorem is remarkably straightforward.</span></span>
<span data-ttu-id="a4a24-287">Bien qu’une preuve complète de l’qubits de non-clonage soit un peu trop technique pour notre discussion ici, la preuve dans le cas d’un auxiliaire supplémentaire se trouve dans notre étendue (les qubits auxiliaires sont qubits utilisés pour l’espace de travail pendant un calcul et sont facilement utilisés et gérés dans Q# , consultez [qubits empruntés](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span><span class="sxs-lookup"><span data-stu-id="a4a24-287">While a full proof of the no-cloning theorem is a little too technical for our discussion here, the proof in the case of no additional auxiliary qubits is within our scope (auxiliary qubits are qubits used for scratch space during a computation and are easily used and managed in Q#, see [borrowed qubits](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).</span></span>

<span data-ttu-id="a4a24-288">Pour un tel ordinateur Quantum, l’opération de clonage doit être décrite par une matrice d’unités.</span><span class="sxs-lookup"><span data-stu-id="a4a24-288">For such a quantum computer, the cloning operation must be described by a unitary matrix.</span></span>
<span data-ttu-id="a4a24-289">Nous interdisent la mesure, car cela corromprait l’État Quantum que nous essayons de cloner.</span><span class="sxs-lookup"><span data-stu-id="a4a24-289">We disallow measurement, since it would corrupt the quantum state we are trying to clone.</span></span>
<span data-ttu-id="a4a24-290">Pour simuler l’opération de clonage, nous voulons que la matrice d’unités utilise la propriété qui $$</span><span class="sxs-lookup"><span data-stu-id="a4a24-290">To simulate the cloning operation, we want the unitary matrix used to have the property that $$</span></span>
  <span data-ttu-id="a4a24-291">U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="a4a24-291">U \ket{\psi} \ket{0} = \ket{\psi} \ket{\psi}</span></span>
$$
<span data-ttu-id="a4a24-292">pour n’importe quel état $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-292">for any state $\ket{\psi}$.</span></span>
<span data-ttu-id="a4a24-293">La propriété de linéarité de la multiplication de matrice implique alors que pour n’importe quel autre État Quantum $ \ket { \phi } $ ,</span><span class="sxs-lookup"><span data-stu-id="a4a24-293">The linearity property of matrix multiplication then implies that for any second quantum state $\ket{\phi}$,</span></span>

$$
\begin{align}
    <span data-ttu-id="a4a24-294">U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="a4a24-294">U \left[ \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right] \ket{0}</span></span>
    <span data-ttu-id="a4a24-295">&= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}</span><span class="sxs-lookup"><span data-stu-id="a4a24-295">& = \frac{1}{\sqrt{2}} U\ket{\phi}\ket{0}</span></span>
      <span data-ttu-id="a4a24-296">+ \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-296">+ \frac{1}{\sqrt{2}} U\ket{\psi}\ket{0} \\\\</span></span>
    <span data-ttu-id="a4a24-297">&= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}</span><span class="sxs-lookup"><span data-stu-id="a4a24-297">& = \frac{1}{\sqrt{2}} \left( \ket{\phi} \ket{\phi} + \ket{\psi} \ket{\psi}</span></span>
        <span data-ttu-id="a4a24-298">\right) \\\\</span><span class="sxs-lookup"><span data-stu-id="a4a24-298">\right) \\\\</span></span>
    <span data-ttu-id="a4a24-299">&\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).</span><span class="sxs-lookup"><span data-stu-id="a4a24-299">& \ne \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right) \otimes \left( \frac{1}{\sqrt{2}}\left(\ket{\phi}+\ket{\psi} \right) \right).</span></span>
\end{align}
$$

<span data-ttu-id="a4a24-300">Cela fournit l’intuition fondamentale derrière le principe de non-clonage : tout appareil qui copie un État Quantum inconnu doit provoquer des erreurs au moins dans certains États qu’il copie.</span><span class="sxs-lookup"><span data-stu-id="a4a24-300">This provides the fundamental intuition behind the No-Cloning Theorem: any device that copies an unknown quantum state must induce errors on at least some of the states it copies.</span></span>
<span data-ttu-id="a4a24-301">Tandis que l’hypothèse clé selon laquelle le cloner agit de manière linéaire sur l’état d’entrée peut être violée par l’ajout et la mesure des qubits auxiliaires, ces interactions fuient également des informations sur le système via les statistiques de mesure et empêchent le clonage exact dans de tels cas.</span><span class="sxs-lookup"><span data-stu-id="a4a24-301">While the key assumption that the cloner acts linearly on the input state can be violated through the addition and measurement of auxiliary qubits, such interactions also leak information about the system through the measurement statistics and prevent exact cloning in such cases as well.</span></span>
<span data-ttu-id="a4a24-302">Pour obtenir une preuve plus complète du titre de non-clonage, consultez [pour plus d’informations](xref:microsoft.quantum.more-information).</span><span class="sxs-lookup"><span data-stu-id="a4a24-302">For a more complete proof of the No-Cloning Theorem see [For more information](xref:microsoft.quantum.more-information).</span></span>

<span data-ttu-id="a4a24-303">Le point de vue de la non-clonage est important pour la compréhension qualitative de l’informatique Quantum, car si vous pouviez cloner des États quantiques de façon inonéreuse, vous bénéficiez d’une capacité proche magique d’apprendre à partir des États quantiques.</span><span class="sxs-lookup"><span data-stu-id="a4a24-303">The No-Cloning Theorem is important for qualitative understanding of quantum computing because if you could clone quantum states inexpensively then you would be granted a near-magical ability to learn from quantum states.</span></span>
<span data-ttu-id="a4a24-304">En effet, vous pourriez violer le principe d’incertitude vaunted de Heisenberg.</span><span class="sxs-lookup"><span data-stu-id="a4a24-304">Indeed, you could violate Heisenberg's vaunted uncertainty principle.</span></span>
<span data-ttu-id="a4a24-305">Vous pouvez également utiliser un Cloner optimal pour obtenir un échantillon unique à partir d’une distribution de Quantum complexe et découvrir tout ce que vous pourriez savoir sur cette distribution à partir d’un seul exemple.</span><span class="sxs-lookup"><span data-stu-id="a4a24-305">Alternatively, you could use an optimal cloner to take a single sample from a complex quantum distribution and learn everything you could possibly learn about that distribution from just one sample.</span></span>
<span data-ttu-id="a4a24-306">Cela revient à retourner une pièce de monnaie et à observer des têtes, puis à dire à un ami sur le résultat de la réponse « Ah que la distribution de cette pièce de monnaie doit être de Bernoulli avec $ p = 0.512643 \ ldots $ ! »</span><span class="sxs-lookup"><span data-stu-id="a4a24-306">This would be like you flipping a coin and observing heads and then upon telling a friend about the result having them respond "Ah the distribution of that coin must be Bernoulli with $p=0.512643\ldots$!"</span></span>  <span data-ttu-id="a4a24-307">Une telle instruction serait non sensée, car un peu d’informations (le résultat des têtes) ne peut pas fournir les nombreux éléments d’informations nécessaires pour encoder la distribution sans aucune information préalable substantielle.</span><span class="sxs-lookup"><span data-stu-id="a4a24-307">Such a statement would be non-sensical because one bit of information (the heads outcome) simply cannot provide the many bits of information needed to encode the distribution without substantial prior information.</span></span>
<span data-ttu-id="a4a24-308">De même, sans informations préalables, nous ne pouvons pas parfaitement cloner un État Quantum, de la même façon que nous ne pouvons pas préparer un ensemble de ces pièces, sans connaître $ p $ .</span><span class="sxs-lookup"><span data-stu-id="a4a24-308">Similarly, without prior information we cannot perfectly clone a quantum state just as we cannot prepare an ensemble of such coins without knowing $p$.</span></span>

<span data-ttu-id="a4a24-309">Les informations ne sont pas gratuites dans quantum computing.</span><span class="sxs-lookup"><span data-stu-id="a4a24-309">Information is not free in quantum computing.</span></span>
<span data-ttu-id="a4a24-310">Chaque qubit mesuré fournit un seul bit d’informations et le principe de non-clonage indique qu’il n’existe pas de porte dérobée pouvant être exploitée pour contourner le compromis fondamental entre les informations acquises sur le système et la perturbation invoquée.</span><span class="sxs-lookup"><span data-stu-id="a4a24-310">Each qubit measured gives a single bit of information, and the No-Cloning Theorem shows that there is no backdoor that can be exploited to get around the fundamental tradeoff between information gained about the system and the disturbance invoked upon it.</span></span>
