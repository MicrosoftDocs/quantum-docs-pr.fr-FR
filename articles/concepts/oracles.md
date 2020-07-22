---
<span data-ttu-id="77c15-101">title : description d’Oracle Quantum : Apprenez à utiliser et à définir des opérations de boîte noire à l’aide d’Oracle Quantum, qui sont utilisées comme entrée d’un autre algorithme.</span><span class="sxs-lookup"><span data-stu-id="77c15-101">title: Quantum oracles description: Learn how to work with and define quantum oracles, black box operations that are used as input to another algorithm.</span></span>
<span data-ttu-id="77c15-102">Auteur : cgranade UID : Microsoft. Quantum. concepts. Oracle ms. Author : Christopher.Granade@microsoft.com ms. Date : 07/11/2018 ms. topic : article No-Loc :</span><span class="sxs-lookup"><span data-stu-id="77c15-102">author: cgranade uid: microsoft.quantum.concepts.oracles ms.author: Christopher.Granade@microsoft.com ms.date: 07/11/2018 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="77c15-103">"$$"</span><span class="sxs-lookup"><span data-stu-id="77c15-103">"$$"</span></span>
- <span data-ttu-id="77c15-104">"$$"</span><span class="sxs-lookup"><span data-stu-id="77c15-104">"$$"</span></span>
- <span data-ttu-id="77c15-105">"$"</span><span class="sxs-lookup"><span data-stu-id="77c15-105">"$"</span></span>
- <span data-ttu-id="77c15-106">"$"</span><span class="sxs-lookup"><span data-stu-id="77c15-106">"$"</span></span>
- <span data-ttu-id="77c15-107">"$"</span><span class="sxs-lookup"><span data-stu-id="77c15-107">"$"</span></span>
- <span data-ttu-id="77c15-108">"$$"</span><span class="sxs-lookup"><span data-stu-id="77c15-108">"$$"</span></span>
- <span data-ttu-id="77c15-109">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="77c15-109">"\cdots"</span></span>
- <span data-ttu-id="77c15-110">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="77c15-110">"bmatrix"</span></span>
- <span data-ttu-id="77c15-111">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="77c15-111">"\ddots"</span></span>
- <span data-ttu-id="77c15-112">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="77c15-112">"\equiv"</span></span>
- <span data-ttu-id="77c15-113">"\sum"</span><span class="sxs-lookup"><span data-stu-id="77c15-113">"\sum"</span></span>
- <span data-ttu-id="77c15-114">"\begin"</span><span class="sxs-lookup"><span data-stu-id="77c15-114">"\begin"</span></span>
- <span data-ttu-id="77c15-115">"\end"</span><span class="sxs-lookup"><span data-stu-id="77c15-115">"\end"</span></span>
- <span data-ttu-id="77c15-116">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="77c15-116">"\sqrt"</span></span>
- <span data-ttu-id="77c15-117">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="77c15-117">"\otimes"</span></span>
- <span data-ttu-id="77c15-118">"{"</span><span class="sxs-lookup"><span data-stu-id="77c15-118">"{"</span></span>
- <span data-ttu-id="77c15-119">"}"</span><span class="sxs-lookup"><span data-stu-id="77c15-119">"}"</span></span>
- <span data-ttu-id="77c15-120">"\text"</span><span class="sxs-lookup"><span data-stu-id="77c15-120">"\text"</span></span>
- <span data-ttu-id="77c15-121">"\phi"</span><span class="sxs-lookup"><span data-stu-id="77c15-121">"\phi"</span></span>
- <span data-ttu-id="77c15-122">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="77c15-122">"\kappa"</span></span>
- <span data-ttu-id="77c15-123">"\psi"</span><span class="sxs-lookup"><span data-stu-id="77c15-123">"\psi"</span></span>
- <span data-ttu-id="77c15-124">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="77c15-124">"\alpha"</span></span>
- <span data-ttu-id="77c15-125">"\beta"</span><span class="sxs-lookup"><span data-stu-id="77c15-125">"\beta"</span></span>
- <span data-ttu-id="77c15-126">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="77c15-126">"\gamma"</span></span>
- <span data-ttu-id="77c15-127">"\delta"</span><span class="sxs-lookup"><span data-stu-id="77c15-127">"\delta"</span></span>
- <span data-ttu-id="77c15-128">"\omega"</span><span class="sxs-lookup"><span data-stu-id="77c15-128">"\omega"</span></span>
- <span data-ttu-id="77c15-129">"\bra"</span><span class="sxs-lookup"><span data-stu-id="77c15-129">"\bra"</span></span>
- <span data-ttu-id="77c15-130">"\ket"</span><span class="sxs-lookup"><span data-stu-id="77c15-130">"\ket"</span></span>
- <span data-ttu-id="77c15-131">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="77c15-131">"\boldone"</span></span>
- <span data-ttu-id="77c15-132">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="77c15-132">"\\\\"</span></span>
- <span data-ttu-id="77c15-133">"\\"</span><span class="sxs-lookup"><span data-stu-id="77c15-133">"\\"</span></span>
- <span data-ttu-id="77c15-134">"="</span><span class="sxs-lookup"><span data-stu-id="77c15-134">"="</span></span>
- <span data-ttu-id="77c15-135">"\frac"</span><span class="sxs-lookup"><span data-stu-id="77c15-135">"\frac"</span></span>
- <span data-ttu-id="77c15-136">"\text"</span><span class="sxs-lookup"><span data-stu-id="77c15-136">"\text"</span></span>
- <span data-ttu-id="77c15-137">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="77c15-137">"\mapsto"</span></span>
- <span data-ttu-id="77c15-138">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="77c15-138">"\dagger"</span></span>
- <span data-ttu-id="77c15-139">"\to"</span><span class="sxs-lookup"><span data-stu-id="77c15-139">"\to"</span></span>
- <span data-ttu-id="77c15-140">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="77c15-140">"\begin{cases}"</span></span>
- <span data-ttu-id="77c15-141">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="77c15-141">"\end{cases}"</span></span>
- <span data-ttu-id="77c15-142">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="77c15-142">"\operatorname"</span></span>
- <span data-ttu-id="77c15-143">"\braket"</span><span class="sxs-lookup"><span data-stu-id="77c15-143">"\braket"</span></span>
- <span data-ttu-id="77c15-144">"\id"</span><span class="sxs-lookup"><span data-stu-id="77c15-144">"\id"</span></span>
- <span data-ttu-id="77c15-145">"\expect"</span><span class="sxs-lookup"><span data-stu-id="77c15-145">"\expect"</span></span>
- <span data-ttu-id="77c15-146">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="77c15-146">"\defeq"</span></span>
- <span data-ttu-id="77c15-147">"\variance"</span><span class="sxs-lookup"><span data-stu-id="77c15-147">"\variance"</span></span>
- <span data-ttu-id="77c15-148">"\dd"</span><span class="sxs-lookup"><span data-stu-id="77c15-148">"\dd"</span></span>
- <span data-ttu-id="77c15-149">"&"</span><span class="sxs-lookup"><span data-stu-id="77c15-149">"&"</span></span>
- <span data-ttu-id="77c15-150">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="77c15-150">"\begin{align}"</span></span>
- <span data-ttu-id="77c15-151">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="77c15-151">"\end{align}"</span></span>
- <span data-ttu-id="77c15-152">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="77c15-152">"\Lambda"</span></span>
- <span data-ttu-id="77c15-153">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="77c15-153">"\lambda"</span></span>
- <span data-ttu-id="77c15-154">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="77c15-154">"\Omega"</span></span>
- <span data-ttu-id="77c15-155">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="77c15-155">"\mathrm"</span></span>
- <span data-ttu-id="77c15-156">"\left"</span><span class="sxs-lookup"><span data-stu-id="77c15-156">"\left"</span></span>
- <span data-ttu-id="77c15-157">"\right"</span><span class="sxs-lookup"><span data-stu-id="77c15-157">"\right"</span></span>
- <span data-ttu-id="77c15-158">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="77c15-158">"\qquad"</span></span>
- <span data-ttu-id="77c15-159">"\times"</span><span class="sxs-lookup"><span data-stu-id="77c15-159">"\times"</span></span>
- <span data-ttu-id="77c15-160">"\big"</span><span class="sxs-lookup"><span data-stu-id="77c15-160">"\big"</span></span>
- <span data-ttu-id="77c15-161">"\langle"</span><span class="sxs-lookup"><span data-stu-id="77c15-161">"\langle"</span></span>
- <span data-ttu-id="77c15-162">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="77c15-162">"\rangle"</span></span>
- <span data-ttu-id="77c15-163">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="77c15-163">"\bigg"</span></span>
- <span data-ttu-id="77c15-164">"\Big"</span><span class="sxs-lookup"><span data-stu-id="77c15-164">"\Big"</span></span>
- <span data-ttu-id="77c15-165">"|"</span><span class="sxs-lookup"><span data-stu-id="77c15-165">"|"</span></span>
- <span data-ttu-id="77c15-166">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="77c15-166">"\mathbb"</span></span>
- <span data-ttu-id="77c15-167">"\vec"</span><span class="sxs-lookup"><span data-stu-id="77c15-167">"\vec"</span></span>
- <span data-ttu-id="77c15-168">"\in"</span><span class="sxs-lookup"><span data-stu-id="77c15-168">"\in"</span></span>
- <span data-ttu-id="77c15-169">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="77c15-169">"\texttt"</span></span>
- <span data-ttu-id="77c15-170">"\ne"</span><span class="sxs-lookup"><span data-stu-id="77c15-170">"\ne"</span></span>
- <span data-ttu-id="77c15-171">"<"</span><span class="sxs-lookup"><span data-stu-id="77c15-171">"<"</span></span>
- <span data-ttu-id="77c15-172">">"</span><span class="sxs-lookup"><span data-stu-id="77c15-172">">"</span></span>
- <span data-ttu-id="77c15-173">"\leq"</span><span class="sxs-lookup"><span data-stu-id="77c15-173">"\leq"</span></span>
- <span data-ttu-id="77c15-174">"\geq"</span><span class="sxs-lookup"><span data-stu-id="77c15-174">"\geq"</span></span>
- <span data-ttu-id="77c15-175">"~~"</span><span class="sxs-lookup"><span data-stu-id="77c15-175">"~~"</span></span>
- <span data-ttu-id="77c15-176">"~"</span><span class="sxs-lookup"><span data-stu-id="77c15-176">"~"</span></span>
- <span data-ttu-id="77c15-177">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="77c15-177">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="77c15-178">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="77c15-178">"\end{bmatrix}"</span></span>
- <span data-ttu-id="77c15-179">"\_"</span><span class="sxs-lookup"><span data-stu-id="77c15-179">"\_"</span></span>

---
# <a name="quantum-oracles"></a><span data-ttu-id="77c15-180">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="77c15-180">Quantum Oracles</span></span>

<span data-ttu-id="77c15-181">Oracle $ O $ est une opération « boîte noire » utilisée comme entrée d’un autre algorithme.</span><span class="sxs-lookup"><span data-stu-id="77c15-181">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="77c15-182">Ces opérations sont souvent définies à l’aide d’une fonction classique $ f : \\ { 0, 1 \\ } ^ n \to \\ { 0, 1 \\ } ^ m $ qui prend une $ $ entrée binaire n bits et produit $ une $ sortie binaire m bits.</span><span class="sxs-lookup"><span data-stu-id="77c15-182">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="77c15-183">Pour ce faire, considérons une entrée binaire particulière $ x = (x_ { 0 } , x_ { 1 } , \dots, x_ { n-1 } ) $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-183">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="77c15-184">Nous pouvons étiqueter les États qubit sous la forme $ \ket { \vec { x } } = \ket { x_ { 0 } } \otimes \ket { x_ { 1 } } \otimes \cdots \otimes \ket { x_ { n-1 } } $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-184">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="77c15-185">Nous pouvons tenter d’abord de définir $ o $ afin que $ o \ket { x } = \ket { f (x) } $ , mais cela pose quelques problèmes.</span><span class="sxs-lookup"><span data-stu-id="77c15-185">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="77c15-186">Premièrement, $ f $ peut avoir une taille différente d’entrée et de sortie ( $ n \ne m $ ), de sorte que l’application de $ O $ modifie le nombre de qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="77c15-186">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="77c15-187">Deuxièmement, même si $ n = m $ , la fonction ne peut pas être réversible : si $ f (x) = f (y) $ pour un $ x \ne y $ , puis $ o \ket { x } = o \ket { y } $ mais $ o ^ \dagger o \ket { x } \ne o ^ \dagger o \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-187">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="77c15-188">Cela signifie que nous ne pourrons pas construire l’opération voisine $ O ^ \dagger $ et qu’Oracle doit avoir un voisin défini pour eux.</span><span class="sxs-lookup"><span data-stu-id="77c15-188">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="77c15-189">Définition d’Oracle par son effet sur les États de base de calcul</span><span class="sxs-lookup"><span data-stu-id="77c15-189">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="77c15-190">Nous pouvons traiter ces deux problèmes en introduisant un deuxième Registre de $ m $ qubits pour y répondre.</span><span class="sxs-lookup"><span data-stu-id="77c15-190">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="77c15-191">Nous allons ensuite définir l’effet de l’Oracle sur tous les États de base de calcul : pour tous les États $ x \in \\ { 0, 1 \\ } ^ n $ et $ y \in \\ { 0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="77c15-191">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

$$
\begin{align}
    <span data-ttu-id="77c15-192">O ( \ket { x } \otimes \ket { y } ) = \ket { x } \otimes \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="77c15-192">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

<span data-ttu-id="77c15-193">Maintenant $ o = o ^ \dagger $ par construction, nous avons résolu les deux problèmes précédents.</span><span class="sxs-lookup"><span data-stu-id="77c15-193">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
><span data-ttu-id="77c15-194">Pour voir si $ o = o ^ { \dagger } $ , Notez que $ o ^ 2 = \boldone $ depuis $ un \oplus b \oplus b = a $ pour tous les $ a, b \in \[ ! Opérationnel. NO-LOC ({)] 0, 1 \[ ! Opérationnel. NO-LOC (})] $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-194"> To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
><span data-ttu-id="77c15-195">Par conséquent, $ O \ket { x } \ket { y \oplus f (x) } = \ket { x } \ket { y \oplus f (x) \oplus f (x) } = \ket { x } \ket { y } $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-195"> As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="77c15-196">Plus important encore, la définition d’une Oracle de cette façon pour chaque État de base de calcul $ \ket { x } \ket { y } $ définit également la manière dont $ O $ agit pour tout autre État.</span><span class="sxs-lookup"><span data-stu-id="77c15-196">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="77c15-197">Cela vient immédiatement du fait que $ O $ , comme toutes les opérations de Quantum, est linéaire dans l’État sur lequel il agit.</span><span class="sxs-lookup"><span data-stu-id="77c15-197">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="77c15-198">Examinez l’opération hadarmard, par exemple, qui est définie par $ h \ket { 0 } = \ket { + } $ et $ h \ket { 1 } = \ket { - } $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-198">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="77c15-199">Si nous souhaitons savoir comment $ h $ agit sur $ \ket { + } $ , nous pouvons utiliser le $ h comme $ linéaire,</span><span class="sxs-lookup"><span data-stu-id="77c15-199">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

$$
\begin{align}
<span data-ttu-id="77c15-200">H \ket { + } & = \frac { 1 } { \sqrt { 2 } } h ( \ket { 0 }  +  \ket { 1 } ) = \frac { 1 } { \sqrt { 2 } } (h \ket { 0 } + h \ket { 1 } )\\\\</span><span class="sxs-lookup"><span data-stu-id="77c15-200">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\</span></span>
           &<span data-ttu-id="77c15-201">= \frac{ 1 } { \sqrt { 2 } } ( \ket { + }  +  \ket { - } ) = \frac 12 ( \ket { 0 }  +  \ket { 1 }  +  \ket { 0 }  -  \ket { 1 } ) = \ket { 0 } .</span><span class="sxs-lookup"><span data-stu-id="77c15-201"> = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
\end{align}
$$

<span data-ttu-id="77c15-202">Dans le cas de la définition de notre $ O Oracle $ , nous pouvons utiliser de la même façon que n’importe quel état $ \ket { \psi } $ sur $ n + m $ qubits peut être écrit comme</span><span class="sxs-lookup"><span data-stu-id="77c15-202">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

$$
\begin{align}
\ket<span data-ttu-id="77c15-203">{\psi}& = \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y}</span><span class="sxs-lookup"><span data-stu-id="77c15-203">{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
\end{align}
$$

<span data-ttu-id="77c15-204">où $ \alpha : \\ { 0, 1 \\ } ^ n \times \\ { 0, 1 \\ } ^ m \to \mathbb { C } $ représente les coefficients de l’état $ \ket { \psi } $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-204">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="77c15-205">Donc</span><span class="sxs-lookup"><span data-stu-id="77c15-205">Thus,</span></span>

$$
\begin{align}
<span data-ttu-id="77c15-206">O \ket { \psi } & = o \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y } x \\\\ 0 & , = 1 ^ n, y 0, 1 ^ m (x, y) O \sum _ { \in \\ { \\ } \in \\ { \\ } } \alpha \ket { x } \ket { y }\\\\</span><span class="sxs-lookup"><span data-stu-id="77c15-206">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\</span></span>
             &<span data-ttu-id="77c15-207">= \sum _ { x \in \\ { 0, 1 \\ } ^ n, y \in \\ { 0, 1 \\ } ^ m } \alpha (x, y) \ket { x } \ket { y \oplus f (x) } .</span><span class="sxs-lookup"><span data-stu-id="77c15-207"> = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
\end{align}
$$

## <a name="phase-oracles"></a><span data-ttu-id="77c15-208">Oracle phase</span><span class="sxs-lookup"><span data-stu-id="77c15-208">Phase oracles</span></span>
<span data-ttu-id="77c15-209">Vous pouvez également encoder $ f $ dans une $ O Oracle $ en appliquant une _phase_ basée sur l’entrée à $ o $ . Par exemple, nous pouvons définir $ O de $ telle sorte que$$</span><span class="sxs-lookup"><span data-stu-id="77c15-209">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$. For instance, we might define $O$ such that $$</span></span>
\begin{align}
    <span data-ttu-id="77c15-210">O \ket { x } = (-1) ^ { f (x) } \ket { x } .</span><span class="sxs-lookup"><span data-stu-id="77c15-210">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
\end{align}
$$
<span data-ttu-id="77c15-211">Si une phase Oracle agit sur un registre initialement dans un état de base de calcul $ \ket { x } $ , cette phase est une phase globale qui n’est donc pas observable.</span><span class="sxs-lookup"><span data-stu-id="77c15-211">If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="77c15-212">Toutefois, Oracle peut être une ressource très puissante si elle est appliquée à une superposition ou en tant qu’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="77c15-212">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="77c15-213">Par exemple, considérez une phase Oracle $ O_f $ pour une fonction qubit unique $ $ .</span><span class="sxs-lookup"><span data-stu-id="77c15-213">For example, consider a phase oracle $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="77c15-214">Cliquez$$</span><span class="sxs-lookup"><span data-stu-id="77c15-214">Then, $$</span></span>
\begin{align}
    <span data-ttu-id="77c15-215">O_f\ket{+}</span><span class="sxs-lookup"><span data-stu-id="77c15-215">O_f \ket{+}</span></span>
        &<span data-ttu-id="77c15-216">=O_f ( \ket { 0 }  +  \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="77c15-216"> = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="77c15-217">=((-1) ^ { f (0) } \ket { 0 } + (-1) ^ { f (1) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="77c15-217"> = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="77c15-218">=(-1) ^ { f (0) } ( \ket { 0 } + (-1) ^ { f (1)-f (0) } \ket { 1 } )/ \sqrt { 2 }\\\\</span><span class="sxs-lookup"><span data-stu-id="77c15-218"> = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\</span></span>
        &<span data-ttu-id="77c15-219">=(-1) ^ { f (0) } Z ^ { f (0)-f (1) } \ket { + } .</span><span class="sxs-lookup"><span data-stu-id="77c15-219"> = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
\end{align}
$$

<span data-ttu-id="77c15-220">Plus généralement, les deux vues d’Oracle peuvent être élargies pour représenter des fonctions classiques qui retournent des nombres réels au lieu d’un seul bit.</span><span class="sxs-lookup"><span data-stu-id="77c15-220">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="77c15-221">Le choix de la meilleure façon d’implémenter Oracle dépend fortement de la façon dont ce Oracle sera utilisé dans un algorithme donné.</span><span class="sxs-lookup"><span data-stu-id="77c15-221">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="77c15-222">Par exemple, l' [algorithme Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) s’appuie sur Oracle implémenté de la même façon, tandis que l' [algorithme de Grover s'](https://en.wikipedia.org/wiki/Grover's_algorithm) appuie sur Oracle implémenté de la seconde façon.</span><span class="sxs-lookup"><span data-stu-id="77c15-222">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="77c15-223">Pour plus d’informations, nous vous suggérons la discussion dans [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="77c15-223">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
