---
title: Spécification de schéma Broombridge (ver 0,1)
description: Décrit en détail les spécifications du schéma Broombridge Quantum chimie v 0.1 pour la bibliothèque Microsoft Quantum chimie.
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/17/2018
ms.topic: article
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_1
ms.openlocfilehash: 618892b6cb01855d17522b06e47f72f68595ab38
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906421"
---
# <a name="broombridge-specification-v01"></a>Spécification Broombridge v 0.1 #

Les mots clés « doit », « ne doit pas », « obligatoire », « doit », « ne doit pas « », « ne doit pas », « recommandé », « peut » et « facultatif » dans ce document doivent être interprétés comme décrit dans le document [RFC 2119](https://tools.ietf.org/html/rfc2119).

Tout encadré avec les en-têtes « NOTE », « INFORMATION » ou « avertissement » est informatif.

## <a name="introduction"></a>Introduction ##

Cette section est informatif.

Les documents Broombridge sont destinés à communiquer des instances de problèmes de simulation dans la chimie Quantum à traiter à l’aide de la simulation quantique et de la programmation chaînes.

## <a name="serialization"></a>Sérialisation ##

Cette section est normative.

Un document Broombridge doit être sérialisé en tant que [document YAML 1,2](http://yaml.org/spec/) représentant un objet JSON, comme décrit dans la section [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2.
L’objet sérialisé en YAML doit avoir une propriété `"$schema"` dont la valeur est `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.1.schema.json"`et doit être valide conformément aux spécifications Draft-06 du schéma JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Pour le reste de cette spécification, « l’objet Broombridge » fait référence à l’objet JSON désérialisé à partir d’un document Broombridge YAML.

Sauf mention contraire explicite, les objets ne doivent pas avoir de propriétés supplémentaires au-delà de celles spécifiées explicitement dans ce document.

## <a name="additional-definitions"></a>Définitions supplémentaires ##

Cette section est normative.

### <a name="quantity-objects"></a>Objets Quantity ###

Cette section est normative.

Un _objet Quantity_ est un objet JSON et doit avoir une propriété `units` dont la valeur est l’une des valeurs autorisées figurant dans le tableau 1.

Un objet Quantity est un _objet Quantity simple_ s’il a une propriété unique `value` en plus de sa propriété `units`.
La valeur de la propriété `value` doit être un nombre.

Un objet Quantity est un _objet Quantity délimité_ s’il possède les propriétés `lower` et `upper` en plus de sa propriété `units`.
Les valeurs des propriétés `lower` et `upper` doivent être des nombres.
Un objet de quantité limitée peut avoir une propriété `value` dont la valeur est un nombre.

Un objet Quantity est un _objet de grandeur de tableau fragmenté_ s’il a la propriété `format` et une propriété `values` en plus de sa propriété `units`.
La valeur de `format` doit être la chaîne `sparse`.
La valeur de la propriété `values` doit être un tableau.
Chaque élément de `values` doit être un tableau représentant les index et la valeur de la grandeur du tableau fragmenté.

Les index de chaque élément d’un objet de quantité éparse de tableau doivent être uniques dans l’ensemble de l’objet grandeur du tableau fragmenté.
Si un index est présent avec une valeur de `0`, un analyseur doit traiter l’objet de grandeur du tableau fragmenté de la même manière qu’un objet de grandeur de tableau fragmenté dans lequel cet index n’est pas présent.


Un objet Quantity doit avoir la valeur

- un objet Quantity simple,
- un objet de quantité limitée, ou
- objet de grandeur de tableau fragmenté.


### <a name="examples"></a>Exemples ###

Cette section est informatif.

Une quantité simple représentant $1.9844146837\,\mathrm{Ha} $ :

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Une quantité limitée représentant une distribution uniforme sur l’intervalle $ [-7,-6]\,\mathrm{Ha} $ :

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Ce qui suit est une grandeur de tableau fragmenté avec un élément `[1, 2]` égal à `hello` et un élément `[3, 4]` égal à `world`:

```yaml
sparse_example:
    format: sparse
    units: hartree
    values:
    - [1, 2, "hello"]
    - [3, 4, "world"]
```

## <a name="format-section"></a>Format, section ##

Cette section est normative.

L’objet Broombridge doit avoir une propriété `format` dont la valeur est un objet JSON avec une propriété appelée `version`.
La valeur de la propriété `version` doit être `"0.1"`.

### <a name="example"></a>Exemple ###

Cette section est informatif.

```yaml
format:                        # required
    version: "0.1"             # must match exactly
```

## <a name="integral-sets-section"></a>Section ensembles intégraux ##

Cette section est normative.

L’objet Broombridge doit avoir une propriété `integral_sets` dont la valeur est un tableau JSON.
Chaque élément de la valeur de la propriété `integral_sets` doit être un objet JSON décrivant un ensemble d’intégrateurs, comme décrit dans le reste de cette section.
Dans le reste de cette section, le terme « objet ensemble entier » fait référence à un élément dans la valeur de la propriété `integral_sets` de l’objet Broombridge.

Chaque objet ensemble intégral doit avoir une propriété `metadata` dont la valeur est un objet JSON.
La valeur de `metadata` peut être l’objet JSON vide (autrement dit, `{}`) ou peut contenir des propriétés supplémentaires définies par l’implémenteur.

### <a name="hamiltonian-section"></a>Section Hamilton ###

#### <a name="overview"></a>Vue d’ensemble ####

Cette section est informatif.

La propriété `hamiltonian` de chaque objet ensemble intégral décrit le niveau de Hamilton pour un problème de chimie Quantum particulier en répertoriant ses termes à un et deux corps comme des tableaux éparss de nombres réels.
Les opérateurs de type Hamilton décrits par chaque objet ensemble intégral prennent la forme

$ $ H = \sum\_\{i, j\}\sum\_{\sigma\in\\{\uparrow, \downarrow\\}} H\_\{IJ\} a ^\{\dagger\}\_{i, \sigma} a\_{j, \sigma} + \frac{1}{2}\sum\_\{i, j, k, l\}\sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} H\_{ijkl} a ^ \dagger\_{i , \sigma} a ^ \dagger\_{k, \rho} a\_{l, \rho} a\_{j, \sigma}, $ $

ici $h _ {ijkl} = (IJ | KL) $ dans la Convention Mulliken.

Par souci de clarté, le terme à un seul électrons est

$ $ h_ {IJ} = \int {\mathrm d} x \Psi ^ *\_i (x) \left (\frac{1}{2}\nabla ^ 2 + \sum\_{A} \frac{Z\_A} {| x-x\_A |}  \right) \Psi\_j (x), $ $

et le terme à deux électrons est

$ $ h\_\{ijkl\} = \iint \{\mathrm d\}x ^ 2 \Psi ^\{\*\}\_i (x\_1) \Psi\_j (x\_1) \frac\{1\}\{\|x\_1-x\_2\|\}\Psi\_k ^\{\*\}(x\_2) \Psi\_l (x\_2).
$$

Comme indiqué dans la description de la [propriété`basis_set`](#basis-set-object) de chaque élément de la propriété `integral_sets`, nous supposons plus explicitement que les fonctions de base utilisées sont des valeurs réelles.
Cela nous permet d’utiliser les Symmetries suivantes entre les termes pour compresser la représentation de la représentation du même.

$ $ h_ {ijkl} = h_ {Ijlk} = h_ {jikl} = h_ {JiLK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Contents ####

Cette section est normative.

Chaque jeu entier doit avoir une propriété `hamiltonian` dont la valeur est un objet JSON.
La valeur de la propriété `hamiltonian` est appelée objet Hamilton, et doit avoir les propriétés `one_electron_integrals` et `two_electron_integrals` comme décrit dans le reste de cette section.
Un objet Hamilton peut également avoir une propriété `particle_hole_representation`.
Si elle est présente, la valeur de `particle_hole_representation` doit respecter le format décrit dans le reste de cette section.

##### <a name="one-electron-integrals-object"></a>Objet intégral à un seul électrons #####

Cette section est normative.

La propriété `one_electron_integrals` de l’objet Hamilton doit être une quantité de tableau épars dont les index sont deux entiers et dont les valeurs sont des nombres.
Chaque terme doit avoir des index `[i, j]` où `i >= j`.

> OBSERVE Cela reflète la symétrie qui $h _ {IJ} = h_ {ji} $, qui est une conséquence du fait que le Hermitian de la Hamilton est le même.


###### <a name="example"></a>Exemple ######

Cette section est informatif.

La quantité de tableau fragmenté suivante représente le volume de Hamilton $ $ H = \left (-5,0 (a ^\{\dagger\}\_{1, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{1, \downarrow}) + 0,17 (a ^\{\dagger\}\_{2, \uparrow} a\_{1, \uparrow} + a ^\{\dagger\}\_{1, \uparrow} a\_{2, \uparrow} + a ^\{\dagger\}\_{2 , \downarrow} a\_{1, \downarrow} + a ^\{\dagger\}\_{1, \downarrow} a\_{2, \downarrow}) \right)\\, \mathrm{Ha}.
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
> Broombridge utilise l’indexation basée sur 1.


##### <a name="two-electron-integrals-object"></a>Objet de type intégral à deux électrons #####

Cette section est normative.

La propriété `two_electron_integrals` de l’objet Hamilton doit être une grandeur de tableau épars avec une propriété supplémentaire appelée `index_convention`.
Chaque élément de la valeur de `two_electron_integrals` doit avoir quatre index.

Chaque propriété `two_electron_integrals` doit avoir une propriété `index_convention`.
La valeur de la propriété `index_convention` doit être l’une des valeurs autorisées figurant dans le tableau 1.
Si la valeur de `index_convention` est `mulliken`, alors pour chaque élément de la `two_electron_integrals` quantité de tableau épars, un analyseur chargeant un document Broombridge doit instancier un terme de Hamilton égal à l’opérateur à deux électrons $h _ {i, j, k, l} a ^ \ dagger_i un ^ \ dagger_j a_k a_l $, où $i $, $j $, $k $ et $l $ doivent être des entiers dans la plage inclusive comprise entre 1 et le nombre d’électrons spécifiés par la propriété `n_electrons` de l’objet ensemble entier, et où $h _ {i, j , k, l} $ est l’élément `[i, j, k, l, h(i, j, k, l)]` de la grandeur du tableau épars.

###### <a name="symmetries"></a>Symmetries ######

Cette section est normative.

Si la propriété `index_convention` d’un objet `two_electron_integrals` est égale à `mulliken`, si un élément avec des index `[i, j, k, l]` est présent, les index suivants ne doivent pas être présents, sauf s’ils sont égaux à `[i, j, k, l]`:

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Étant donné que la propriété `index_convention` est un objet de quantité éparse, aucun index ne peut être répété sur des éléments différents.
> En particulier, si un élément avec des index `[i, j, k, l]` est présent, aucun autre élément ne peut avoir ces index.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exemple #######

Cette section est informatif.

L’objet suivant spécifie la

$ $ H = \frac12 \sum\_{\sigma, \rho\in\\{\uparrow, \downarrow\\}} \Biggr (1,6 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{1, \rho} a\_{1, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{6, \sigma} a ^ {\dagger}\_{1, \rho} a\_{2 , \rho} a\_{3, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{3, \rho} a\_{2, \sigma}-0,1 a ^ {\dagger}\_{1, \sigma} a ^ {\dagger}\_{6, \rho} a\_{2, \rho} a\_{3, \sigma} $ $ $-0,1 a ^ {\dagger}\_{3, \sigma} a ^ {\dagger}\_{2, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{3 , \sigma} a ^ {\dagger}\_{2, \rho} a\_{1, \rho} a\_{6, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{6, \rho} a\_{1, \sigma}-0,1 a ^ {\dagger}\_{2, \sigma} a ^ {\dagger}\_{3, \rho} a\_{1, \rho} a\_{6, \sigma}\Biggr)\\, \textrm{Ha}.
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

##### <a name="particlehole-representation-object"></a>Particule : objet de représentation de trou #####

Cette section est normative.

L’objet de représentation particule-Hole spécifie que les intégrales stockées sont définies par rapport à la représentation de trou de particule dans laquelle les opérateurs de création et de annihilation décrivent les écarts par rapport à l’état de référence utilisé, tel qu’un Hartree – État de Fock.
L’objet est facultatif.
Si l’objet n’est pas spécifié, le lieu de la particule doit être interprété comme n’étant pas donné dans une représentation de trou de particule.
Si elle est présente, la valeur de `particle_hole_representation` doit être un objet de quantité de tableau fragmenté dont les index sont quatre entiers et dont les valeurs sont un nombre et une chaîne.
La partie de chaîne de la valeur de chaque élément doit contenir uniquement les caractères `'+'` et `'-'` qui spécifie si un facteur donné dans le terme est un opérateur de création ou de annihilation dans la représentation particule-Hole.  Par exemple `"-+++"` répond à un trou créé sur le site $i $ et les particules créées sur les sites $j, k $ et $l $.

> [!NOTE]
> Comme la valeur de l' `particle_hole_representation` est un objet de quantité de tableau fragmenté, les propriétés `unit` et `format` doivent être spécifiées.
> Les unités acceptables sont répertoriées dans le tableau 1.
> La propriété `format` est obligatoire et indique si les coefficients de Hamilton sont spécifiés comme un tableau dense ou épars.
> Dans la version actuelle, seuls les tableaux éparss sont pris en charge, avec l’interprétation que tous les éléments non spécifiés sont $0 $, mais les futures versions peuvent ajouter la prise en charge de valeurs supplémentaires de la propriété `format`.

### <a name="initial-state-section"></a>Section état initial ###

L’objet initial_state_suggestion spécifie les États quantiques initiaux qui présentent un intérêt pour le pays de Hamilton spécifié. Cet objet doit être un tableau d’objets `state` JSON.

#### <a name="state-object"></a>Objet d’État ####

Chaque État représente une superposition d’orbites occupés. Chaque objet d’État doit avoir une propriété `label` contenant une chaîne. Chaque objet d’État doit avoir une propriété `superposition` contenant un tableau d’États de base et leurs amplitudes non normalisées.

Par exemple, les États initiaux $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) \ket{0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{2, \uparrow}a ^ {\dagger}\_{2, \downarrow}) + 0,2 (a ^ {\dagger}\_{1, \uparrow}a ^ {\dagger}\_{3, \uparrow}a ^ {\dagger}\_{2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket{0} $ $ sont représentés par
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

#### <a name="basis-set-object"></a>Objet de jeu de base ####

Cette section est normative.

Chaque objet ensemble entier peut avoir une propriété `basis_set`.
Si elle est présente, la valeur de la propriété `basis_set` doit être un objet avec deux propriétés, `type` et `name`.

Les fonctions de base identifiées par la valeur de la propriété `basis_set` doivent être des valeurs réelles.

> [!NOTE]
> En supposant que toutes les fonctions de base sont des valeurs réelles, elles peuvent être assouplies dans les futures versions de cette spécification.

## <a name="tables-and-lists"></a>Tables et listes ##

### <a name="table-1-allowed-physical-units"></a>Tableau 1. Unités physiques autorisées ###

Cette section est normative.

Toute chaîne spécifiant une unité doit être l’une des suivantes :

- `hartree`
- `ev`

Les analyseurs et les producteurs doivent traiter les objets de quantité simple suivants comme équivalents :

```yaml
- {"units": "hartree", "value": 1}
- {"units": "ev", "value": 27.2113831301723}
```

### <a name="table-2-allowed-index-conventions"></a>Tableau 2. Conventions d’index autorisées ###

Cette section est normative.

Toute chaîne spécifiant une convention d’index doit être l’une des suivantes :

- `mulliken`

Cette section est informatif.

Des conventions d’index supplémentaires peuvent être introduites dans les versions ultérieures de cette spécification.

#### <a name="interpretation-of-index-conventions"></a>Interprétation des conventions d’index ####

Cette section est informatif.
