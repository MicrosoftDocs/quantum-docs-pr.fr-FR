---
<span data-ttu-id="4d6b5-101">titre : vecteurs et matrices dans quantum computing Description : Découvrez les principes de base de l’utilisation des vecteurs et des matrices.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-101">title: Vectors and matrices in quantum computing description: Learn the basics of how to work with vectors and matrices.</span></span>
<span data-ttu-id="4d6b5-102">Auteur : QuantumWriter UID : Microsoft. Quantum. concepts. vectors ms. Author : nawiebe@microsoft.com ms. Date : 12/11/2017 ms. topic : article No-Loc :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-102">author: QuantumWriter uid: microsoft.quantum.concepts.vectors ms.author: nawiebe@microsoft.com ms.date: 12/11/2017 ms.topic: article no-loc:</span></span>
- <span data-ttu-id="4d6b5-103">"Q#"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-103">"Q#"</span></span>
- <span data-ttu-id="4d6b5-104">"$$v"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-104">"$$v"</span></span>
- <span data-ttu-id="4d6b5-105">"$$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-105">"$$"</span></span>
- <span data-ttu-id="4d6b5-106">"$$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-106">"$$"</span></span>
- <span data-ttu-id="4d6b5-107">"$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-107">"$"</span></span>
- <span data-ttu-id="4d6b5-108">"$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-108">"$"</span></span>
- <span data-ttu-id="4d6b5-109">"$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-109">"$"</span></span>
- <span data-ttu-id="4d6b5-110">"$$"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-110">"$$"</span></span>
- <span data-ttu-id="4d6b5-111">"\cdots"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-111">"\cdots"</span></span>
- <span data-ttu-id="4d6b5-112">"bmatrix"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-112">"bmatrix"</span></span>
- <span data-ttu-id="4d6b5-113">"\ddots"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-113">"\ddots"</span></span>
- <span data-ttu-id="4d6b5-114">"\equiv"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-114">"\equiv"</span></span>
- <span data-ttu-id="4d6b5-115">"\sum"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-115">"\sum"</span></span>
- <span data-ttu-id="4d6b5-116">"\begin"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-116">"\begin"</span></span>
- <span data-ttu-id="4d6b5-117">"\end"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-117">"\end"</span></span>
- <span data-ttu-id="4d6b5-118">"\sqrt"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-118">"\sqrt"</span></span>
- <span data-ttu-id="4d6b5-119">"\otimes"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-119">"\otimes"</span></span>
- <span data-ttu-id="4d6b5-120">"{"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-120">"{"</span></span>
- <span data-ttu-id="4d6b5-121">"}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-121">"}"</span></span>
- <span data-ttu-id="4d6b5-122">"\text"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-122">"\text"</span></span>
- <span data-ttu-id="4d6b5-123">"\phi"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-123">"\phi"</span></span>
- <span data-ttu-id="4d6b5-124">"\kappa"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-124">"\kappa"</span></span>
- <span data-ttu-id="4d6b5-125">"\psi"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-125">"\psi"</span></span>
- <span data-ttu-id="4d6b5-126">"\alpha"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-126">"\alpha"</span></span>
- <span data-ttu-id="4d6b5-127">"\beta"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-127">"\beta"</span></span>
- <span data-ttu-id="4d6b5-128">"\gamma"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-128">"\gamma"</span></span>
- <span data-ttu-id="4d6b5-129">"\delta"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-129">"\delta"</span></span>
- <span data-ttu-id="4d6b5-130">"\omega"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-130">"\omega"</span></span>
- <span data-ttu-id="4d6b5-131">"\bra"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-131">"\bra"</span></span>
- <span data-ttu-id="4d6b5-132">"\ket"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-132">"\ket"</span></span>
- <span data-ttu-id="4d6b5-133">"\boldone"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-133">"\boldone"</span></span>
- <span data-ttu-id="4d6b5-134">"\\\\"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-134">"\\\\"</span></span>
- <span data-ttu-id="4d6b5-135">"\\"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-135">"\\"</span></span>
- <span data-ttu-id="4d6b5-136">"="</span><span class="sxs-lookup"><span data-stu-id="4d6b5-136">"="</span></span>
- <span data-ttu-id="4d6b5-137">"\frac"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-137">"\frac"</span></span>
- <span data-ttu-id="4d6b5-138">"\text"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-138">"\text"</span></span>
- <span data-ttu-id="4d6b5-139">"\mapsto"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-139">"\mapsto"</span></span>
- <span data-ttu-id="4d6b5-140">"\dagger"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-140">"\dagger"</span></span>
- <span data-ttu-id="4d6b5-141">"\to"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-141">"\to"</span></span>
- <span data-ttu-id="4d6b5-142">"\begin{cases}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-142">"\begin{cases}"</span></span>
- <span data-ttu-id="4d6b5-143">"\end{cases}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-143">"\end{cases}"</span></span>
- <span data-ttu-id="4d6b5-144">"\operatorname"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-144">"\operatorname"</span></span>
- <span data-ttu-id="4d6b5-145">"\braket"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-145">"\braket"</span></span>
- <span data-ttu-id="4d6b5-146">"\id"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-146">"\id"</span></span>
- <span data-ttu-id="4d6b5-147">"\expect"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-147">"\expect"</span></span>
- <span data-ttu-id="4d6b5-148">"\defeq"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-148">"\defeq"</span></span>
- <span data-ttu-id="4d6b5-149">"\variance"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-149">"\variance"</span></span>
- <span data-ttu-id="4d6b5-150">"\dd"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-150">"\dd"</span></span>
- <span data-ttu-id="4d6b5-151">"&"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-151">"&"</span></span>
- <span data-ttu-id="4d6b5-152">"\begin{align}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-152">"\begin{align}"</span></span>
- <span data-ttu-id="4d6b5-153">"\end{align}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-153">"\end{align}"</span></span>
- <span data-ttu-id="4d6b5-154">"\Lambda"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-154">"\Lambda"</span></span>
- <span data-ttu-id="4d6b5-155">"\lambda"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-155">"\lambda"</span></span>
- <span data-ttu-id="4d6b5-156">"\Omega"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-156">"\Omega"</span></span>
- <span data-ttu-id="4d6b5-157">"\mathrm"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-157">"\mathrm"</span></span>
- <span data-ttu-id="4d6b5-158">"\left"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-158">"\left"</span></span>
- <span data-ttu-id="4d6b5-159">"\right"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-159">"\right"</span></span>
- <span data-ttu-id="4d6b5-160">"\qquad"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-160">"\qquad"</span></span>
- <span data-ttu-id="4d6b5-161">"\times"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-161">"\times"</span></span>
- <span data-ttu-id="4d6b5-162">"\big"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-162">"\big"</span></span>
- <span data-ttu-id="4d6b5-163">"\langle"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-163">"\langle"</span></span>
- <span data-ttu-id="4d6b5-164">"\rangle"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-164">"\rangle"</span></span>
- <span data-ttu-id="4d6b5-165">"\bigg"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-165">"\bigg"</span></span>
- <span data-ttu-id="4d6b5-166">"\Big"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-166">"\Big"</span></span>
- <span data-ttu-id="4d6b5-167">"|"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-167">"|"</span></span>
- <span data-ttu-id="4d6b5-168">"\mathbb"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-168">"\mathbb"</span></span>
- <span data-ttu-id="4d6b5-169">"\vec"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-169">"\vec"</span></span>
- <span data-ttu-id="4d6b5-170">"\in"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-170">"\in"</span></span>
- <span data-ttu-id="4d6b5-171">"\texttt"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-171">"\texttt"</span></span>
- <span data-ttu-id="4d6b5-172">"\ne"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-172">"\ne"</span></span>
- <span data-ttu-id="4d6b5-173">"<"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-173">"<"</span></span>
- <span data-ttu-id="4d6b5-174">">"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-174">">"</span></span>
- <span data-ttu-id="4d6b5-175">"\leq"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-175">"\leq"</span></span>
- <span data-ttu-id="4d6b5-176">"\geq"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-176">"\geq"</span></span>
- <span data-ttu-id="4d6b5-177">"~~"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-177">"~~"</span></span>
- <span data-ttu-id="4d6b5-178">"~"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-178">"~"</span></span>
- <span data-ttu-id="4d6b5-179">"\begin{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-179">"\begin{bmatrix}"</span></span>
- <span data-ttu-id="4d6b5-180">"\end{bmatrix}"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-180">"\end{bmatrix}"</span></span>
- <span data-ttu-id="4d6b5-181">"\_"</span><span class="sxs-lookup"><span data-stu-id="4d6b5-181">"\_"</span></span>

---

# <a name="vectors-and-matrices"></a><span data-ttu-id="4d6b5-182">Vecteurs et matrices</span><span class="sxs-lookup"><span data-stu-id="4d6b5-182">Vectors and Matrices</span></span>

<span data-ttu-id="4d6b5-183">Une certaine connaissance des vecteurs et des matrices est essentielle pour comprendre l’informatique quantique.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-183">Some familiarity with vectors and matrices is essential to understand quantum computing.</span></span> <span data-ttu-id="4d6b5-184">Nous fournissons une brève présentation ci-dessous et les lecteurs intéressés sont recommandés pour lire une référence standard sur l’algèbre linéaire telle que *Strang, G. (1993). Présentation de l’algèbre linéaire (vol. 3). Wellesley, MA : Wellesley-Cambridge Press* ou une référence en ligne telle que [algébrique linéaire](http://joshua.smcvt.edu/linearalgebra/).</span><span class="sxs-lookup"><span data-stu-id="4d6b5-184">We provide a brief introduction below and interested readers are recommended to read a standard reference on linear algebra such as *Strang, G. (1993). Introduction to linear algebra (Vol. 3). Wellesley, MA: Wellesley-Cambridge Press* or an online reference such as [Linear Algebra](http://joshua.smcvt.edu/linearalgebra/).</span></span>

<span data-ttu-id="4d6b5-185">Un vecteur de colonne (ou simplement [*Vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $ v $ de dimension (ou taille) $ n $ est une collection de $ n $ nombres complexes $ (V_1, V_2, \ldots, V_n) $ organisés en tant que colonne :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-185">A column vector (or simply [*vector*](https://en.wikipedia.org/wiki/Vector_(mathematics_and_physics))) $v$ of dimension (or size) $n$ is a collection of $n$ complex numbers $(v_1,v_2,\ldots,v_n)$ arranged as a column:</span></span>

<span data-ttu-id="4d6b5-186">$$v =\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-186">$$v =\begin{bmatrix}</span></span>
<span data-ttu-id="4d6b5-187">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-187">v_1\\\\</span></span>
<span data-ttu-id="4d6b5-188">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-188">v_2\\\\</span></span>
<span data-ttu-id="4d6b5-189">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-189">\vdots\\\\</span></span>
<span data-ttu-id="4d6b5-190">v_n\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="4d6b5-190">v_n \end{bmatrix}$$</span></span>

<span data-ttu-id="4d6b5-191">La norme d’un vecteur $ v $ est définie comme $ \sqrt { \sum \_ i | v \_ | ^ 2 } $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-191">The norm of a vector $v$ is defined as $\sqrt{\sum\_i |v\_i|^2}$.</span></span> <span data-ttu-id="4d6b5-192">Un vecteur est considéré comme une norme d’unité (ou il est également appelé vecteur d' [*unité*](https://en.wikipedia.org/wiki/Unit_vector)) si sa norme est $ 1 $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-192">A vector is said to be of unit norm (or alternatively it is called a [*unit vector*](https://en.wikipedia.org/wiki/Unit_vector)) if its norm is $1$.</span></span> <span data-ttu-id="4d6b5-193">Le [*voisin d’un vecteur*](https://en.wikipedia.org/wiki/Adjoint_matrix) $ v $ est désigné $ v ^ \dagger $ et est défini comme étant le vecteur de ligne suivant, où désigne $ \* $ le conjugué complexe.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-193">The [*adjoint of a vector*](https://en.wikipedia.org/wiki/Adjoint_matrix) $v$ is denoted $v^\dagger$ and is defined to be the following row vector where $\*$ denotes the complex conjugate,</span></span>

<span data-ttu-id="4d6b5-194">$$\begin{bmatrix}V_1 \\\\ \vdots \\\\ V_n \end{bmatrix} ^ \dagger = \begin{bmatrix} V_1 ^ \* & \cdots & V_n ^ \*\end{bmatrix}$$</span><span class="sxs-lookup"><span data-stu-id="4d6b5-194">$$\begin{bmatrix}v_1 \\\\ \vdots \\\\ v_n \end{bmatrix}^\dagger = \begin{bmatrix}v_1^\* & \cdots & v_n^\* \end{bmatrix}$$</span></span>

<span data-ttu-id="4d6b5-195">La méthode la plus courante pour multiplier deux vecteurs ensemble est le [*produit interne*](https://en.wikipedia.org/wiki/Inner_product_space), également connu sous le nom de produit scalaire.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-195">The most common way to multiply two vectors together is through the [*inner product*](https://en.wikipedia.org/wiki/Inner_product_space), also known as a dot product.</span></span>  <span data-ttu-id="4d6b5-196">Le produit interne donne la projection d’un vecteur sur un autre et est très utile pour décrire comment exprimer un vecteur comme somme d’autres vecteurs plus simples.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-196">The inner product gives the projection of one vector onto another and is invaluable in describing how to express one vector as a sum of other simpler vectors.</span></span>  <span data-ttu-id="4d6b5-197">Le produit interne entre $ u $ et $ v $ , désigné $ \left \langle u, v, \right \rangle $ est défini comme</span><span class="sxs-lookup"><span data-stu-id="4d6b5-197">The inner product between $u$ and $v$, denoted $\left\langle u, v\right\rangle$ is defined as</span></span>

$$
<span data-ttu-id="4d6b5-198">\langleu, v \rangle = u ^ \dagger v = u \_ 1 ^ { \* } V_1 + \cdots + u \_ n ^ { \* } v \_ n.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-198">\langle u, v\rangle = u^\dagger v=u\_1^{\*} v_1 + \cdots + u\_n^{\*} v\_n.</span></span>
$$

<span data-ttu-id="4d6b5-199">Cette notation permet également d’écrire la norme d’un vecteur $ v $ sous la forme $ \sqrt { \langle v, v \rangle } $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-199">This notation also allows the norm of a vector $v$ to be written as $\sqrt{\langle v, v\rangle}$.</span></span>

<span data-ttu-id="4d6b5-200">Nous pouvons multiplier un vecteur par un nombre $ c $ pour former un nouveau vecteur dont les entrées sont multipliées par $ c $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-200">We can multiply a vector with a number $c$ to form a new vector whose entries are multiplied by $c$.</span></span> <span data-ttu-id="4d6b5-201">Nous pouvons également ajouter deux vecteurs $ u $ et $ v $ pour former un nouveau vecteur dont les entrées sont la somme des entrées de $ u $ et $ v $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-201">We can also add two vectors $u$ and $v$ to form a new vector whose entries are the sum of the entries of $u$ and $v$.</span></span> <span data-ttu-id="4d6b5-202">Ces opérations sont décrites ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-202">These operations are depicted below:</span></span>

<span data-ttu-id="4d6b5-203">$$\mathrm{Si } ~ u=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-203">$$\mathrm{If}~u =\begin{bmatrix}</span></span>
<span data-ttu-id="4d6b5-204">u_1\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-204">u_1\\\\</span></span>
<span data-ttu-id="4d6b5-205">u_2\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-205">u_2\\\\</span></span>
<span data-ttu-id="4d6b5-206">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-206">\vdots\\\\</span></span>
<span data-ttu-id="4d6b5-207">u_n \end{bmatrix} ~ \mathrm { et}~</span><span class="sxs-lookup"><span data-stu-id="4d6b5-207">u_n \end{bmatrix}~\mathrm{and}~</span></span>
<span data-ttu-id="4d6b5-208">v=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-208">v =\begin{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-209">v_1\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-209">v_1\\\\</span></span>
    <span data-ttu-id="4d6b5-210">v_2\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-210">v_2\\\\</span></span>
    <span data-ttu-id="4d6b5-211">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-211">\vdots\\\\</span></span>
    <span data-ttu-id="4d6b5-212">V_n \end{bmatrix} , ~ \mathrm { puis}~</span><span class="sxs-lookup"><span data-stu-id="4d6b5-212">v_n \end{bmatrix},~\mathrm{then}~</span></span>
<span data-ttu-id="4d6b5-213">au + BV=\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-213">au+bv =\begin{bmatrix}</span></span>
<span data-ttu-id="4d6b5-214">au_1 + bv_1\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-214">au_1+bv_1\\\\</span></span>
<span data-ttu-id="4d6b5-215">au_2 + bv_2\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-215">au_2+bv_2\\\\</span></span>
<span data-ttu-id="4d6b5-216">\vdots\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-216">\vdots\\\\</span></span>
<span data-ttu-id="4d6b5-217">au_n + bv_n \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-217">au_n+bv_n \end{bmatrix}.</span></span>
$$

<span data-ttu-id="4d6b5-218">Une [*matrice*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) de taille $ m \times n $ est une collection de $ mn $ nombres complexes organisés en $ m $ lignes et $ n $ colonnes, comme indiqué ci-dessous :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-218">A [*matrix*](https://en.wikipedia.org/wiki/Matrix_(mathematics)) of size $m \times n$ is a collection of $mn$ complex numbers arranged in $m$ rows and $n$ columns as shown below:</span></span>

<span data-ttu-id="4d6b5-219">$$Lecteur=</span><span class="sxs-lookup"><span data-stu-id="4d6b5-219">$$M =</span></span> 
\begin{bmatrix}
<span data-ttu-id="4d6b5-220">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-220">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
<span data-ttu-id="4d6b5-221">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-221">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="4d6b5-222">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { mn}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-222">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}\\\\</span></span>
<span data-ttu-id="4d6b5-223">\end{bmatrix}.$$</span><span class="sxs-lookup"><span data-stu-id="4d6b5-223">\end{bmatrix}.$$</span></span>

<span data-ttu-id="4d6b5-224">Notez qu’un vecteur de dimension $ n $ est simplement une matrice de taille $ n \times 1 $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-224">Note that a vector of dimension $n$ is simply a matrix of size $n \times 1$.</span></span> <span data-ttu-id="4d6b5-225">Comme pour les vecteurs, nous pouvons multiplier une matrice avec un nombre $ c $ pour obtenir une nouvelle matrice où chaque entrée est multipliée par $ c $ , et nous pouvons ajouter deux matrices de même taille pour produire une nouvelle matrice dont les entrées sont la somme des entrées respectives des deux matrices.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-225">As with vectors, we can multiply a matrix with a number $c$ to obtain a new matrix where every entry is multiplied with $c$, and we can add two matrices of the same size to produce a new matrix whose entries are the sum of the respective entries of the two matrices.</span></span> 

## <a name="matrix-multiplication-and-tensor-products"></a><span data-ttu-id="4d6b5-226">Produits de multiplication de matrice et tenseur</span><span class="sxs-lookup"><span data-stu-id="4d6b5-226">Matrix Multiplication and Tensor Products</span></span>

<span data-ttu-id="4d6b5-227">Nous pouvons également multiplier deux matrices $ m $ de dimension $ m \times n $ et $ n $ de dimension $ n \times p $ pour obtenir une nouvelle matrice $ p $ de dimension $ m \times p $ comme suit :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-227">We can also multiply two matrices $M$ of dimension $m\times n$ and $N$ of dimension $n \times p$ to get a new matrix $P$ of dimension $m \times p$ as follows:</span></span>

\begin{align}
&\begin{bmatrix}
    <span data-ttu-id="4d6b5-228">M_ { 11 } ~~ m_ { 12 } ~~ \cdots ~~ m_ { 1N}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-228">M_{11} ~~ M_{12} ~~ \cdots ~~ M_{1n}\\\\</span></span>
    <span data-ttu-id="4d6b5-229">M_ { 21 } ~~ m_ { 22 } ~~ \cdots ~~ m_ { 2n}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-229">M_{21} ~~ M_{22} ~~ \cdots ~~ M_{2n}\\\\</span></span>
    \ddots\\\\
    <span data-ttu-id="4d6b5-230">M_ { M1 } ~~ m_ { m2 } ~~ \cdots ~~ m_ { mn}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-230">M_{m1} ~~ M_{m2} ~~ \cdots ~~ M_{mn}</span></span>
\end{bmatrix}
\begin{bmatrix}
<span data-ttu-id="4d6b5-231">N_ { 11 } ~~ n_ { 12 } ~~ \cdots ~~ n_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-231">N_{11} ~~ N_{12} ~~ \cdots ~~ N_{1p}\\\\</span></span>
<span data-ttu-id="4d6b5-232">N_ { 21 } ~~ n_ { 22 } ~~ \cdots ~~ n_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-232">N_{21} ~~ N_{22} ~~ \cdots ~~ N_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="4d6b5-233">N_ { N1 } ~~ n_ { N2 } ~~ \cdots ~~ n_ { NP}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-233">N_{n1} ~~ N_{n2} ~~ \cdots ~~ N_{np}</span></span>
\end{bmatrix}=\begin{bmatrix}
<span data-ttu-id="4d6b5-234">P_ { 11 } ~~ P_ { 12 } ~~ \cdots ~~ P_ { 1P}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-234">P_{11} ~~ P_{12} ~~ \cdots ~~ P_{1p}\\\\</span></span>
<span data-ttu-id="4d6b5-235">P_ { 21 } ~~ P_ { 22 } ~~ \cdots ~~ P_ { 2p}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-235">P_{21} ~~ P_{22} ~~ \cdots ~~ P_{2p}\\\\</span></span>
\ddots\\\\
<span data-ttu-id="4d6b5-236">{Pack d' } ~~ { } ~~ \cdots ~~ P_ { P_ M1 P_ m2}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-236">P_{m1} ~~ P_{m2} ~~ \cdots ~~ P_{mp}</span></span>
\end{bmatrix}
\end{align}

<span data-ttu-id="4d6b5-237">où les entrées de $ P $ sont $ P_ { ik } = \sum _j M_ { IJ } n_ { JK } $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-237">where the entries of $P$ are $P_{ik} = \sum_j M_{ij}N_{jk}$.</span></span> <span data-ttu-id="4d6b5-238">Par exemple, l’entrée $ P_ { 11 } $ est le produit interne de la première ligne de $ M $ avec la première colonne de $ N $ . Notez que dans la mesure où un vecteur est simplement un cas particulier d’une matrice, cette définition s’étend à la multiplication de vecteurs de matrice.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-238">For example, the entry $P_{11}$ is the inner product of the first row of $M$ with the first column of $N$. Note that since a vector is simply a special case of a matrix, this definition extends to matrix-vector multiplication.</span></span> 

<span data-ttu-id="4d6b5-239">Toutes les matrices que nous considérons sont des matrices carrées, où le nombre de lignes et de colonnes est égal, ou vecteurs, qui correspond uniquement à $ 1 $ colonne.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-239">All the matrices we consider will either be square matrices, where the number of rows and columns are equal, or vectors, which corresponds to only $1$ column.</span></span> <span data-ttu-id="4d6b5-240">Une matrice carrée spéciale est la [*matrice d’identité*](https://en.wikipedia.org/wiki/Identity_matrix), dénotée $ \boldone $ , dont tous les éléments diagonales sont égaux à $ 1 $ et les éléments restants égaux à $ 0 $ :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-240">One special square matrix is the [*identity matrix*](https://en.wikipedia.org/wiki/Identity_matrix), denoted $\boldone$, which has all its diagonal elements equal to $1$ and the remaining elements equal to $0$:</span></span>

$$\boldone=\begin{bmatrix}
<span data-ttu-id="4d6b5-241">1 ~~ 0 ~~ 0 \cdots ~~\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-241">1 ~~ 0 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="4d6b5-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-242">0 ~~ 1 ~~ \cdots ~~ 0\\\\</span></span>
<span data-ttu-id="4d6b5-243">~~ \ddots\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-243">~~ \ddots\\\\</span></span>
<span data-ttu-id="4d6b5-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix} .$$</span><span class="sxs-lookup"><span data-stu-id="4d6b5-244">0 ~~ 0 ~~ \cdots ~~ 1 \end{bmatrix}.$$</span></span>

<span data-ttu-id="4d6b5-245">Pour une matrice carrée $ a $ , nous disons qu’une matrice $ B $ est son [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) si $ AB = BA = \boldone $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-245">For a square matrix $A$, we say a matrix $B$ is its [*inverse*](https://en.wikipedia.org/wiki/Invertible_matrix) if $AB = BA = \boldone$.</span></span> <span data-ttu-id="4d6b5-246">L’inverse d’une matrice n’a pas besoin d’exister, mais lorsqu’elle existe, elle est unique et nous la dénotarons $ { en ^-1 } $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-246">The inverse of a matrix need not exist, but when it exists it is unique and we denote it $A^{-1}$.</span></span> 

<span data-ttu-id="4d6b5-247">Pour n’importe quelle matrice $ m $ , la permutation de voisins ou de conjugués de $ m $ est une matrice $ N $ telle que $ n_ { IJ } = m_ { ji } ^ \* $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-247">For any matrix $M$, the adjoint or conjugate transpose of $M$ is a matrix $N$ such that $N_{ij} = M_{ji}^\*$.</span></span> <span data-ttu-id="4d6b5-248">Le voisint de $ m $ est généralement le signe $ m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-248">The adjoint of $M$ is usually denoted $M^\dagger$.</span></span> <span data-ttu-id="4d6b5-249">Nous disons qu’une matrice $ U $ est [*unitaire*](https://en.wikipedia.org/wiki/Unitary_matrix) si $ uu ^ \dagger = u ^ \dagger u = \boldone $ ou équivalent, $ u ^ { -1 } = u ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-249">We say a matrix $U$ is [*unitary*](https://en.wikipedia.org/wiki/Unitary_matrix) if $UU^\dagger = U^\dagger U = \boldone$ or equivalently, $U^{-1} = U^\dagger$.</span></span>  <span data-ttu-id="4d6b5-250">La propriété la plus importante des matrices unitaires est peut-être qu’elle conserve la norme d’un vecteur.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-250">Perhaps the most important property of unitary matrices is that they preserve the norm of a vector.</span></span>  <span data-ttu-id="4d6b5-251">Cela se produit car</span><span class="sxs-lookup"><span data-stu-id="4d6b5-251">This happens because</span></span> 

<span data-ttu-id="4d6b5-252">$$\langlev, v \rangle = v ^ \dagger v v = ^ \dagger u ^ { -1 } U v v = ^ \dagger u ^ u v u v \dagger = \langle , u v \rangle .$$</span><span class="sxs-lookup"><span data-stu-id="4d6b5-252">$$\langle v,v \rangle=v^\dagger v = v^\dagger U^{-1} U v = v^\dagger U^\dagger U v = \langle U v, U v\rangle.$$</span></span>  

<span data-ttu-id="4d6b5-253">Une matrice $ m $ est dite [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) si $ m = m ^ \dagger $ .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-253">A matrix $M$ is said to be [*Hermitian*](https://en.wikipedia.org/wiki/Hermitian_matrix) if $M=M^\dagger$.</span></span>

<span data-ttu-id="4d6b5-254">Enfin, le [*produit tenseur*](https://en.wikipedia.org/wiki/Tensor_product) (ou le produit Kronecker) de deux matrices $ m $ de taille $ m \times n $ et $ n $ de taille $ p \times q $ est une matrice plus grande $ p = m \otimes n $ de taille $ MP \times NQ $ et est obtenue à partir de $ M $ et $ n $ comme suit :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-254">Finally, the [*tensor product*](https://en.wikipedia.org/wiki/Tensor_product) (or Kronecker product) of two matrices $M$ of size $m\times n$ and $N$ of size $p \times q$ is a larger matrix $P=M\otimes N$ of size $mp \times nq$, and is obtained from $M$ and $N$ as follows:</span></span>

\begin{align}
    <span data-ttu-id="4d6b5-255">M \otimes N&=</span><span class="sxs-lookup"><span data-stu-id="4d6b5-255">M \otimes N &=</span></span>
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-256">M_ { 11 } ~~ \cdots ~~ m_ { 1N }\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-256">M_{11} ~~ \cdots ~~ M_{1n} \\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="4d6b5-257">M_ { M1 } ~~ \cdots ~~ m_ { mn  }</span><span class="sxs-lookup"><span data-stu-id="4d6b5-257">M_{m1}  ~~ \cdots ~~ M_{mn}</span></span>
    \end{bmatrix}
    \otimes
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-258">N_ { 11 } ~~ \cdots ~~ n_ { 1t  }\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-258">N_{11}  ~~ \cdots ~~ N_{1q}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="4d6b5-259">N_ { P1 } ~~ \cdots ~~ n_ { PQ}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-259">N_{p1} ~~ \cdots ~~ N_{pq}</span></span>
    \end{bmatrix}\\\\
    &=
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-260">M_ { 11 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="4d6b5-260">M_{11} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="4d6b5-261">M_ { 1N } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ }  \end{bmatrix}\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-261">M_{1n} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}\\\\</span></span>
        \ddots\\\\
        <span data-ttu-id="4d6b5-262">M_ { M1 } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ } \end{bmatrix} ~~ \cdots  ~~</span><span class="sxs-lookup"><span data-stu-id="4d6b5-262">M_{m1} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}~~ \cdots ~~</span></span> 
        <span data-ttu-id="4d6b5-263">M_ { mn } \begin{bmatrix} n_ { 11 } ~~ \cdots ~~ n_ { 1t } \\\\ \ddots \\\\ n_ { P1 } ~~ \cdots ~~ n_ { PQ }  \end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-263">M_{mn} \begin{bmatrix} N_{11}  ~~ \cdots ~~ N_{1q}\\\\ \ddots\\\\ N_{p1} ~~ \cdots ~~ N_{pq} \end{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-264">\end{bmatrix}.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-264">\end{bmatrix}.</span></span>
\end{align}

<span data-ttu-id="4d6b5-265">Cette solution est mieux illustrée par des exemples :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-265">This is better demonstrated with some examples:</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-266">a \\\\ b \end{bmatrix} \otimes \begin{bmatrix} c \\\\ \\\\ d \end{bmatrix}=</span><span class="sxs-lookup"><span data-stu-id="4d6b5-266">a \\\\ b  \end{bmatrix} \otimes \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix} =</span></span>
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-267">\begin{bmatrix}c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-267">a \begin{bmatrix} c \\\\ d \\\\ e \end{bmatrix}</span></span>
        <span data-ttu-id="4d6b5-268">\\\\[1.5 em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-268">\\\\[1.5em] b \begin{bmatrix} c \\\\ d \\\\ e\end{bmatrix}</span></span>
    \end{bmatrix}
    <span data-ttu-id="4d6b5-269">=\begin{bmatrix}un c \\\\ a d \\\\ a e \\\\ b c \\\\ b \\\\ est\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-269">= \begin{bmatrix} a c \\\\ a d \\\\ a e \\\\ b c \\\\ b d \\\\ be\end{bmatrix}</span></span>
$$

<span data-ttu-id="4d6b5-270">and</span><span class="sxs-lookup"><span data-stu-id="4d6b5-270">and</span></span>

$$
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-271">a \ b \\\\ c \ d\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-271">a\ b \\\\ c\ d \end{bmatrix}</span></span>
    \otimes 
    \begin{bmatrix}
        <span data-ttu-id="4d6b5-272">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-272">e\ f\\\\g\ h \end{bmatrix}</span></span>
     =
    \begin{bmatrix}
    <span data-ttu-id="4d6b5-273">un\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-273">a\begin{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-274">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-274">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-275">p\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-275">b\begin{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-276">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-276">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-277">\\\\[1em] c\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-277">\\\\[1em] c\begin{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-278">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-278">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-279">e\begin{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-279">d\begin{bmatrix}</span></span>
    <span data-ttu-id="4d6b5-280">e \ f \\\\ g \ h\end{bmatrix}</span><span class="sxs-lookup"><span data-stu-id="4d6b5-280">e\ f\\\\ g\ h \end{bmatrix}</span></span>
    \end{bmatrix}
    =
    \begin{bmatrix}
    <span data-ttu-id="4d6b5-281">AE \ AF \ est \ BF\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-281">ae\ af\ be\ bf \\\\</span></span>
    <span data-ttu-id="4d6b5-282">AG \ Ah \ BG \ BH\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-282">ag\ ah\ bg\ bh \\\\</span></span>
    <span data-ttu-id="4d6b5-283">ce \ CF \ de \ DF\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-283">ce\ cf\ de\ df \\\\</span></span>
    <span data-ttu-id="4d6b5-284">CG \ ch \ DG \ DH \end{bmatrix} .</span><span class="sxs-lookup"><span data-stu-id="4d6b5-284">cg\ ch\ dg\ dh \end{bmatrix}.</span></span>
$$

<span data-ttu-id="4d6b5-285">La dernière convention de notation utile entourant les produits tenseur est que, pour n’importe quel vecteur $ v $ ou matrice $ m $ , $ v ^ { \otimes n } $ ou $ M ^ { \otimes n } $ est la main pour un $ $ produit tenseur répété à n plis.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-285">A final useful notational convention surrounding tensor products is that, for any vector $v$ or matrix $M$, $v^{\otimes n}$ or $M^{\otimes n}$ is short hand for an $n$-fold repeated tensor product.</span></span>  <span data-ttu-id="4d6b5-286">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="4d6b5-286">For example:</span></span>

\begin{align}
<span data-ttu-id="4d6b5-287">&\begin{bmatrix}1 \\\\ 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ 0 2 1 0 0 0 \end{bmatrix} ^ { \otimes } = \begin{bmatrix} \\\\ \\\\ \\\\ \end{bmatrix} , \qquad \begin{bmatrix} 1 \\\\ -1 \end{bmatrix} ^ { \otimes 2 } = \begin{bmatrix} 1 \\\\ -1 \\\\ -1 \\\\ 1 \end{bmatrix} ,\\\\</span><span class="sxs-lookup"><span data-stu-id="4d6b5-287">&\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 1} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ 0 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ 0 \\\\0 \\\\0 \end{bmatrix}, \qquad\begin{bmatrix} 1 \\\\ -1 \end{bmatrix}^{\otimes 2} = \begin{bmatrix} 1 \\\\ -1 \\\\-1 \\\\1 \end{bmatrix}, \\\\</span></span>
  <span data-ttu-id="4d6b5-288">&\begin{bmatrix}0 & 1 \\\\ 1 & 0 \end{bmatrix} ^ { \otimes 1 } = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} , \qquad \begin{bmatrix} 0 & 1 \\\\ 1 0 & \end{bmatrix} ^ { 2 \otimes } = \begin{bmatrix} & & & \\\\ & & & \\\\ & & & \\\\ & & & \end{bmatrix} 0 0 0 0 1 0 0 1 0 0 1 0 0 1 0 0 0.</span><span class="sxs-lookup"><span data-stu-id="4d6b5-288">&\begin{bmatrix}  0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 1}= \begin{bmatrix}  0& 1 \\\\ 1& 0    \end{bmatrix},    \qquad\begin{bmatrix}   0 & 1 \\\\ 1& 0   \end{bmatrix}^{\otimes 2}= \begin{bmatrix} 0 &0&0&1 \\\\ 0 &0&1&0 \\\\ 0 &1&0&0\\\\ 1 &0&0&0\end{bmatrix}.</span></span>
\end{align}
