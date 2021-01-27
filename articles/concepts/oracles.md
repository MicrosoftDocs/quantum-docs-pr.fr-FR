---
<span data-ttu-id="53dca-101">title : description d’Oracle Quantum : Apprenez à utiliser et à définir des opérations de boîte noire à l’aide d’Oracle Quantum, qui sont utilisées comme entrée d’un autre algorithme.</span><span class="sxs-lookup"><span data-stu-id="53dca-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="53dca-102">Auteur : cgranade UID : Microsoft. Quantum. concepts. Oracle ms. Author : chgranad ms. Date : 07/11/2018 ms. rubrique : Conceptual No-Loc :</span><span class="sxs-lookup"><span data-stu-id="53dca-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: chgranad ms.date: 07/11/2018 ms.topic: conceptual no-loc:</span></span>
- <span data-ttu-id="53dca-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="53dca-103">"Q#"</span></span>
- <span data-ttu-id="53dca-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="53dca-104">"$$v"</span></span>
- <span data-ttu-id="53dca-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="53dca-105">"$$"</span></span>
- <span data-ttu-id="53dca-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="53dca-106">"$$"</span></span>
- <span data-ttu-id="53dca-107">"$"</span><span class="sxs-lookup"><span data-stu-id="53dca-107">"$"</span></span>
- <span data-ttu-id="53dca-108">"$"</span><span class="sxs-lookup"><span data-stu-id="53dca-108">"$"</span></span>
- <span data-ttu-id="53dca-109">"$"</span><span class="sxs-lookup"><span data-stu-id="53dca-109">"$"</span></span>
- <span data-ttu-id="53dca-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="53dca-110">"$$"</span></span>
- <span data-ttu-id="53dca-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="53dca-111">"\cdots"</span></span>
- <span data-ttu-id="53dca-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="53dca-112">"bmatrix"</span></span>
- <span data-ttu-id="53dca-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="53dca-113">"\ddots"</span></span>
- <span data-ttu-id="53dca-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="53dca-114">"\equiv"</span></span>
- <span data-ttu-id="53dca-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="53dca-115">"\sum"</span></span>
- <span data-ttu-id="53dca-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="53dca-116">"\begin"</span></span>
- <span data-ttu-id="53dca-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="53dca-117">"\end"</span></span>
- <span data-ttu-id="53dca-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="53dca-118">"\sqrt"</span></span>
- <span data-ttu-id="53dca-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="53dca-119">"\otimes"</span></span>
- <span data-ttu-id="53dca-120">"{"</span><span class="sxs-lookup"><span data-stu-id="53dca-120">"{"</span></span>
- <span data-ttu-id="53dca-121">"}"</span><span class="sxs-lookup"><span data-stu-id="53dca-121">"}"</span></span>
- <span data-ttu-id="53dca-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="53dca-122">"\text"</span></span>
- <span data-ttu-id="53dca-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="53dca-123">"\phi"</span></span>
- <span data-ttu-id="53dca-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="53dca-124">"\kappa"</span></span>
- <span data-ttu-id="53dca-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="53dca-125">"\psi"</span></span>
- <span data-ttu-id="53dca-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="53dca-126">"\alpha"</span></span>
- <span data-ttu-id="53dca-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="53dca-127">"\beta"</span></span>
- <span data-ttu-id="53dca-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="53dca-128">"\gamma"</span></span>
- <span data-ttu-id="53dca-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="53dca-129">"\delta"</span></span>
- <span data-ttu-id="53dca-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="53dca-130">"\omega"</span></span>
- <span data-ttu-id="53dca-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="53dca-131">"\bra"</span></span>
- <span data-ttu-id="53dca-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="53dca-132">"\ket"</span></span>
- <span data-ttu-id="53dca-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="53dca-133">"\boldone"</span></span>
- <span data-ttu-id="53dca-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="53dca-134">"\\\\"</span></span>
- <span data-ttu-id="53dca-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="53dca-135">"\\"</span></span>
- <span data-ttu-id="53dca-136">"="</span><span class="sxs-lookup"><span data-stu-id="53dca-136">"="</span></span>
- <span data-ttu-id="53dca-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="53dca-137">"\frac"</span></span>
- <span data-ttu-id="53dca-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="53dca-138">"\text"</span></span>
- <span data-ttu-id="53dca-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="53dca-139">"\mapsto"</span></span>
- <span data-ttu-id="53dca-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="53dca-140">"\dagger"</span></span>
- <span data-ttu-id="53dca-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="53dca-141">"\to"</span></span>
- <span data-ttu-id="53dca-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="53dca-142">"\begin{cases}"</span></span>
- <span data-ttu-id="53dca-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="53dca-143">"\end{cases}"</span></span>
- <span data-ttu-id="53dca-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="53dca-144">"\operatorname"</span></span>
- <span data-ttu-id="53dca-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="53dca-145">"\braket"</span></span>
- <span data-ttu-id="53dca-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="53dca-146">"\id"</span></span>
- <span data-ttu-id="53dca-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="53dca-147">"\expect"</span></span>
- <span data-ttu-id="53dca-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="53dca-148">"\defeq"</span></span>
- <span data-ttu-id="53dca-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="53dca-149">"\variance"</span></span>
- <span data-ttu-id="53dca-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="53dca-150">"\dd"</span></span>
- <span data-ttu-id="53dca-151">"&"</span><span class="sxs-lookup"><span data-stu-id="53dca-151">"&"</span></span>
- <span data-ttu-id="53dca-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="53dca-152">"\begin{align}"</span></span>
- <span data-ttu-id="53dca-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="53dca-153">"\end{align}"</span></span>
- <span data-ttu-id="53dca-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="53dca-154">"\Lambda"</span></span>
- <span data-ttu-id="53dca-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="53dca-155">"\lambda"</span></span>
- <span data-ttu-id="53dca-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="53dca-156">"\Omega"</span></span>
- <span data-ttu-id="53dca-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="53dca-157">"\mathrm"</span></span>
- <span data-ttu-id="53dca-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="53dca-158">"\left"</span></span>
- <span data-ttu-id="53dca-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="53dca-159">"\right"</span></span>
- <span data-ttu-id="53dca-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="53dca-160">"\qquad"</span></span>
- <span data-ttu-id="53dca-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="53dca-161">"\times"</span></span>
- <span data-ttu-id="53dca-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="53dca-162">"\big"</span></span>
- <span data-ttu-id="53dca-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="53dca-163">"\langle"</span></span>
- <span data-ttu-id="53dca-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="53dca-164">"\rangle"</span></span>
- <span data-ttu-id="53dca-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="53dca-165">"\bigg"</span></span>
- <span data-ttu-id="53dca-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="53dca-166">"\Big"</span></span>
- <span data-ttu-id="53dca-167">"|"</span><span class="sxs-lookup"><span data-stu-id="53dca-167">"|"</span></span>
- <span data-ttu-id="53dca-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="53dca-168">"\mathbb"</span></span>
- <span data-ttu-id="53dca-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="53dca-169">"\vec"</span></span>
- <span data-ttu-id="53dca-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="53dca-170">"\in"</span></span>
- <span data-ttu-id="53dca-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="53dca-171">"\texttt"</span></span>
- <span data-ttu-id="53dca-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="53dca-172">"\ne"</span></span>
- <span data-ttu-id="53dca-173">"<"</span><span class="sxs-lookup"><span data-stu-id="53dca-173">"<"</span></span>
- <span data-ttu-id="53dca-174">">"</span><span class="sxs-lookup"><span data-stu-id="53dca-174">">"</span></span>
- <span data-ttu-id="53dca-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="53dca-175">"\leq"</span></span>
- <span data-ttu-id="53dca-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="53dca-176">"\geq"</span></span>
- <span data-ttu-id="53dca-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="53dca-177">"~~"</span></span>
- <span data-ttu-id="53dca-178">"~"</span><span class="sxs-lookup"><span data-stu-id="53dca-178">"~"</span></span>
- <span data-ttu-id="53dca-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="53dca-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="53dca-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="53dca-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="53dca-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="53dca-181">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="53dca-182">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="53dca-182">Quantum Oracles</span></span>

<span data-ttu-id="53dca-183">Oracle $ O $ est une opération « boîte noire » utilisée comme entrée d’un autre algorithme.</span><span class="sxs-lookup"><span data-stu-id="53dca-183">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="53dca-184">Ces opérations sont souvent définies à l’aide d’une fonction classique $ f : \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ qui prend une $ $ entrée binaire n bits et produit $ une $ sortie binaire m bits.</span><span class="sxs-lookup"><span data-stu-id="53dca-184">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="53dca-185">Pour ce faire, considérons une entrée binaire particulière $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-185">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="53dca-186">Nous pouvons étiqueter les États qubit sous la forme $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-186">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="53dca-187">Nous pouvons tenter d’abord de définir $ o $ afin que $ o \ket { x } = \ket { f (x) } $ , mais cela pose quelques problèmes.</span><span class="sxs-lookup"><span data-stu-id="53dca-187">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="53dca-188">Premièrement, $ f $ peut avoir une taille différente d’entrée et de sortie ( $ n \ne m $ ), de sorte que l’application de $ O $ modifie le nombre de qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="53dca-188">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="53dca-189">Deuxièmement, même si $ n = m $ , la fonction ne peut pas être réversible : si $ f (x) = f (y) $ pour un $ x \ne y $ , puis $ o \ket { x } = o \ket { y } $ mais $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-189">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="53dca-190">Cela signifie que nous ne pourrons pas construire l’opération voisine $ O ^ \dagger $ et qu’Oracle doit avoir un voisin défini pour eux.</span><span class="sxs-lookup"><span data-stu-id="53dca-190">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="53dca-191">Définition d’Oracle par son effet sur les États de base de calcul</span><span class="sxs-lookup"><span data-stu-id="53dca-191">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="53dca-192">Nous pouvons traiter ces deux problèmes en introduisant un deuxième Registre de $ m $ qubits pour y répondre.</span><span class="sxs-lookup"><span data-stu-id="53dca-192">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="53dca-193">Nous allons ensuite définir l’effet de l’Oracle sur tous les États de base de calcul : pour tous les États $ x \in \\ { 0, 1 \\ } ^ n $ et $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="53dca-193">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="53dca-194">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="53dca-194">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="53dca-195">Maintenant $ o = o ^ \dagger $ par construction, nous avons résolu les deux problèmes précédents.</span><span class="sxs-lookup"><span data-stu-id="53dca-195">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
<span data-ttu-id="53dca-196">>Pour voir si $ o = o ^ { \dagger } $ , Notez que $ o ^ 2 = \boldone $ depuis $ un \oplus b \oplus b = a $ pour tout $ a, b \in \: :: No-Loc ({) ::: 0, 1 \: :: No-Loc (}) ::: $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-196">> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
<span data-ttu-id="53dca-197">>Par conséquent, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-197">> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="53dca-198">Plus important encore, la définition d’une Oracle de cette façon pour chaque État de base de calcul $ \ket { x } \ket { y } $ définit également la manière dont $ O $ agit pour tout autre État.</span><span class="sxs-lookup"><span data-stu-id="53dca-198">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="53dca-199">Cela vient immédiatement du fait que $ O $ , comme toutes les opérations de Quantum, est linéaire dans l’État sur lequel il agit.</span><span class="sxs-lookup"><span data-stu-id="53dca-199">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="53dca-200">Examinez l’opération hadarmard, par exemple, qui est définie par $ h \ket { 0 } = \ket { + } $ et $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-200">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="53dca-201">Si nous souhaitons savoir comment $ h $ agit sur $ \ket { + } $ , nous pouvons utiliser le $ h comme $ linéaire,</span><span class="sxs-lookup"><span data-stu-id="53dca-201">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="53dca-202">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="53dca-202">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           <span data-ttu-id="53dca-203">&= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="53dca-203">& = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="53dca-204">Dans le cas de la définition de notre $ O Oracle $ , nous pouvons utiliser de la même façon que n’importe quel état $ \ket { \psi } $ sur $ n + m $ qubits peut être écrit comme</span><span class="sxs-lookup"><span data-stu-id="53dca-204">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
<span data-ttu-id="53dca-205">\ket{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="53dca-205">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="53dca-206">où $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ représente les coefficients de l’état $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-206">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="53dca-207">Donc</span><span class="sxs-lookup"><span data-stu-id="53dca-207">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="53dca-208">O \ket { \psi } & = o \sum _{ x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum_ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="53dca-208">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             <span data-ttu-id="53dca-209">&= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="53dca-209">& = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="53dca-210">Oracle phase</span><span class="sxs-lookup"><span data-stu-id="53dca-210">Phase oracles</span></span>
<span data-ttu-id="53dca-211">Vous pouvez également encoder $ f $ dans une $ O Oracle $ en appliquant une _phase_ basée sur l’entrée à $ o $ . Par exemple, nous pouvons définir $ O de $ telle sorte que $$</span><span class="sxs-lookup"><span data-stu-id="53dca-211">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="53dca-212">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="53dca-212">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="53dca-213">Si une phase Oracle agit sur un registre initialement dans un état de base de calcul $ \ket { x } $ , cette phase est une phase globale qui n’est donc pas observable.</span><span class="sxs-lookup"><span data-stu-id="53dca-213">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="53dca-214">Toutefois, Oracle peut être une ressource très puissante si elle est appliquée à une superposition ou en tant qu’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="53dca-214">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="53dca-215">Par exemple, considérez une phase Oracle $ O_f $ pour une fonction qubit unique $ $ .</span><span class="sxs-lookup"><span data-stu-id="53dca-215">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="53dca-216">Cliquez $$</span><span class="sxs-lookup"><span data-stu-id="53dca-216">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="53dca-217">O_f \ket{+}</span><span class="sxs-lookup"><span data-stu-id="53dca-217">O_f \ket{+}</span></span>
        <span data-ttu-id="53dca-218">&=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="53dca-218">& = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="53dca-219">&=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="53dca-219">& = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="53dca-220">&=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="53dca-220">& = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        <span data-ttu-id="53dca-221">&=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="53dca-221">& = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

> [!NOTE]
<span data-ttu-id="53dca-222">>Notez que $ z ^ { -1 } = z ^ { \dagger } = Z $ et donc $ z ^ { f (0)-f (1) } = z ^ { f (1)-f (0) } .$</span><span class="sxs-lookup"><span data-stu-id="53dca-222">> Note that $Z^{-1}=Z^{\dagger}=Z$ and therefore $Z^{f(0)-f(1)}=Z^{f(1)-f(0)}.$</span></span>

<span data-ttu-id="53dca-223">Plus généralement, les deux vues d’Oracle peuvent être élargies pour représenter des fonctions classiques qui retournent des nombres réels au lieu d’un seul bit.</span><span class="sxs-lookup"><span data-stu-id="53dca-223">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="53dca-224">Le choix de la meilleure façon d’implémenter Oracle dépend fortement de la façon dont ce Oracle sera utilisé dans un algorithme donné.</span><span class="sxs-lookup"><span data-stu-id="53dca-224">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="53dca-225">Par exemple, l' [algorithme Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) s’appuie sur Oracle implémenté de la même façon, tandis que l' [algorithme de Grover s'](https://en.wikipedia.org/wiki/Grover's_algorithm) appuie sur Oracle implémenté de la seconde façon.</span><span class="sxs-lookup"><span data-stu-id="53dca-225">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="53dca-226">Pour plus d’informations, nous vous suggérons la discussion dans [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="53dca-226">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
