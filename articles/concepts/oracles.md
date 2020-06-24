---
title: Oracles de quantum
description: Découvrez comment utiliser et définir des opérations d’Oracle quantique et de boîte noire utilisées comme entrée d’un autre algorithme.
author: cgranade
uid: microsoft.quantum.concepts.oracles
ms.author: Christopher.Granade@microsoft.com
ms.date: 07/11/2018
ms.topic: article
no-loc:
- $
- $
- $
- $
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
- "\begin{bmatrix}"
- "\end{bmatrix}"
- '\_'
ms.openlocfilehash: 747c08df110f1f10efe552628d15e3500509b690
ms.sourcegitcommit: 0181e7c9e98f9af30ea32d3cd8e7e5e30257a4dc
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85269556"
---
# <a name="quantum-oracles"></a><span data-ttu-id="8481c-103">Oracle Quantum</span><span class="sxs-lookup"><span data-stu-id="8481c-103">Quantum Oracles</span></span>

<span data-ttu-id="8481c-104">Une $O Oracle $ est une opération « boîte noire » utilisée comme entrée d’un autre algorithme.</span><span class="sxs-lookup"><span data-stu-id="8481c-104">An oracle $O$ is a "black box" operation that is used as input to another algorithm.</span></span>
<span data-ttu-id="8481c-105">Ces opérations sont souvent définies à l’aide d’une fonction classique $f : \\ {0, 1 \\ } ^ n \To \\ {0, 1 \\ } ^ m $ qui prend une $ entrée binaire $n bits et produit une $ sortie binaire $m bits.</span><span class="sxs-lookup"><span data-stu-id="8481c-105">Often, such operations are defined using a classical function $f : \\{0, 1\\}^n \to \\{0, 1\\}^m$ which takes an $n$-bit binary input and produces an $m$-bit binary output.</span></span>
<span data-ttu-id="8481c-106">Pour ce faire, considérez une entrée binaire particulière $x = (x_ {0 } , x_ {1 } , \dots, x_ {n-1 } ) $.</span><span class="sxs-lookup"><span data-stu-id="8481c-106">To do so, consider a particular binary input $x = (x_{0}, x_{1}, \dots, x_{n-1})$.</span></span>
<span data-ttu-id="8481c-107">Nous pouvons étiqueter les États qubit sous la forme $ \ket { \vec{x } } = \ket{x_ {0 } } \otimes \ket{x_ {1 } } \otimes \cdots \otimes \ket{x_ {n-1 } } $.</span><span class="sxs-lookup"><span data-stu-id="8481c-107">We can label qubit states as $\ket{\vec{x}} = \ket{x_{0}} \otimes \ket{x_{1}} \otimes \cdots \otimes \ket{x_{n-1}}$.</span></span>

<span data-ttu-id="8481c-108">Nous pouvons tenter d’abord de définir $O $ afin que $O \ket {x } = \ket{f (x)} $, mais cela pose quelques problèmes.</span><span class="sxs-lookup"><span data-stu-id="8481c-108">We may first attempt to define $O$ so that $O\ket{x} = \ket{f(x)}$, but this has a couple problems.</span></span>
<span data-ttu-id="8481c-109">Tout d’abord, $f $ pouvez avoir une taille différente d’entrée et de sortie ($n \ne m $ ), de sorte que l’application de $O $ modifie le nombre de qubits dans le registre.</span><span class="sxs-lookup"><span data-stu-id="8481c-109">First, $f$ may have a different size of input and output ($n \ne m$), such that applying $O$ would change the number of qubits in the register.</span></span>
<span data-ttu-id="8481c-110">Deuxièmement, même si $n = m $ , la fonction ne peut pas être réversible : si $f (x) = f (y) $ pour certains $x \ne y $ , $O \ket {x } = O \ket {y } $ mais $O ^ \dagger o \ket {x } \ne o ^ \dagger o \ket {y } $.</span><span class="sxs-lookup"><span data-stu-id="8481c-110">Second, even if $n = m$, the function may not be invertible: if $f(x) = f(y)$ for some $x \ne y$, then $O\ket{x} = O\ket{y}$ but $O^\dagger O\ket{x} \ne O^\dagger O\ket{y}$.</span></span>
<span data-ttu-id="8481c-111">Cela signifie que nous ne pouvons pas construire l’opération joint $O ^ \dagger $ , et Oracle doivent avoir un voisin défini pour eux.</span><span class="sxs-lookup"><span data-stu-id="8481c-111">This means we won't be able to construct the adjoint operation $O^\dagger$, and oracles have to have an adjoint defined for them.</span></span>

## <a name="defining-an-oracle-by-its-effect-on-computational-basis-states"></a><span data-ttu-id="8481c-112">Définition d’Oracle par son effet sur les États de base de calcul</span><span class="sxs-lookup"><span data-stu-id="8481c-112">Defining an oracle by its effect on computational basis states</span></span>
<span data-ttu-id="8481c-113">Nous pouvons traiter ces deux problèmes en introduisant un deuxième Registre de $m $ qubits pour conserver notre réponse.</span><span class="sxs-lookup"><span data-stu-id="8481c-113">We can deal with both of these problems by introducing a second register of $m$ qubits to hold our answer.</span></span>
<span data-ttu-id="8481c-114">Nous allons ensuite définir l’effet d’Oracle sur tous les États de base de calcul : pour tous les $x \Dans \\ {0, 1 \\ } ^ n $ et $y \Dans \\ {0, 1 \\ } ^ m $ ,</span><span class="sxs-lookup"><span data-stu-id="8481c-114">Then we will define the effect of the oracle on all computational basis states: for all $x \in \\{0, 1\\}^n$ and $y \in \\{0, 1\\}^m$,</span></span>

<span data-ttu-id="8481c-115">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-115">$$ \begin{align}</span></span>
    <span data-ttu-id="8481c-116">O (\ket{x } \otimes \ket{y } ) = \ket{x } \otimes \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="8481c-116">O(\ket{x} \otimes \ket{y}) = \ket{x} \otimes \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="8481c-117">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-117">\end{align}</span></span>
$$

<span data-ttu-id="8481c-118">Maintenant $O = O ^ \dagger $ par construction. nous avons donc résolu les deux problèmes précédents.</span><span class="sxs-lookup"><span data-stu-id="8481c-118">Now $O = O^\dagger$ by construction, thus we have resolved both of the earlier problems.</span></span>

> [!TIP]
> <span data-ttu-id="8481c-119">Pour voir que $O = O ^ {\dagger } $, Notez que $O ^ 2 = \boldone $ depuis $a \oplus b \oplus b = a $ pour tous les $a, b \Dans \{ 0,1 \} $.</span><span class="sxs-lookup"><span data-stu-id="8481c-119">To see that $O = O^{\dagger}$, note that $O^2 = \boldone$ since $a \oplus b \oplus b = a$ for all $a, b \in \{0, 1\}$.</span></span>
> <span data-ttu-id="8481c-120">Par conséquent, $O \ket{x } \ket{y \oplus f (x)} = \ket{x } \ket{y \oplus f (x) \oplus f (x)} = \ket{x } \ket{y } $.</span><span class="sxs-lookup"><span data-stu-id="8481c-120">As a result, $O \ket{x} \ket{y \oplus f(x)} = \ket{x} \ket{y \oplus f(x) \oplus f(x)} = \ket{x} \ket{y}$.</span></span>

<span data-ttu-id="8481c-121">Plus important encore, la définition d’une Oracle de cette façon pour chaque État de base de calcul $ \ket{x } \ket{y } $ définit également la manière dont $O $ agit pour tout autre État.</span><span class="sxs-lookup"><span data-stu-id="8481c-121">Importantly, defining an oracle this way for each computational basis state $\ket{x}\ket{y}$ also defines how $O$ acts for any other state.</span></span>
<span data-ttu-id="8481c-122">Cela vient immédiatement du fait que $O $ , comme toutes les opérations de Quantum, est linéaire dans l’État sur lequel il agit.</span><span class="sxs-lookup"><span data-stu-id="8481c-122">This follows immediately from the fact that $O$, like all quantum operations, is linear in the state that it acts on.</span></span>
<span data-ttu-id="8481c-123">Prenons l’opération Hadarmard, par exemple, qui est définie par $H \ket{0 } = \ket { +} $ et $H \ket{1 } = \ket { -} $.</span><span class="sxs-lookup"><span data-stu-id="8481c-123">Consider the Hadamard operation, for instance, which is defined by $H \ket{0} = \ket{+}$ and $H \ket{1} = \ket{-}$.</span></span>
<span data-ttu-id="8481c-124">Si nous souhaitons savoir comment $H $ agit sur $ \ket { +} $, nous pouvons utiliser ce $H $ linéaire,</span><span class="sxs-lookup"><span data-stu-id="8481c-124">If we wish to know how $H$ acts on $\ket{+}$, we can use that $H$ is linear,</span></span>

<span data-ttu-id="8481c-125">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-125">$$ \begin{align}</span></span>
<span data-ttu-id="8481c-126">H \ket { +} & = \frac{1 } {\sqrt{2 } } h (\ket{0 } + \ket{1 } ) = \frac{1 } {\sqrt{2 } } (H \ket {0 } + h \ket {1 } ) \\ \\ & = \frac{1 } {\sqrt{2 } } (\ket { +} + \ket { -}) = \frac12 (\ket{0 } + \ket{1 } + \ket{0 } -\ket{1 } ) = \ket{0 } .</span><span class="sxs-lookup"><span data-stu-id="8481c-126">H\ket{+} & = \frac{1}{\sqrt{2}} H(\ket{0} + \ket{1}) = \frac{1}{\sqrt{2}} (H\ket{0} + H\ket{1}) \\\\ & = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}) = \frac12 (\ket{0} + \ket{1} + \ket{0} - \ket{1}) = \ket{0}.</span></span>
<span data-ttu-id="8481c-127">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-127">\end{align}</span></span>
$$

<span data-ttu-id="8481c-128">Dans le cas de la définition de notre $O Oracle $ , nous pouvons utiliser de la même façon que n’importe quel état $ \ket { \Psi } $ sur $n + m $ qubits peut être écrit comme</span><span class="sxs-lookup"><span data-stu-id="8481c-128">In the case of defining our oracle $O$, we can similarly use that any state $\ket{\psi}$ on $n + m$ qubits can be written as</span></span>

<span data-ttu-id="8481c-129">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-129">$$ \begin{align}</span></span>
<span data-ttu-id="8481c-130">\ket { \psi } & = \ sum_ {x \Dans \\ {0, 1 \\ } ^ n, y \Dans \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y}</span><span class="sxs-lookup"><span data-stu-id="8481c-130">\ket{\psi} & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y}</span></span>
<span data-ttu-id="8481c-131">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-131">\end{align}</span></span>
$$

<span data-ttu-id="8481c-132">où $ \alpha : \\ {0, 1 \\ } ^ n \times \\ {0, 1 \\ } ^ m \To \mathbb{C } $ représente les coefficients de l’État $ \ket { \Psi } $.</span><span class="sxs-lookup"><span data-stu-id="8481c-132">where $\alpha : \\{0, 1\\}^n \times \\{0, 1\\}^m \to \mathbb{C}$ represents the coefficients of the state $\ket{\psi}$.</span></span> <span data-ttu-id="8481c-133">Donc</span><span class="sxs-lookup"><span data-stu-id="8481c-133">Thus,</span></span>

<span data-ttu-id="8481c-134">$ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-134">$$ \begin{align}</span></span>
<span data-ttu-id="8481c-135">O \ket { \Psi } & = O \ sum_ {x \Dans \\ {0, 1 \\ } ^ n, y \Dans \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y } \\ \\ & = \ sum_ {x \Dans \\ {0, 1 \\ } ^ n, y \Dans \\ {0, 1 \\ } ^ m } \alpha (x, y) O \ket{x } \ket{y } \\ \\ & = \ sum_ {x \Dans \\ {0, 1 \\ } ^ n, y \Dans \\ {0, 1 \\ } ^ m } \alpha (x, y) \ket{x } \ket{y \oplus f (x)}.</span><span class="sxs-lookup"><span data-stu-id="8481c-135">O \ket{\psi} & = O \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) O \ket{x} \ket{y} \\\\ & = \sum_{x \in \\{0, 1\\}^n, y \in \\{0, 1\\}^m} \alpha(x, y) \ket{x} \ket{y \oplus f(x)}.</span></span>
<span data-ttu-id="8481c-136">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-136">\end{align}</span></span>
$$

## <a name="phase-oracles"></a><span data-ttu-id="8481c-137">Oracle phase</span><span class="sxs-lookup"><span data-stu-id="8481c-137">Phase oracles</span></span>
<span data-ttu-id="8481c-138">Vous pouvez également Encoder $f $ dans un $O Oracle $ en appliquant une _phase_ basée sur l’entrée à $O $ .</span><span class="sxs-lookup"><span data-stu-id="8481c-138">Alternatively, we can encode $f$ into an oracle $O$ by applying a _phase_ based on the input to $O$.</span></span>
<span data-ttu-id="8481c-139">Par exemple, nous pouvons définir $O de $ manière à ce que $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-139">For instance, we might define $O$ such that $$ \begin{align}</span></span>
    <span data-ttu-id="8481c-140">O \ket{x } = (-1) ^ {f (x)} \ket{x } .</span><span class="sxs-lookup"><span data-stu-id="8481c-140">O \ket{x} = (-1)^{f(x)} \ket{x}.</span></span>
<span data-ttu-id="8481c-141">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-141">\end{align}</span></span>
<span data-ttu-id="8481c-142">$ $ Si une phase Oracle agit sur un registre initialement dans un état de base de calcul $ \ket{x } $, cette phase est une phase globale qui n’est donc pas observable.</span><span class="sxs-lookup"><span data-stu-id="8481c-142">$$ If a phase oracle acts on a register initially in a computational basis state $\ket{x}$, then this phase is a global phase and hence not observable.</span></span>
<span data-ttu-id="8481c-143">Toutefois, Oracle peut être une ressource très puissante si elle est appliquée à une superposition ou en tant qu’opération contrôlée.</span><span class="sxs-lookup"><span data-stu-id="8481c-143">But such an oracle can be a very powerful resource if applied to a superposition or as a controlled operation.</span></span>
<span data-ttu-id="8481c-144">Par exemple, considérez une phase Orcale $O _f $ pour une fonction à qubit unique $f $ .</span><span class="sxs-lookup"><span data-stu-id="8481c-144">For example, consider a phase orcale $O_f$ for a single-qubit function $f$.</span></span>
<span data-ttu-id="8481c-145">Ensuite, $ $ \begin{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-145">Then, $$ \begin{align}</span></span>
    <span data-ttu-id="8481c-146">O_f \ket { +} & = O_f (\ket{0 } + \ket{1 } )/\sqrt{2 } \\ \\ & = ((-1) ^ {f (0)} \ket{0 } + (-1) ^ {f (1)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} (\ket{0 } + (-1) ^ {f (1)-f (0)} \ket{1 } )/\sqrt{2 } \\ \\ & = (-1) ^ {f (0)} Z ^ {f (0)-f (1)} \ket { +}.</span><span class="sxs-lookup"><span data-stu-id="8481c-146">O_f \ket{+} & = O_f (\ket{0} + \ket{1}) / \sqrt{2} \\\\ & = ((-1)^{f(0)} \ket{0} + (-1)^{f(1)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} (\ket{0} + (-1)^{f(1) - f(0)} \ket{1}) / \sqrt{2} \\\\ & = (-1)^{f(0)} Z^{f(0) - f(1)} \ket{+}.</span></span>
<span data-ttu-id="8481c-147">\end{align}</span><span class="sxs-lookup"><span data-stu-id="8481c-147">\end{align}</span></span>
$$

<span data-ttu-id="8481c-148">Plus généralement, les deux vues d’Oracle peuvent être élargies pour représenter des fonctions classiques qui retournent des nombres réels au lieu d’un seul bit.</span><span class="sxs-lookup"><span data-stu-id="8481c-148">More generally, both views of oracles can be broadened to represent classical functions which return real numbers instead of only a single bit.</span></span>

<span data-ttu-id="8481c-149">Le choix de la meilleure façon d’implémenter Oracle dépend fortement de la façon dont ce Oracle sera utilisé dans un algorithme donné.</span><span class="sxs-lookup"><span data-stu-id="8481c-149">Choosing the best way to implement an oracle depends heavily on how this oracle will be used within a given algorithm.</span></span>
<span data-ttu-id="8481c-150">Par exemple, l' [algorithme Deutsch-Jozsa](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) s’appuie sur Oracle implémenté de la même façon, tandis que l' [algorithme de Grover s'](https://en.wikipedia.org/wiki/Grover's_algorithm) appuie sur Oracle implémenté de la seconde façon.</span><span class="sxs-lookup"><span data-stu-id="8481c-150">For example, [Deutsch-Jozsa algorithm](https://en.wikipedia.org/wiki/Deutsch%E2%80%93Jozsa_algorithm) relies on the oracle implemented in the first way, while [Grover's algorithm](https://en.wikipedia.org/wiki/Grover's_algorithm) relies on the oracle implemented in the second way.</span></span>


<span data-ttu-id="8481c-151">Pour plus d’informations, nous vous suggérons la discussion dans [Gilyén *et al*. 1711,00465](https://arxiv.org/abs/1711.00465).</span><span class="sxs-lookup"><span data-stu-id="8481c-151">For more details, we suggest the discussion in [Gilyén *et al*. 1711.00465](https://arxiv.org/abs/1711.00465).</span></span>
