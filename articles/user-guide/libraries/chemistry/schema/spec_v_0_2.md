---
title: Spécification de schéma Broombridge (ver 0,2)
description: Décrit en détail les spécifications du schéma Broombridge Quantum chimie v 0,2 pour la bibliothèque Microsoft Quantum chimie.
author: guanghaolow
ms.author: gulow@microsoft.com
ms.date: 05/28/2019
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 3d935ec9de7e9b93bcdb00a4e13fc7bfce33b0aa
ms.sourcegitcommit: 6bf99d93590d6aa80490e88f2fd74dbbee8e0371
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/06/2020
ms.locfileid: "87869084"
---
# <a name="broombridge-specification-v02"></a><span data-ttu-id="b4358-103">Spécification Broombridge v 0,2</span><span class="sxs-lookup"><span data-stu-id="b4358-103">Broombridge Specification v0.2</span></span> #

<span data-ttu-id="b4358-104">Les mots clés « doit », « ne doit pas », « obligatoire », « doit », « ne doit pas « », « ne doit pas », « recommandé », « peut » et « facultatif » dans ce document doivent être interprétés comme décrit dans le document [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="b4358-104">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="b4358-105">Tout encadré avec les en-têtes « NOTE », « INFORMATION » ou « avertissement » est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-105">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="b4358-106">Introduction</span><span class="sxs-lookup"><span data-stu-id="b4358-106">Introduction</span></span> ##

<span data-ttu-id="b4358-107">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-107">This section is informative.</span></span>

<span data-ttu-id="b4358-108">Les documents Broombridge sont destinés à communiquer des instances de problèmes de simulation dans la chimie Quantum à traiter à l’aide de la simulation quantique et de la programmation chaînes.</span><span class="sxs-lookup"><span data-stu-id="b4358-108">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="b4358-109">Sérialisation</span><span class="sxs-lookup"><span data-stu-id="b4358-109">Serialization</span></span> ##

<span data-ttu-id="b4358-110">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-110">This section is normative.</span></span>

<span data-ttu-id="b4358-111">Un document Broombridge doit être sérialisé en tant que [document YAML 1,2](http://yaml.org/spec/) représentant un objet JSON, comme décrit dans la section [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2.</span><span class="sxs-lookup"><span data-stu-id="b4358-111">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="b4358-112">L’objet sérialisé en YAML doit avoir une propriété `"$schema"` dont la valeur est `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` et doit être valide conformément aux spécifications Draft-06 du schéma JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="b4358-112">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="b4358-113">Pour le reste de cette spécification, « l’objet Broombridge » fait référence à l’objet JSON désérialisé à partir d’un document Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="b4358-113">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="b4358-114">Sauf mention contraire explicite, les objets ne doivent pas avoir de propriétés supplémentaires au-delà de celles spécifiées explicitement dans ce document.</span><span class="sxs-lookup"><span data-stu-id="b4358-114">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="b4358-115">Définitions supplémentaires</span><span class="sxs-lookup"><span data-stu-id="b4358-115">Additional Definitions</span></span> ##

<span data-ttu-id="b4358-116">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-116">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="b4358-117">Objets Quantity</span><span class="sxs-lookup"><span data-stu-id="b4358-117">Quantity Objects</span></span> ###

<span data-ttu-id="b4358-118">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-118">This section is normative.</span></span>

<span data-ttu-id="b4358-119">Un _objet Quantity_ est un objet JSON et doit avoir une propriété `units` dont la valeur est l’une des valeurs autorisées figurant dans le tableau 1.</span><span class="sxs-lookup"><span data-stu-id="b4358-119">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="b4358-120">Un objet Quantity est un _objet Quantity simple_ s’il a une propriété unique `value` en plus de sa `units` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-120">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="b4358-121">La valeur de la `value` propriété doit être un nombre.</span><span class="sxs-lookup"><span data-stu-id="b4358-121">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="b4358-122">Un objet Quantity est un _objet Quantity limité_ s’il possède les propriétés `lower` et `upper` en plus de sa `units` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-122">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="b4358-123">Les valeurs des `lower` Propriétés et `upper` doivent être des nombres.</span><span class="sxs-lookup"><span data-stu-id="b4358-123">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="b4358-124">Un objet de quantité limitée peut avoir une propriété `value` dont la valeur est un nombre.</span><span class="sxs-lookup"><span data-stu-id="b4358-124">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="b4358-125">Un objet Quantity est un _objet de grandeur de tableau fragmenté_ s’il a la propriété `format` et une propriété `values` en plus de sa `units` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-125">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="b4358-126">La valeur de `format` doit être la chaîne `sparse` .</span><span class="sxs-lookup"><span data-stu-id="b4358-126">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="b4358-127">La valeur de la `values` propriété doit être un tableau.</span><span class="sxs-lookup"><span data-stu-id="b4358-127">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="b4358-128">Chaque élément de `values` doit être un tableau représentant les index et la valeur de la grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="b4358-128">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="b4358-129">Les index de chaque élément d’un objet de quantité éparse de tableau doivent être uniques dans l’ensemble de l’objet grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="b4358-129">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="b4358-130">Si un index est présent avec la valeur `0` , un analyseur doit traiter l’objet de grandeur du tableau fragmenté de la même manière qu’un objet de grandeur de tableau fragmenté dans lequel cet index n’est pas présent.</span><span class="sxs-lookup"><span data-stu-id="b4358-130">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="b4358-131">Un objet Quantity doit avoir la valeur</span><span class="sxs-lookup"><span data-stu-id="b4358-131">A quantity object MUST either be</span></span>

- <span data-ttu-id="b4358-132">un objet Quantity simple,</span><span class="sxs-lookup"><span data-stu-id="b4358-132">a simple quantity object,</span></span>
- <span data-ttu-id="b4358-133">un objet de quantité limitée, ou</span><span class="sxs-lookup"><span data-stu-id="b4358-133">a bounded quantity object, or</span></span>
- <span data-ttu-id="b4358-134">objet de grandeur de tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="b4358-134">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="b4358-135">Exemples</span><span class="sxs-lookup"><span data-stu-id="b4358-135">Examples</span></span> ###

<span data-ttu-id="b4358-136">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-136">This section is informative.</span></span>

<span data-ttu-id="b4358-137">Une quantité simple représentant $1.9844146837 \, \mathrm{ha} $ :</span><span class="sxs-lookup"><span data-stu-id="b4358-137">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="b4358-138">Une quantité limitée représentant une distribution uniforme sur l’intervalle $ [-7,-6] \, \mathrm{ha} $ :</span><span class="sxs-lookup"><span data-stu-id="b4358-138">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="b4358-139">Ce qui suit est une grandeur de tableau fragmenté avec un élément `[1, 2]` égal à `hello` et un élément `[3, 4]` égal à `world` :</span><span class="sxs-lookup"><span data-stu-id="b4358-139">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="b4358-140">Format, section</span><span class="sxs-lookup"><span data-stu-id="b4358-140">Format Section</span></span> ##

<span data-ttu-id="b4358-141">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-141">This section is normative.</span></span>

<span data-ttu-id="b4358-142">L’objet Broombridge doit avoir une propriété `format` dont la valeur est un objet JSON avec une propriété appelée `version` .</span><span class="sxs-lookup"><span data-stu-id="b4358-142">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="b4358-143">La `version` propriété doit avoir la valeur `"0.2"` .</span><span class="sxs-lookup"><span data-stu-id="b4358-143">The `version` property MUST have the value `"0.2"`.</span></span>

### <a name="example"></a><span data-ttu-id="b4358-144">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4358-144">Example</span></span> ###

<span data-ttu-id="b4358-145">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-145">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a><span data-ttu-id="b4358-146">Section Description du problème</span><span class="sxs-lookup"><span data-stu-id="b4358-146">Problem Description Section</span></span> ##

<span data-ttu-id="b4358-147">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-147">This section is normative.</span></span>

<span data-ttu-id="b4358-148">L’objet Broombridge doit avoir une propriété `problem_description` dont la valeur est un tableau JSON.</span><span class="sxs-lookup"><span data-stu-id="b4358-148">The Broombridge object MUST have a property `problem_description` whose value is a JSON array.</span></span>
<span data-ttu-id="b4358-149">Chaque élément de la valeur de la `problem_description` propriété doit être un objet JSON décrivant un ensemble d’intégrateurs, comme décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="b4358-149">Each item in the value of the `problem_description` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="b4358-150">Dans le reste de cette section, le terme « objet de description du problème » fait référence à un élément dans la valeur de la `problem_description` propriété de l’objet Broombridge.</span><span class="sxs-lookup"><span data-stu-id="b4358-150">In the remainder of this section, the term "problem description object" will refer to an item in the value of the `problem_description` property of the Broombridge object.</span></span>

<span data-ttu-id="b4358-151">Chaque objet de description du problème doit avoir une propriété `metadata` dont la valeur est un objet JSON.</span><span class="sxs-lookup"><span data-stu-id="b4358-151">Each problem description object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="b4358-152">La valeur de `metadata` peut être l’objet JSON vide (autrement dit, `{}` ), ou peut contenir des propriétés supplémentaires définies par l’implémenteur.</span><span class="sxs-lookup"><span data-stu-id="b4358-152">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="b4358-153">Section Hamilton</span><span class="sxs-lookup"><span data-stu-id="b4358-153">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="b4358-154">Vue d’ensemble</span><span class="sxs-lookup"><span data-stu-id="b4358-154">Overview</span></span> ####

<span data-ttu-id="b4358-155">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-155">This section is informative.</span></span>

<span data-ttu-id="b4358-156">La `hamiltonian` propriété de chaque objet de description du problème décrit le niveau de Hamilton pour un problème de chimie de Quantum particulier en répertoriant ses termes à un et deux corps comme des tableaux éparss de nombres réels.</span><span class="sxs-lookup"><span data-stu-id="b4358-156">The `hamiltonian` property of each problem description object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="b4358-157">Les opérateurs de type Hamilton décrits par chaque objet de description du problème prennent la forme</span><span class="sxs-lookup"><span data-stu-id="b4358-157">The Hamiltonian operators described by each problem description object take the form</span></span>

<span data-ttu-id="b4358-158">$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="b4358-158">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="b4358-159">ici $h _ {ijkl} = (IJ | KL) $ dans la Convention Mulliken.</span><span class="sxs-lookup"><span data-stu-id="b4358-159">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="b4358-160">Par souci de clarté, le terme à un seul électrons est</span><span class="sxs-lookup"><span data-stu-id="b4358-160">For clarity, the one-electron term is</span></span>

<span data-ttu-id="b4358-161">$ $ h_ {IJ} = \int {\mathrm d} x \Psi ^ \* \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ a} {| x-x \_ A |}  \right) \Psi \_ j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="b4358-161">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="b4358-162">et le terme à deux électrons est</span><span class="sxs-lookup"><span data-stu-id="b4358-162">and the two-electron term is</span></span>

<span data-ttu-id="b4358-163">$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \Psi ^ \{ \* \} \_ i (x \_ 1) \Psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \Psi \_ k ^ \{ \* \} (x \_ 2) \Psi \_ l (x \_ 2).</span><span class="sxs-lookup"><span data-stu-id="b4358-163">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="b4358-164">Comme indiqué dans la description de la [ `basis_set` propriété](#basis-set-object) de chaque élément de la `integral_sets` propriété, nous supposons plus explicitement que les fonctions de base utilisées sont des valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="b4358-164">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="b4358-165">Cela nous permet d’utiliser les Symmetries suivantes entre les termes pour compresser la représentation de la représentation du même.</span><span class="sxs-lookup"><span data-stu-id="b4358-165">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="b4358-166">$ $ h_ {ijkl} = h_ {Ijlk} = h_ {jikl} = h_ {JiLK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="b4358-166">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="b4358-167">Contenu</span><span class="sxs-lookup"><span data-stu-id="b4358-167">Contents</span></span> ####

<span data-ttu-id="b4358-168">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-168">This section is normative.</span></span>

<span data-ttu-id="b4358-169">Chaque objet de description du problème doit avoir une propriété `hamiltonian` dont la valeur est un objet JSON.</span><span class="sxs-lookup"><span data-stu-id="b4358-169">Each problem description object MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="b4358-170">La valeur de la `hamiltonian` propriété est appelée objet Hamilton, et doit avoir les propriétés `one_electron_integrals` et `two_electron_integrals` comme décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="b4358-170">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>

<span data-ttu-id="b4358-171">Chaque objet de description du problème doit avoir une propriété `coulomb_repulsion` dont la valeur est un objet de quantité simple.</span><span class="sxs-lookup"><span data-stu-id="b4358-171">Each problem description object MUST have a property `coulomb_repulsion` whose value is a simple quantity object.</span></span>
<span data-ttu-id="b4358-172">Chaque objet de description du problème doit avoir une propriété `energy_offet` dont la valeur est un objet de quantité simple.</span><span class="sxs-lookup"><span data-stu-id="b4358-172">Each problem description object MUST have a property `energy_offet` whose value is a simple quantity object.</span></span>
> <span data-ttu-id="b4358-173">OBSERVE Les valeurs de `coulomb_repulsion` et `energy_offet` ajoutées ensemble capturent la valeur d’identité de la « Hamilton ».</span><span class="sxs-lookup"><span data-stu-id="b4358-173">[NOTE] The values of `coulomb_repulsion` and `energy_offet` added together capture the identity term of the Hamiltonian.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="b4358-174">Objet intégral à un seul électrons</span><span class="sxs-lookup"><span data-stu-id="b4358-174">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="b4358-175">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-175">This section is normative.</span></span>

<span data-ttu-id="b4358-176">La `one_electron_integrals` propriété de l’objet Hamilton doit être une quantité de tableau épars dont les index sont deux entiers et dont les valeurs sont des nombres.</span><span class="sxs-lookup"><span data-stu-id="b4358-176">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="b4358-177">Chaque terme doit avoir des index `[i, j]` où `i >= j` .</span><span class="sxs-lookup"><span data-stu-id="b4358-177">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="b4358-178">OBSERVE Cela reflète la symétrie qui $h _ {IJ} = h_ {ji} $, qui est une conséquence du fait que le Hermitian de la Hamilton est le même.</span><span class="sxs-lookup"><span data-stu-id="b4358-178">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="b4358-179">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4358-179">Example</span></span> ######

<span data-ttu-id="b4358-180">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-180">This section is informative.</span></span>

<span data-ttu-id="b4358-181">La quantité de tableau fragmenté suivante représente le point de Hamilton $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a {2 \_ , \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b4358-181">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
$$

```yaml
one_electron_integrals:     # required
    units: hartree          # required
    format: sparse          # required
    values:                 # required
        # i j f(i,j)
        - [1, 1, -5.0]
        - [2, 1,  0.17]
```
> [!NOTE]
> <span data-ttu-id="b4358-182">Broombridge utilise l’indexation basée sur 1.</span><span class="sxs-lookup"><span data-stu-id="b4358-182">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="b4358-183">Objet de type intégral à deux électrons</span><span class="sxs-lookup"><span data-stu-id="b4358-183">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="b4358-184">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-184">This section is normative.</span></span>

<span data-ttu-id="b4358-185">La `two_electron_integrals` propriété de l’objet Hamilton doit être une grandeur de tableau épars avec une propriété supplémentaire appelée `index_convention` .</span><span class="sxs-lookup"><span data-stu-id="b4358-185">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="b4358-186">Chaque élément de la valeur de `two_electron_integrals` doit avoir quatre index.</span><span class="sxs-lookup"><span data-stu-id="b4358-186">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="b4358-187">Chaque `two_electron_integrals` propriété doit avoir une `index_convention` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-187">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="b4358-188">La valeur de la `index_convention` propriété doit être l’une des valeurs autorisées figurant dans le tableau 1.</span><span class="sxs-lookup"><span data-stu-id="b4358-188">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="b4358-189">Si la valeur de `index_convention` est `mulliken` , pour chaque élément de la `two_electron_integrals` grandeur du tableau partiellement alloué, un analyseur chargeant un document Broombridge doit instancier un terme de Hamilton égal à l’opérateur à deux électrons $h _ {i, j, k, l} a ^ \ dagger_i un ^ \ dagger_j a_k a_l $, où $i $, $j $, $k $ et $l $ doivent être des entiers de valeur au moins 1, et où $h _ {i, j, k, l} $ est l’élément `[i, j, k, l, h(i, j, k, l)]` de la grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="b4358-189">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers of value at least 1, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="b4358-190">Symmetries</span><span class="sxs-lookup"><span data-stu-id="b4358-190">Symmetries</span></span> ######

<span data-ttu-id="b4358-191">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-191">This section is normative.</span></span>

<span data-ttu-id="b4358-192">Si la `index_convention` propriété d’un `two_electron_integrals` objet est égale à `mulliken` , alors qu’un élément avec des index `[i, j, k, l]` est présent, les index suivants ne doivent pas être présents, sauf s’ils sont égaux à `[i, j, k, l]` :</span><span class="sxs-lookup"><span data-stu-id="b4358-192">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="b4358-193">Étant donné que la `index_convention` propriété est un objet de quantité éparse, aucun index ne peut être répété sur des éléments différents.</span><span class="sxs-lookup"><span data-stu-id="b4358-193">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="b4358-194">En particulier, si un élément avec des index `[i, j, k, l]` est présent, aucun autre élément ne peut avoir ces index.</span><span class="sxs-lookup"><span data-stu-id="b4358-194">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="b4358-195">Exemple</span><span class="sxs-lookup"><span data-stu-id="b4358-195">Example</span></span> #######

<span data-ttu-id="b4358-196">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-196">This section is informative.</span></span>

<span data-ttu-id="b4358-197">L’objet suivant spécifie la</span><span class="sxs-lookup"><span data-stu-id="b4358-197">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="b4358-198">$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} \_ 0,1 a ^ {\sigma}- \_ {1, \dagger} a ^ {\sigma} \_ {6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.</span><span class="sxs-lookup"><span data-stu-id="b4358-198">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
$$

```yaml
two_electron_integrals:
    index_convention: mulliken
    units: hartree
    format: sparse
    values:
        - [1, 1, 1, 1,  1.6]
        - [6, 1, 3, 2, -0.1]
```

### <a name="initial-state-section"></a><span data-ttu-id="b4358-199">Section état initial</span><span class="sxs-lookup"><span data-stu-id="b4358-199">Initial State Section</span></span> ###

<span data-ttu-id="b4358-200">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-200">This section is normative.</span></span>

<span data-ttu-id="b4358-201">L' `initial_state_suggestion` objet dont la valeur est un tableau JSON spécifie les États de Quantum initiaux qui présentent un intérêt pour le pays de Hamilton spécifié.</span><span class="sxs-lookup"><span data-stu-id="b4358-201">The `initial_state_suggestion` object whose value is a JSON array specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="b4358-202">Chaque élément de la valeur de la `initial_state_suggestion` propriété doit être un objet JSON décrivant un État Quantum, comme décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="b4358-202">Each item in the value of the `initial_state_suggestion` property MUST be a JSON object describing one quantum state, as described in the remainder of this section.</span></span>
<span data-ttu-id="b4358-203">Dans le reste de cette section, le terme « objet d’État » fait référence à un élément dans la valeur de la `initial_state_suggestion` propriété de l’objet Broombridge.</span><span class="sxs-lookup"><span data-stu-id="b4358-203">In the remainder of this section, the term "state object" will refer to an item in the value of the `initial_state_suggestion` property of the Broombridge object.</span></span>

#### <a name="state-object"></a><span data-ttu-id="b4358-204">Objet d’État</span><span class="sxs-lookup"><span data-stu-id="b4358-204">State object</span></span> ####

<span data-ttu-id="b4358-205">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-205">This section is normative.</span></span>

<span data-ttu-id="b4358-206">Chaque objet d’État doit avoir une `label` propriété contenant une chaîne.</span><span class="sxs-lookup"><span data-stu-id="b4358-206">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="b4358-207">Chaque objet d’État doit avoir une `method` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-207">Each state object MUST have a `method` property.</span></span> <span data-ttu-id="b4358-208">La valeur de la `method` propriété doit être l’une des valeurs autorisées énumérées dans le tableau 3.</span><span class="sxs-lookup"><span data-stu-id="b4358-208">The value of the `method` property MUST be one of the allowed values listed in Table 3.</span></span>
<span data-ttu-id="b4358-209">Chaque objet d’État peut avoir une propriété `energy` dont la valeur doit être un objet de quantité simple.</span><span class="sxs-lookup"><span data-stu-id="b4358-209">Each state object MAY have a property `energy` whose value MUST be a simple quantity object.</span></span>

<span data-ttu-id="b4358-210">Si la valeur de la `method` propriété est `sparse_multi_configurational` , l’objet d’État doit avoir une `superposition` propriété contenant un tableau d’États de base et leurs amplitudes non normalisées.</span><span class="sxs-lookup"><span data-stu-id="b4358-210">If the value of the `method` property is `sparse_multi_configurational`, the state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b4358-211">Par exemple, les États initiaux $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $ where $ \ket{E} $ a Energy $0,987 \textrm{ha} $, sont représentés par</span><span class="sxs-lookup"><span data-stu-id="b4358-211">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0}, $$ where $\ket{E}$ has energy $0.987 \textrm{Ha}$, are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "|G0>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
  - label: "|G1>"
    method: sparse_multi_configurational
    superposition:
      - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
  - label: "|G2>"
    method: sparse_multi_configurational
    superposition:
      - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
  - label: "|E>"
    energy: {units: hartree, value: 0.987}
    method: sparse_multi_configurational
    superposition:
      - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
      - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

<span data-ttu-id="b4358-212">Si la valeur de la `method` propriété est `unitary_coupled_cluster` , l’objet d’État doit avoir une `cluster_operator` propriété dont la valeur est un objet JSON.</span><span class="sxs-lookup"><span data-stu-id="b4358-212">If the value of the `method` property is `unitary_coupled_cluster`, the state object MUST have a `cluster_operator` property whose value is a JSON object.</span></span>
<span data-ttu-id="b4358-213">L’objet JSON doit avoir une `reference_state` propriété dont la valeur est un état de base.</span><span class="sxs-lookup"><span data-stu-id="b4358-213">The JSON object MUST have a `reference_state` property whose value is a basis state.</span></span>
<span data-ttu-id="b4358-214">L’objet JSON peut avoir une `one_body_amplitudes` propriété dont la valeur est un tableau d’opérateurs de cluster à un corps et leurs amplitudes.</span><span class="sxs-lookup"><span data-stu-id="b4358-214">The JSON object MAY have a `one_body_amplitudes` property whose value is an array of one-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="b4358-215">L’objet JSON peut avoir une `two_body_amplitudes` propriété dont la valeur est un tableau d’opérateurs de cluster à deux corps et leurs amplitudes.</span><span class="sxs-lookup"><span data-stu-id="b4358-215">The JSON object MAY have a `two_body_amplitudes` property whose value is an array of two-body cluster operators and their amplitudes.</span></span>
<span data-ttu-id="b4358-216">contenant un tableau d’États de base et leurs amplitudes non normalisées.</span><span class="sxs-lookup"><span data-stu-id="b4358-216">containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="b4358-217">Par exemple, l’État $ $ \ket{\text{Reference}} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $</span><span class="sxs-lookup"><span data-stu-id="b4358-217">For example, the state $$ \ket{\text{reference}}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0}, $$</span></span>

<span data-ttu-id="b4358-218">$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $</span><span class="sxs-lookup"><span data-stu-id="b4358-218">$$ \ket{\text{UCCSD}}=e^{T-T^\dagger}\ket{\text{reference}}, $$</span></span>

<span data-ttu-id="b4358-219">$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ est représenté par</span><span class="sxs-lookup"><span data-stu-id="b4358-219">$$ T = 0.1 a^{\dagger}\_{3,\uparrow}a\_{2,\downarrow} + 0.2 a^{\dagger}\_{2,\uparrow}a\_{2,\downarrow} - 0.3 a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\downarrow}a\_{3,\uparrow}a\_{2,\downarrow} $$ is represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
  - label: "UCCSD"
    method: unitary_coupled_cluster
    cluster_operator: # Initial state that cluster operator is applied to.
        reference_state: 
          [1.0, "(1a)+", "(2a)+", "(2b)+", '|vacuum>']
        one_body_amplitudes: # A one-body cluster term is t^{q}_{p} a^\dag_p a_q   
            - [0.1, "(3a)+", "(2b)"]
            - [-0.2, "(2a)+", "(2b)"]
        two_body_amplitudes: # A two-body unitary cluster term is t^{rs}_{pq} a^\dag_p a^\dag_q a_r a_s
            - [-0.3, "(1a)+", "(3b)+", "(3a)", "(2b)"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="b4358-220">Objet de jeu de base</span><span class="sxs-lookup"><span data-stu-id="b4358-220">Basis Set Object</span></span> ####

<span data-ttu-id="b4358-221">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-221">This section is normative.</span></span>

<span data-ttu-id="b4358-222">Chaque objet de description du problème peut avoir une `basis_set` propriété.</span><span class="sxs-lookup"><span data-stu-id="b4358-222">Each problem description object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="b4358-223">Si elle est présente, la valeur de la `basis_set` propriété doit être un objet avec deux propriétés, `type` et `name` .</span><span class="sxs-lookup"><span data-stu-id="b4358-223">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="b4358-224">Les fonctions de base identifiées par la valeur de la `basis_set` propriété doivent être des valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="b4358-224">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="b4358-225">En supposant que toutes les fonctions de base sont des valeurs réelles, elles peuvent être assouplies dans les futures versions de cette spécification.</span><span class="sxs-lookup"><span data-stu-id="b4358-225">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="b4358-226">Tables et listes</span><span class="sxs-lookup"><span data-stu-id="b4358-226">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="b4358-227">Tableau 1.</span><span class="sxs-lookup"><span data-stu-id="b4358-227">Table 1.</span></span> <span data-ttu-id="b4358-228">Unités physiques autorisées</span><span class="sxs-lookup"><span data-stu-id="b4358-228">Allowed Physical Units</span></span> ###

<span data-ttu-id="b4358-229">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-229">This section is normative.</span></span>

<span data-ttu-id="b4358-230">Toute chaîne spécifiant une unité doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4358-230">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="b4358-231">Les analyseurs et les producteurs doivent traiter les objets de quantité simple suivants comme équivalents :</span><span class="sxs-lookup"><span data-stu-id="b4358-231">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="b4358-232">Tableau 2.</span><span class="sxs-lookup"><span data-stu-id="b4358-232">Table 2.</span></span> <span data-ttu-id="b4358-233">Conventions d’index autorisées</span><span class="sxs-lookup"><span data-stu-id="b4358-233">Allowed Index Conventions</span></span> ###

<span data-ttu-id="b4358-234">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-234">This section is normative.</span></span>

<span data-ttu-id="b4358-235">Toute chaîne spécifiant une convention d’index doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4358-235">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="b4358-236">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-236">This section is informative.</span></span>

<span data-ttu-id="b4358-237">Des conventions d’index supplémentaires peuvent être introduites dans les versions ultérieures de cette spécification.</span><span class="sxs-lookup"><span data-stu-id="b4358-237">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="b4358-238">Interprétation des conventions d’index</span><span class="sxs-lookup"><span data-stu-id="b4358-238">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="b4358-239">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-239">This section is informative.</span></span>

### <a name="table-3-allowed-state-methods"></a><span data-ttu-id="b4358-240">Tableau 3.</span><span class="sxs-lookup"><span data-stu-id="b4358-240">Table 3.</span></span> <span data-ttu-id="b4358-241">Méthodes d’État autorisées</span><span class="sxs-lookup"><span data-stu-id="b4358-241">Allowed State methods</span></span> ###

<span data-ttu-id="b4358-242">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="b4358-242">This section is normative.</span></span>

<span data-ttu-id="b4358-243">Toute chaîne spécifiant une méthode d’État doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4358-243">Any string specifying a state method MUST be one of the following:</span></span>

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

<span data-ttu-id="b4358-244">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="b4358-244">This section is informative.</span></span>

<span data-ttu-id="b4358-245">Des méthodes d’État supplémentaires peuvent être introduites dans les versions ultérieures de cette spécification.</span><span class="sxs-lookup"><span data-stu-id="b4358-245">Additional state methods may be introduced in future versions of this specification.</span></span>
