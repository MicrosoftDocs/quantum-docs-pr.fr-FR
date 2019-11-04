---
title: Spécification de schéma Broombridge
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: a950e04d44e5de8091b034214258d2c2fa663f58
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73185356"
---
# <a name="broombridge-specification-v01"></a><span data-ttu-id="e4a4e-102">Spécification Broombridge v 0.1</span><span class="sxs-lookup"><span data-stu-id="e4a4e-102">Broombridge Specification v0.1</span></span> #

<span data-ttu-id="e4a4e-103">Les mots clés « doit », « ne doit pas », « obligatoire », « doit », « ne doit pas « », « ne doit pas », « recommandé », « peut » et « facultatif » dans ce document doivent être interprétés comme décrit dans le document [RFC 2119](https://tools.ietf.org/html/rfc2119).</span><span class="sxs-lookup"><span data-stu-id="e4a4e-103">The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](https://tools.ietf.org/html/rfc2119).</span></span>

<span data-ttu-id="e4a4e-104">Tout encadré avec les en-têtes « NOTE », « INFORMATION » ou « avertissement » est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-104">Any sidebar with the headings "NOTE," "INFORMATION," or "WARNING" is informative.</span></span>

## <a name="introduction"></a><span data-ttu-id="e4a4e-105">Présentation</span><span class="sxs-lookup"><span data-stu-id="e4a4e-105">Introduction</span></span> ##

<span data-ttu-id="e4a4e-106">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-106">This section is informative.</span></span>

<span data-ttu-id="e4a4e-107">Les documents Broombridge sont destinés à communiquer des instances de problèmes de simulation dans la chimie Quantum à traiter à l’aide de la simulation quantique et de la programmation chaînes.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-107">Broombridge documents are intended to communicate instances of simulation problems in quantum chemistry for processing using quantum simulation and programming toolchains.</span></span>

## <a name="serialization"></a><span data-ttu-id="e4a4e-108">Sérialisation</span><span class="sxs-lookup"><span data-stu-id="e4a4e-108">Serialization</span></span> ##

<span data-ttu-id="e4a4e-109">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-109">This section is normative.</span></span>

<span data-ttu-id="e4a4e-110">Un document Broombridge doit être sérialisé en tant que [document YAML 1,2](http://yaml.org/spec/) représentant un objet JSON, comme décrit dans la section [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-110">A Broombridge document MUST be serialized as a [YAML 1.2 document](http://yaml.org/spec/) representing a JSON object as described in [RFC 4627](https://tools.ietf.org/html/rfc4627) section 2.2.</span></span>
<span data-ttu-id="e4a4e-111">L’objet sérialisé en YAML doit avoir une propriété `"$schema"` dont la valeur est `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`et doit être valide conformément aux spécifications Draft-06 du schéma JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span><span class="sxs-lookup"><span data-stu-id="e4a4e-111">The object serialized to YAML MUST have a property `"$schema"` whose value is `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`, and MUST be valid according to the JSON Schema draft-06 specifications [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].</span></span>

<span data-ttu-id="e4a4e-112">Pour le reste de cette spécification, « l’objet Broombridge » fait référence à l’objet JSON désérialisé à partir d’un document Broombridge YAML.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-112">For the remainder of this specification, "the Broombridge object" will refer to the JSON object deserialized from a Broombridge YAML document.</span></span>

<span data-ttu-id="e4a4e-113">Sauf mention contraire explicite, les objets ne doivent pas avoir de propriétés supplémentaires au-delà de celles spécifiées explicitement dans ce document.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-113">Unless otherwise explicitly noted, objects MUST NOT have additional properties beyond those specified explicitly in this document.</span></span>

## <a name="additional-definitions"></a><span data-ttu-id="e4a4e-114">Définitions complémentaires</span><span class="sxs-lookup"><span data-stu-id="e4a4e-114">Additional Definitions</span></span> ##

<span data-ttu-id="e4a4e-115">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-115">This section is normative.</span></span>

### <a name="quantity-objects"></a><span data-ttu-id="e4a4e-116">Objets Quantity</span><span class="sxs-lookup"><span data-stu-id="e4a4e-116">Quantity Objects</span></span> ###

<span data-ttu-id="e4a4e-117">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-117">This section is normative.</span></span>

<span data-ttu-id="e4a4e-118">Un _objet Quantity_ est un objet JSON et doit avoir une propriété `units` dont la valeur est l’une des valeurs autorisées figurant dans le tableau 1.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-118">A _quantity object_ is a JSON object, and MUST have a property `units` whose value is one of the allowed values listed in Table 1.</span></span>

<span data-ttu-id="e4a4e-119">Un objet Quantity est un _objet Quantity simple_ s’il a une propriété unique `value` en plus de sa propriété `units`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-119">A quantity object is a _simple quantity object_ if it has a single property `value` in addition to its `units` property.</span></span>
<span data-ttu-id="e4a4e-120">La valeur de la propriété `value` doit être un nombre.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-120">The value of the `value` property MUST be a number.</span></span>

<span data-ttu-id="e4a4e-121">Un objet Quantity est un _objet Quantity délimité_ s’il possède les propriétés `lower` et `upper` en plus de sa propriété `units`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-121">A quantity object is a _bounded quantity object_ if it has the properties `lower` and `upper` in addition to its `units` property.</span></span>
<span data-ttu-id="e4a4e-122">Les valeurs des propriétés `lower` et `upper` doivent être des nombres.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-122">The values of the `lower` and `upper` properties MUST be numbers.</span></span>
<span data-ttu-id="e4a4e-123">Un objet de quantité limitée peut avoir une propriété `value` dont la valeur est un nombre.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-123">A bounded quantity object MAY have a property `value` whose value is a number.</span></span>

<span data-ttu-id="e4a4e-124">Un objet Quantity est un _objet de grandeur de tableau fragmenté_ s’il a la propriété `format` et une propriété `values` en plus de sa propriété `units`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-124">A quantity object is a _sparse array quantity object_ if it has the property `format` and a property `values` in addition to its `units` property.</span></span>
<span data-ttu-id="e4a4e-125">La valeur de `format` doit être la chaîne `sparse`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-125">The value of `format` MUST be the string `sparse`.</span></span>
<span data-ttu-id="e4a4e-126">La valeur de la propriété `values` doit être un tableau.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-126">The value of the `values` property MUST be an array.</span></span>
<span data-ttu-id="e4a4e-127">Chaque élément de `values` doit être un tableau représentant les index et la valeur de la grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-127">Each element of `values` MUST be an array representing the indices and value of the sparse array quantity.</span></span>

<span data-ttu-id="e4a4e-128">Les index de chaque élément d’un objet de quantité éparse de tableau doivent être uniques dans l’ensemble de l’objet grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-128">The indices for each element of a sparse array quantity object MUST be unique across the entire sparse array quantity object.</span></span>
<span data-ttu-id="e4a4e-129">Si un index est présent avec une valeur de `0`, un analyseur doit traiter l’objet de grandeur du tableau fragmenté de la même manière qu’un objet de grandeur de tableau fragmenté dans lequel cet index n’est pas présent.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-129">If an index is present with a value of `0`, a parser MUST treat the sparse array quantity object identically to a sparse array quantity object in which that index is not present at all.</span></span>


<span data-ttu-id="e4a4e-130">Un objet Quantity doit avoir la valeur</span><span class="sxs-lookup"><span data-stu-id="e4a4e-130">A quantity object MUST either be</span></span>

- <span data-ttu-id="e4a4e-131">un objet Quantity simple,</span><span class="sxs-lookup"><span data-stu-id="e4a4e-131">a simple quantity object,</span></span>
- <span data-ttu-id="e4a4e-132">un objet de quantité limitée, ou</span><span class="sxs-lookup"><span data-stu-id="e4a4e-132">a bounded quantity object, or</span></span>
- <span data-ttu-id="e4a4e-133">objet de grandeur de tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-133">a sparse array quantity object.</span></span>


### <a name="examples"></a><span data-ttu-id="e4a4e-134">Exemples</span><span class="sxs-lookup"><span data-stu-id="e4a4e-134">Examples</span></span> ###

<span data-ttu-id="e4a4e-135">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-135">This section is informative.</span></span>

<span data-ttu-id="e4a4e-136">Une quantité simple représentant $1.9844146837\,\mathrm{Ha} $ :</span><span class="sxs-lookup"><span data-stu-id="e4a4e-136">A simple quantity representing $1.9844146837\,\mathrm{Ha}$:</span></span>

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

<span data-ttu-id="e4a4e-137">Une quantité limitée représentant une distribution uniforme sur l’intervalle $ [-7,-6]\,\mathrm{Ha} $ :</span><span class="sxs-lookup"><span data-stu-id="e4a4e-137">A bounded quantity representing a uniform distribution over the interval $[-7, -6]\,\mathrm{Ha}$:</span></span>

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

<span data-ttu-id="e4a4e-138">Ce qui suit est une grandeur de tableau fragmenté avec un élément `[1, 2]` égal à `hello` et un élément `[3, 4]` égal à `world`:</span><span class="sxs-lookup"><span data-stu-id="e4a4e-138">The following is a sparse array quantity with an element `[1, 2]` equal to `hello` and an element `[3, 4]` equal to `world`:</span></span>

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a><span data-ttu-id="e4a4e-139">Format, section</span><span class="sxs-lookup"><span data-stu-id="e4a4e-139">Format Section</span></span> ##

<span data-ttu-id="e4a4e-140">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-140">This section is normative.</span></span>

<span data-ttu-id="e4a4e-141">L’objet Broombridge doit avoir une propriété `format` dont la valeur est un objet JSON avec une propriété appelée `version`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-141">The Broombridge object MUST have a property `format` whose value is a JSON object with one property called `version`.</span></span>
<span data-ttu-id="e4a4e-142">La valeur de la propriété `version` doit être `"0.1"`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-142">The `version` property MUST have the value `"0.1"`.</span></span>

### <a name="example"></a><span data-ttu-id="e4a4e-143">Lire</span><span class="sxs-lookup"><span data-stu-id="e4a4e-143">Example</span></span> ###

<span data-ttu-id="e4a4e-144">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-144">This section is informative.</span></span>

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a><span data-ttu-id="e4a4e-145">Section ensembles intégraux</span><span class="sxs-lookup"><span data-stu-id="e4a4e-145">Integral Sets Section</span></span> ##

<span data-ttu-id="e4a4e-146">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-146">This section is normative.</span></span>

<span data-ttu-id="e4a4e-147">L’objet Broombridge doit avoir une propriété `integral_sets` dont la valeur est un tableau JSON.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-147">The Broombridge object MUST have a property `integral_sets` whose value is a JSON array.</span></span>
<span data-ttu-id="e4a4e-148">Chaque élément de la valeur de la propriété `integral_sets` doit être un objet JSON décrivant un ensemble d’intégrateurs, comme décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-148">Each item in the value of the `integral_sets` property MUST be a JSON object describing one set of integrals, as described in the remainder of this section.</span></span>
<span data-ttu-id="e4a4e-149">Dans le reste de cette section, le terme « objet ensemble entier » fait référence à un élément dans la valeur de la propriété `integral_sets` de l’objet Broombridge.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-149">In the remainder of this section, the term "integral set object" will refer to an item in the value of the `integral_sets` property of the Broombridge object.</span></span>

<span data-ttu-id="e4a4e-150">Chaque objet ensemble intégral doit avoir une propriété `metadata` dont la valeur est un objet JSON.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-150">Each integral set object MUST have a property `metadata` whose value is a JSON object.</span></span>
<span data-ttu-id="e4a4e-151">La valeur de `metadata` peut être l’objet JSON vide (autrement dit, `{}`) ou peut contenir des propriétés supplémentaires définies par l’implémenteur.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-151">The value of `metadata` MAY be the empty JSON object (that is, `{}`), or MAY contain additional properties defined by the implementor.</span></span>

### <a name="hamiltonian-section"></a><span data-ttu-id="e4a4e-152">Section Hamilton</span><span class="sxs-lookup"><span data-stu-id="e4a4e-152">Hamiltonian Section</span></span> ###

#### <a name="overview"></a><span data-ttu-id="e4a4e-153">Présentation</span><span class="sxs-lookup"><span data-stu-id="e4a4e-153">Overview</span></span> ####

<span data-ttu-id="e4a4e-154">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-154">This section is informative.</span></span>

<span data-ttu-id="e4a4e-155">La propriété `hamiltonian` de chaque objet ensemble intégral décrit le niveau de Hamilton pour un problème de chimie Quantum particulier en répertoriant ses termes à un et deux corps comme des tableaux éparss de nombres réels.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-155">The `hamiltonian` property of each integral set object describes the Hamiltonian for a particular quantum chemistry problem by listing out its one- and two-body terms as sparse arrays of real numbers.</span></span>
<span data-ttu-id="e4a4e-156">Les opérateurs de type Hamilton décrits par chaque objet ensemble intégral prennent la forme</span><span class="sxs-lookup"><span data-stu-id="e4a4e-156">The Hamiltonian operators described by each integral set object take the form</span></span>

<span data-ttu-id="e4a4e-157">$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} a ^\{\dagger\}\_{i , \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} h\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $</span><span class="sxs-lookup"><span data-stu-id="e4a4e-157">$$ H = \sum\_\{i,j\}\sum\_{\sigma\in\\{\uparrow,\downarrow\\}} h\_\{ij\} a^\{\dagger\}\_{i,\sigma} a\_{j,\sigma} + \frac{1}{2}\sum\_\{i,j,k,l\}\sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}} h\_{ijkl} a^\dagger\_{i,\sigma} a^\dagger\_{k,\rho} a\_{l,\rho} a\_{j,\sigma}, $$</span></span>

<span data-ttu-id="e4a4e-158">ici $h _ {ijkl} = (IJ | KL) $ dans la Convention Mulliken.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-158">here $h_{ijkl}= (ij|kl)$ in Mulliken convention.</span></span>

<span data-ttu-id="e4a4e-159">Par souci de clarté, le terme à un seul électrons est</span><span class="sxs-lookup"><span data-stu-id="e4a4e-159">For clarity, the one-electron term is</span></span>

<span data-ttu-id="e4a4e-160">$ $ H_ {IJ} = \int {\mathrm d} x \Psi ^ \*\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \Psi\_j (x), $ $</span><span class="sxs-lookup"><span data-stu-id="e4a4e-160">$$ h_{ij} = \int {\mathrm d}x \psi^\*\_i(x) \left(\frac{1}{2}\nabla^2 + \sum\_{A}\frac{Z\_A}{|x-x\_A|}  \right) \psi\_j(x), $$</span></span>

<span data-ttu-id="e4a4e-161">et le terme à deux électrons est</span><span class="sxs-lookup"><span data-stu-id="e4a4e-161">and the two-electron term is</span></span>

<span data-ttu-id="e4a4e-162">$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \Psi ^\{\*\}\_i (x\_1) \Psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\Psi\_k ^\{\*\}(x\_2) \Psi\_l (x\_2).</span><span class="sxs-lookup"><span data-stu-id="e4a4e-162">$$ h\_\{ijkl\} = \iint \{\mathrm d\}x^2 \psi^\{\*\}\_i(x\_1)\psi\_j(x\_1) \frac\{1\}\{\|x\_1 -x\_2\|\}\psi\_k^\{\*\}(x\_2) \psi\_l(x\_2).</span></span>
$$

<span data-ttu-id="e4a4e-163">Comme indiqué dans la description de la [propriété`basis_set`](#basis-set-object) de chaque élément de la propriété `integral_sets`, nous supposons plus explicitement que les fonctions de base utilisées sont des valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-163">As noted in our description of the [`basis_set` property](#basis-set-object) of each element of the `integral_sets` property, we further explicitly assume that the basis functions used are real-valued.</span></span>
<span data-ttu-id="e4a4e-164">Cela nous permet d’utiliser les Symmetries suivantes entre les termes pour compresser la représentation de la représentation du même.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-164">This allows us to use the following symmetries between the terms to compress the representation of the Hamiltonian.</span></span>

<span data-ttu-id="e4a4e-165">$ $ H_ {ijkl} = H_ {Ijlk} = H_ {jikl} = H_ {JiLK} = H_ {klij} = H_ {klji} = H_ {lkij} = H_ {lkji}.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-165">$$ h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkij}=h_{lkji}.</span></span>
$$


#### <a name="contents"></a><span data-ttu-id="e4a4e-166">Contenu</span><span class="sxs-lookup"><span data-stu-id="e4a4e-166">Contents</span></span> ####

<span data-ttu-id="e4a4e-167">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-167">This section is normative.</span></span>

<span data-ttu-id="e4a4e-168">Chaque jeu entier doit avoir une propriété `hamiltonian` dont la valeur est un objet JSON.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-168">Each integral set MUST have a property `hamiltonian` whose value is a JSON object.</span></span>
<span data-ttu-id="e4a4e-169">La valeur de la propriété `hamiltonian` est appelée objet Hamilton, et doit avoir les propriétés `one_electron_integrals` et `two_electron_integrals` comme décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-169">The value of the `hamiltonian` property is known as a Hamiltonian object, and MUST have the properties `one_electron_integrals` and `two_electron_integrals` as described in the remainder of this section.</span></span>
<span data-ttu-id="e4a4e-170">Un objet Hamilton peut également avoir une propriété `particle_hole_representation`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-170">A Hamiltonian object MAY also have a property `particle_hole_representation`.</span></span>
<span data-ttu-id="e4a4e-171">Si elle est présente, la valeur de `particle_hole_representation` doit respecter le format décrit dans le reste de cette section.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-171">If present, the value of `particle_hole_representation` MUST follow the format described in the remainder of this section.</span></span>

##### <a name="one-electron-integrals-object"></a><span data-ttu-id="e4a4e-172">Objet intégral à un seul électrons</span><span class="sxs-lookup"><span data-stu-id="e4a4e-172">One-Electron Integrals Object</span></span> #####

<span data-ttu-id="e4a4e-173">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-173">This section is normative.</span></span>

<span data-ttu-id="e4a4e-174">La propriété `one_electron_integrals` de l’objet Hamilton doit être une quantité de tableau épars dont les index sont deux entiers et dont les valeurs sont des nombres.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-174">The `one_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity whose indices are two integers and whose values are numbers.</span></span>
<span data-ttu-id="e4a4e-175">Chaque terme doit avoir des index `[i, j]` où `i >= j`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-175">Every term MUST have indices `[i, j]` where `i >= j`.</span></span>

> <span data-ttu-id="e4a4e-176">OBSERVE Cela reflète la symétrie qui $h _ {IJ} = H_ {ji} $ qui est la conséquence du fait que le Hermitian de la Hamilton est.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-176">[NOTE] This reflects the symmetry that $h_{ij} = h_{ji}$ which is a consequence of the fact that the Hamiltonian is Hermitian.</span></span>


###### <a name="example"></a><span data-ttu-id="e4a4e-177">Lire</span><span class="sxs-lookup"><span data-stu-id="e4a4e-177">Example</span></span> ######

<span data-ttu-id="e4a4e-178">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-178">This section is informative.</span></span>

<span data-ttu-id="e4a4e-179">La quantité de tableau épars suivante représente le point de \left-$ H = (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1 , \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-179">The following sparse array quantity represents the Hamiltonian $$ H = \left(-5.0  (a^\{\dagger\}\_{1,\uparrow} a\_{1,\uparrow}+a^\{\dagger\}\_{1,\downarrow} a\_{1,\downarrow})+ 0.17 (a^\{\dagger\}\_{2,\uparrow} a\_{1,\uparrow}+ a^\{\dagger\}\_{1,\uparrow} a\_{2,\uparrow}+a^\{\dagger\}\_{2,\downarrow} a\_{1,\downarrow}+ a^\{\dagger\}\_{1,\downarrow} a\_{2,\downarrow})\right)\\,\mathrm{Ha}.</span></span>
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
> <span data-ttu-id="e4a4e-180">Broombridge utilise l’indexation basée sur 1.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-180">Broombridge uses 1-based indexing.</span></span>


##### <a name="two-electron-integrals-object"></a><span data-ttu-id="e4a4e-181">Objet de type intégral à deux électrons</span><span class="sxs-lookup"><span data-stu-id="e4a4e-181">Two-Electron Integrals Object</span></span> #####

<span data-ttu-id="e4a4e-182">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-182">This section is normative.</span></span>

<span data-ttu-id="e4a4e-183">La propriété `two_electron_integrals` de l’objet Hamilton doit être une grandeur de tableau épars avec une propriété supplémentaire appelée `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-183">The `two_electron_integrals` property of the Hamiltonian object MUST be a sparse array quantity with one additional property called `index_convention`.</span></span>
<span data-ttu-id="e4a4e-184">Chaque élément de la valeur de `two_electron_integrals` doit avoir quatre index.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-184">Each element of the value of `two_electron_integrals` MUST have four indices.</span></span>

<span data-ttu-id="e4a4e-185">Chaque propriété `two_electron_integrals` doit avoir une propriété `index_convention`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-185">Each `two_electron_integrals` property MUST have a `index_convention` property.</span></span>
<span data-ttu-id="e4a4e-186">La valeur de la propriété `index_convention` doit être l’une des valeurs autorisées figurant dans le tableau 1.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-186">The value of the `index_convention` property MUST be one of the allowed values listed in Table 1.</span></span>
<span data-ttu-id="e4a4e-187">Si la valeur de `index_convention` est `mulliken`, alors pour chaque élément de la `two_electron_integrals` quantité de tableau épars, un analyseur chargeant un document Broombridge doit instancier un terme de Hamilton égal à l’opérateur à deux électrons $h _ {i, j, k, l} a ^ \dagger_i a ^ \dagger_j a_k a_l $ , où $i $, $j $, $k $ et $l $ doivent être des entiers dans la plage inclusive comprise entre 1 et le nombre d’électrons spécifiés par la propriété `n_electrons` de l’objet ensemble intégral, et où $h _ {i, j, k, l} $ correspond à l’élément `[i, j, k, l, h(i, j, k, l)]` de la grandeur du tableau fragmenté.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-187">If the value of `index_convention` is `mulliken`, then for each element of the `two_electron_integrals` sparse array quantity, a parser loading a Broombridge document MUST instantiate a Hamiltonian term equal to the two-electron operator $h_{i, j, k, l} a^\dagger_i a^\dagger_j a_k a_l$, where $i$, $j$, $k$, and $l$ MUST be integers in the inclusive range from 1 to the number of electrons specified by the `n_electrons` property of the integral set object, and where $h_{i, j, k, l}$ is the element `[i, j, k, l, h(i, j, k, l)]` of the sparse array quantity.</span></span>

###### <a name="symmetries"></a><span data-ttu-id="e4a4e-188">Symmetries</span><span class="sxs-lookup"><span data-stu-id="e4a4e-188">Symmetries</span></span> ######

<span data-ttu-id="e4a4e-189">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-189">This section is normative.</span></span>

<span data-ttu-id="e4a4e-190">Si la propriété `index_convention` d’un objet `two_electron_integrals` est égale à `mulliken`, si un élément avec des index `[i, j, k, l]` est présent, les index suivants ne doivent pas être présents, sauf s’ils sont égaux à `[i, j, k, l]`:</span><span class="sxs-lookup"><span data-stu-id="e4a4e-190">If the `index_convention` property of a `two_electron_integrals` object is equal to `mulliken`, then if an element with indices `[i, j, k, l]` is present, the following indices MUST NOT be present unless they are equal to `[i, j, k, l]`:</span></span>

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> <span data-ttu-id="e4a4e-191">Étant donné que la propriété `index_convention` est un objet de quantité éparse, aucun index ne peut être répété sur des éléments différents.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-191">Because the `index_convention` property is a sparse quantity object, no indices may be repeated on different elements.</span></span>
> <span data-ttu-id="e4a4e-192">En particulier, si un élément avec des index `[i, j, k, l]` est présent, aucun autre élément ne peut avoir ces index.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-192">In particular, if an element with indices `[i, j, k, l]` is present, no other element may have those indices.</span></span>


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a><span data-ttu-id="e4a4e-193">Lire</span><span class="sxs-lookup"><span data-stu-id="e4a4e-193">Example</span></span> #######

<span data-ttu-id="e4a4e-194">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-194">This section is informative.</span></span>

<span data-ttu-id="e4a4e-195">L’objet suivant spécifie la</span><span class="sxs-lookup"><span data-stu-id="e4a4e-195">The following object specifies the Hamiltonian</span></span>

<span data-ttu-id="e4a4e-196">$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6 , \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2, \rho} a\_{3 , \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2 , \rho} a\_{3, \sigma} $ $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2 , \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2 , \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-196">$$ H = \frac12 \sum\_{\sigma,\rho\in\\{\uparrow,\downarrow\\}}\Biggr( 1.6 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{1,\rho} a\_{1,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{6,\sigma} a^{\dagger}\_{1,\rho} a\_{2,\rho} a\_{3,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{3,\rho} a\_{2,\sigma}- 0.1 a^{\dagger}\_{1,\sigma} a^{\dagger}\_{6,\rho} a\_{2,\rho} a\_{3,\sigma} $$ $$- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{3,\sigma} a^{\dagger}\_{2,\rho} a\_{1,\rho} a\_{6,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{6,\rho} a\_{1,\sigma}- 0.1 a^{\dagger}\_{2,\sigma} a^{\dagger}\_{3,\rho} a\_{1,\rho} a\_{6,\sigma}\Biggr)\\,\textrm{Ha}.</span></span>
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

##### <a name="particlehole-representation-object"></a><span data-ttu-id="e4a4e-197">Particule : objet de représentation de trou</span><span class="sxs-lookup"><span data-stu-id="e4a4e-197">Particle–Hole Representation Object</span></span> #####

<span data-ttu-id="e4a4e-198">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-198">This section is normative.</span></span>

<span data-ttu-id="e4a4e-199">L’objet de représentation particule-Hole spécifie que les intégrales stockées sont définies par rapport à la représentation de trou de particule dans laquelle les opérateurs de création et de annihilation décrivent les écarts par rapport à l’état de référence utilisé, tel qu’un Hartree – État de Fock.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-199">The particle–hole representation object specifies that the integrals stored are defined with respect to particle hole representation wherein the creation and annihilation operators describe excitations away from the reference state used, such as a Hartree–Fock state.</span></span>
<span data-ttu-id="e4a4e-200">L’objet est facultatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-200">The object is OPTIONAL.</span></span>
<span data-ttu-id="e4a4e-201">Si l’objet n’est pas spécifié, le lieu de la particule doit être interprété comme n’étant pas donné dans une représentation de trou de particule.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-201">If the object is not specified then the Hamiltonian is to be interpreted as not given in particle-hole representation.</span></span>
<span data-ttu-id="e4a4e-202">Si elle est présente, la valeur de `particle_hole_representation` doit être un objet de quantité de tableau fragmenté dont les index sont quatre entiers et dont les valeurs sont un nombre et une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-202">If present, the value of `particle_hole_representation` MUST be a sparse array quantity object whose indices are four integers, and whose values are a number and a string.</span></span>
<span data-ttu-id="e4a4e-203">La partie de chaîne de la valeur de chaque élément doit contenir uniquement les caractères `'+'` et `'-'` qui spécifie si un facteur donné dans le terme est un opérateur de création ou de annihilation dans la représentation particule-Hole.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-203">The string portion of the value of each element MUST contain only the characters `'+'` and `'-'` which specifies whether a given factor in the term is a creation or annihilation operator in the particle–hole representation.</span></span>  <span data-ttu-id="e4a4e-204">Par exemple `"-+++"` répond à un trou créé sur le site $i $ et les particules créées sur les sites $j, k $ et $l $.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-204">For example `"-+++"` coresponds to a hole being created at site $i$ and particles being created at sites $j,k$ and $l$.</span></span>

> [!NOTE]
> <span data-ttu-id="e4a4e-205">Comme la valeur de l' `particle_hole_representation` est un objet de quantité de tableau fragmenté, les propriétés `unit` et `format` doivent être spécifiées.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-205">As the value of the `particle_hole_representation` is a sparse array quantity object, the `unit` and `format` properties must be specified.</span></span>
> <span data-ttu-id="e4a4e-206">Les unités acceptables sont répertoriées dans le tableau 1.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-206">Acceptable units include are listed in Table 1.</span></span>
> <span data-ttu-id="e4a4e-207">La propriété `format` est obligatoire et indique si les coefficients de Hamilton sont spécifiés comme un tableau dense ou épars.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-207">The `format` property is required, and indicates whether the Hamiltonian coefficients are specified as a dense or sparse array.</span></span>
> <span data-ttu-id="e4a4e-208">Dans la version actuelle, seuls les tableaux éparss sont pris en charge, avec l’interprétation que tous les éléments non spécifiés sont $0 $, mais les futures versions peuvent ajouter la prise en charge de valeurs supplémentaires de la propriété `format`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-208">In the current version, only sparse arrays are supported, with interpretation that all unspecified elements are $0$, but future versions may add support for additional values of the `format` property.</span></span>

### <a name="initial-state-section"></a><span data-ttu-id="e4a4e-209">Section état initial</span><span class="sxs-lookup"><span data-stu-id="e4a4e-209">Initial State Section</span></span> ###

<span data-ttu-id="e4a4e-210">L’objet initial_state_suggestion spécifie les États quantiques initiaux qui présentent un intérêt pour le pays de Hamilton spécifié.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-210">The initial_state_suggestion object specifies initial quantum states of interest to the specified Hamiltonian.</span></span> <span data-ttu-id="e4a4e-211">Cet objet doit être un tableau d’objets `state` JSON.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-211">This object must be an array of JSON `state` objects.</span></span>

#### <a name="state-object"></a><span data-ttu-id="e4a4e-212">Objet d’État</span><span class="sxs-lookup"><span data-stu-id="e4a4e-212">State object</span></span> ####

<span data-ttu-id="e4a4e-213">Chaque État représente une superposition d’orbites occupés.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-213">Each states represents a superposition of occupied orbitals.</span></span> <span data-ttu-id="e4a4e-214">Chaque objet d’État doit avoir une propriété `label` contenant une chaîne.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-214">Each state object MUST have a `label` property containing a string.</span></span> <span data-ttu-id="e4a4e-215">Chaque objet d’État doit avoir une propriété `superposition` contenant un tableau d’États de base et leurs amplitudes non normalisées.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-215">Each state object MUST have a `superposition` property containing an array of basis states and their unnormalized amplitudes.</span></span>

<span data-ttu-id="e4a4e-216">Par exemple, les États initiaux $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1 , \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ sont représenté par</span><span class="sxs-lookup"><span data-stu-id="e4a4e-216">For example, the initial states $$ \ket{G0}=\ket{G1}=\ket{G2}=(a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})\ket{0} $$ $$ \ket{E}=\frac{0.1 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{2,\uparrow}a^{\dagger}\_{2,\downarrow})+0.2 (a^{\dagger}\_{1,\uparrow}a^{\dagger}\_{3,\uparrow}a^{\dagger}\_{2,\downarrow})}{\sqrt{|0.1|^2+|0.2|^2}}\ket{0} $$ are represented by</span></span>
```yaml
initial_state_suggestions: # optional. If not provided, spin-orbitals will be filled to minimize one-body diagonal term energies.
    - state:
        label: "|G0>"
        superposition:
            - [1.0, "(1a)+","(2a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G1>"
        superposition:
            - [-1.0, "(2a)+","(1a)+","(2b)+","|vacuum>"]
    - state:
        label: "|G2>"
        superposition:
            - [1.0, "(3a)","(1a)+","(2a)+","(3a)+","(2b)+","|vacuum>"]
    - state:
        label: "|E>"
        superposition:
            - [0.1, "(1a)+","(2a)+","(2b)+","|vacuum>"]
            - [0.2, "(1a)+","(3a)+","(2b)+","|vacuum>"]
```

#### <a name="basis-set-object"></a><span data-ttu-id="e4a4e-217">Objet de jeu de base</span><span class="sxs-lookup"><span data-stu-id="e4a4e-217">Basis Set Object</span></span> ####

<span data-ttu-id="e4a4e-218">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-218">This section is normative.</span></span>

<span data-ttu-id="e4a4e-219">Chaque objet ensemble entier peut avoir une propriété `basis_set`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-219">Each integral set object MAY have a `basis_set` property.</span></span>
<span data-ttu-id="e4a4e-220">Si elle est présente, la valeur de la propriété `basis_set` doit être un objet avec deux propriétés, `type` et `name`.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-220">If present, the value of the `basis_set` property MUST be an object with two properties, `type` and `name`.</span></span>

<span data-ttu-id="e4a4e-221">Les fonctions de base identifiées par la valeur de la propriété `basis_set` doivent être des valeurs réelles.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-221">The basis functions identified by the value of the `basis_set` property MUST be real-valued.</span></span>

> [!NOTE]
> <span data-ttu-id="e4a4e-222">En supposant que toutes les fonctions de base sont des valeurs réelles, elles peuvent être assouplies dans les futures versions de cette spécification.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-222">The assumption that all basis functions are real-valued may be relaxed in future versions of this specification.</span></span>

## <a name="tables-and-lists"></a><span data-ttu-id="e4a4e-223">Tables et listes</span><span class="sxs-lookup"><span data-stu-id="e4a4e-223">Tables and Lists</span></span> ##

### <a name="table-1-allowed-physical-units"></a><span data-ttu-id="e4a4e-224">Tableau 1.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-224">Table 1.</span></span> <span data-ttu-id="e4a4e-225">Unités physiques autorisées</span><span class="sxs-lookup"><span data-stu-id="e4a4e-225">Allowed Physical Units</span></span> ###

<span data-ttu-id="e4a4e-226">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-226">This section is normative.</span></span>

<span data-ttu-id="e4a4e-227">Toute chaîne spécifiant une unité doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4a4e-227">Any string specifying a unit MUST be one of the following:</span></span>

- `hartree`
- `ev`

<span data-ttu-id="e4a4e-228">Les analyseurs et les producteurs doivent traiter les objets de quantité simple suivants comme équivalents :</span><span class="sxs-lookup"><span data-stu-id="e4a4e-228">Parsers and producers MUST treat the following simple quantity objects as equivalent:</span></span>

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a><span data-ttu-id="e4a4e-229">Tableau 2.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-229">Table 2.</span></span> <span data-ttu-id="e4a4e-230">Conventions d’index autorisées</span><span class="sxs-lookup"><span data-stu-id="e4a4e-230">Allowed Index Conventions</span></span> ###

<span data-ttu-id="e4a4e-231">Cette section est normative.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-231">This section is normative.</span></span>

<span data-ttu-id="e4a4e-232">Toute chaîne spécifiant une convention d’index doit être l’une des suivantes :</span><span class="sxs-lookup"><span data-stu-id="e4a4e-232">Any string specifying an index convention MUST be one of the following:</span></span>

- `mulliken`

<span data-ttu-id="e4a4e-233">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-233">This section is informative.</span></span>

<span data-ttu-id="e4a4e-234">Des conventions d’index supplémentaires peuvent être introduites dans les versions ultérieures de cette spécification.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-234">Additional index conventions may be introduced in future versions of this specification.</span></span>

#### <a name="interpretation-of-index-conventions"></a><span data-ttu-id="e4a4e-235">Interprétation des conventions d’index</span><span class="sxs-lookup"><span data-stu-id="e4a4e-235">Interpretation of Index Conventions</span></span> ####

<span data-ttu-id="e4a4e-236">Cette section est informatif.</span><span class="sxs-lookup"><span data-stu-id="e4a4e-236">This section is informative.</span></span>
