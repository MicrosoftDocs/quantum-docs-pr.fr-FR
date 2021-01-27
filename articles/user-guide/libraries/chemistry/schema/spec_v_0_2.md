---
title: Spécification de schéma Broombridge (ver 0,2)
description: Décrit en détail les spécifications du schéma Broombridge Quantum chimie v 0,2 pour la bibliothèque Microsoft Quantum chimie.
author: guanghaolow
ms.author: gulow
ms.date: 05/28/2019
ms.topic: conceptual
uid: microsoft.quantum.libraries.chemistry.schema.spec_v_0_2
no-loc:
- Q#
- $$v
ms.openlocfilehash: 8d26b56d88f365144510692466bfffc7feb71d88
ms.sourcegitcommit: 71605ea9cc630e84e7ef29027e1f0ea06299747e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98854065"
---
# <a name="broombridge-specification-v02"></a>Spécification Broombridge v 0,2 #

Les mots clés « doit », « ne doit pas », « obligatoire », « doit », « ne doit pas « », « ne doit pas », « recommandé », « peut » et « facultatif » dans ce document doivent être interprétés comme décrit dans le document [RFC 2119](https://tools.ietf.org/html/rfc2119).

Tout encadré avec les en-têtes « NOTE », « INFORMATION » ou « avertissement » est informatif.

## <a name="introduction"></a>Introduction ##

Cette section est informatif.

Les documents Broombridge sont destinés à communiquer des instances de problèmes de simulation dans la chimie Quantum à traiter à l’aide de la simulation quantique et de la programmation chaînes.

## <a name="serialization"></a>Sérialisation ##

Cette section est normative.

Un document Broombridge doit être sérialisé en tant que [document YAML 1,2](http://yaml.org/spec/) représentant un objet JSON, comme décrit dans la section [RFC 4627](https://tools.ietf.org/html/rfc4627) 2,2.
L’objet sérialisé en YAML doit avoir une propriété `"$schema"` dont la valeur est `"https://raw.githubusercontent.com/Microsoft/Quantum/master/Chemistry/Schema/qchem-0.2.schema.json"` et doit être valide conformément aux spécifications Draft-06 du schéma JSON [[1](https://tools.ietf.org/html/draft-wright-json-schema-01), [2](https://tools.ietf.org/html/draft-wright-json-schema-validation-01)].

Pour le reste de cette spécification, « l’objet Broombridge » fait référence à l’objet JSON désérialisé à partir d’un document Broombridge YAML.

Sauf mention contraire explicite, les objets ne doivent pas avoir de propriétés supplémentaires au-delà de celles spécifiées explicitement dans ce document.

## <a name="additional-definitions"></a>Définitions supplémentaires ##

Cette section est normative.

### <a name="quantity-objects"></a>Objets Quantity ###

Cette section est normative.

Un _objet Quantity_ est un objet JSON et doit avoir une propriété `units` dont la valeur est l’une des valeurs autorisées figurant dans le tableau 1.

Un objet Quantity est un _objet Quantity simple_ s’il a une propriété unique `value` en plus de sa `units` propriété.
La valeur de la `value` propriété doit être un nombre.

Un objet Quantity est un _objet Quantity limité_ s’il possède les propriétés `lower` et `upper` en plus de sa `units` propriété.
Les valeurs des `lower` Propriétés et `upper` doivent être des nombres.
Un objet de quantité limitée peut avoir une propriété `value` dont la valeur est un nombre.

Un objet Quantity est un _objet de grandeur de tableau fragmenté_ s’il a la propriété `format` et une propriété `values` en plus de sa `units` propriété.
La valeur de `format` doit être la chaîne `sparse` .
La valeur de la `values` propriété doit être un tableau.
Chaque élément de `values` doit être un tableau représentant les index et la valeur de la grandeur du tableau fragmenté.

Les index de chaque élément d’un objet de quantité éparse de tableau doivent être uniques dans l’ensemble de l’objet grandeur du tableau fragmenté.
Si un index est présent avec la valeur `0` , un analyseur doit traiter l’objet de grandeur du tableau fragmenté de la même manière qu’un objet de grandeur de tableau fragmenté dans lequel cet index n’est pas présent.


Un objet Quantity doit avoir la valeur

- un objet Quantity simple,
- un objet de quantité limitée, ou
- objet de grandeur de tableau fragmenté.


### <a name="examples"></a>Exemples ###

Cette section est informatif.

Une quantité simple représentant $1.9844146837 \, \mathrm{ha} $ :

```yaml
coulomb_repulsion:
    value: 1.9844146837
    units: hartree
```

Une quantité limitée représentant une distribution uniforme sur l’intervalle $ [-7,-6] \, \mathrm{ha} $ :

```yaml
fci_energy:
    upper: -6
    lower: -7
    units: hartree
```

Ce qui suit est une grandeur de tableau fragmenté avec un élément `[1, 2]` égal à `hello` et un élément `[3, 4]` égal à `world` :

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

L’objet Broombridge doit avoir une propriété `format` dont la valeur est un objet JSON avec une propriété appelée `version` .
La `version` propriété doit avoir la valeur `"0.2"` .

### <a name="example"></a>Exemple ###

Cette section est informatif.

```yaml
format:                        # required
    version: "0.2"             # must match exactly
```

## <a name="problem-description-section"></a>Section Description du problème ##

Cette section est normative.

L’objet Broombridge doit avoir une propriété `problem_description` dont la valeur est un tableau JSON.
Chaque élément de la valeur de la `problem_description` propriété doit être un objet JSON décrivant un ensemble d’intégrateurs, comme décrit dans le reste de cette section.
Dans le reste de cette section, le terme « objet de description du problème » fait référence à un élément dans la valeur de la `problem_description` propriété de l’objet Broombridge.

Chaque objet de description du problème doit avoir une propriété `metadata` dont la valeur est un objet JSON.
La valeur de `metadata` peut être l’objet JSON vide (autrement dit, `{}` ), ou peut contenir des propriétés supplémentaires définies par l’implémenteur.

### <a name="hamiltonian-section"></a>Section Hamilton ###

#### <a name="overview"></a>Vue d’ensemble ####

Cette section est informatif.

La `hamiltonian` propriété de chaque objet de description du problème décrit le niveau de Hamilton pour un problème de chimie de Quantum particulier en répertoriant ses termes à un et deux corps comme des tableaux éparss de nombres réels.
Les opérateurs de type Hamilton décrits par chaque objet de description du problème prennent la forme

$ $ H = \sum \_ \{ i, j \} \sum \_ {\sigma\in \\ {\uparrow, \downarrow \\ }} H \_ \{ IJ \} a ^ \{ \dagger \} \_ {i, \sigma} a \_ {j, \sigma} + \frac {1} {2} \sum \_ \{ i, j, k, l \} \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} H \_ {ijkl} a ^ \dagger \_ {i, \sigma} a ^ \dagger \_ {k, \rho} a \_ {l, \rho} a \_ {j, \sigma}, $ $

ici $h _ {ijkl} = (IJ | KL) $ dans la Convention Mulliken.

Par souci de clarté, le terme à un seul électrons est

$ $ h_ {IJ} = \int {\mathrm d} x \Psi ^ * \_ i (x) \left (\frac {1} {2} \nabla ^ 2 + \sum \_ {a} \frac{Z \_ a} {| x-x \_ A |}  \right) \Psi \_ j (x), $ $

et le terme à deux électrons est

$ $ h \_ \{ ijkl \} = \iint \{ \mathrm d \} x ^ 2 \Psi ^ \{ \* \} \_ i (x \_ 1) \Psi \_ j (x \_ 1) \frac \{ 1 \} \{ \| x \_ 1-x \_ 2 \| \} \Psi \_ k ^ \{ \* \} (x \_ 2) \Psi \_ l (x \_ 2).
$$

Comme indiqué dans la description de la [ `basis_set` propriété](#basis-set-object) de chaque élément de la `integral_sets` propriété, nous supposons plus explicitement que les fonctions de base utilisées sont des valeurs réelles.
Cela nous permet d’utiliser les Symmetries suivantes entre les termes pour compresser la représentation de la représentation du même.

$ $ h_ {ijkl} = h_ {Ijlk} = h_ {jikl} = h_ {JiLK} = h_ {klij} = h_ {klji} = h_ {lkij} = h_ {lkji}.
$$


#### <a name="contents"></a>Contenu ####

Cette section est normative.

Chaque objet de description du problème doit avoir une propriété `hamiltonian` dont la valeur est un objet JSON.
La valeur de la `hamiltonian` propriété est appelée objet Hamilton, et doit avoir les propriétés `one_electron_integrals` et `two_electron_integrals` comme décrit dans le reste de cette section.

Chaque objet de description du problème doit avoir une propriété `coulomb_repulsion` dont la valeur est un objet de quantité simple.
Chaque objet de description du problème doit avoir une propriété `energy_offet` dont la valeur est un objet de quantité simple.
> OBSERVE Les valeurs de `coulomb_repulsion` et `energy_offet` ajoutées ensemble capturent la valeur d’identité de la « Hamilton ».

##### <a name="one-electron-integrals-object"></a>Objet One-Electron intégrales #####

Cette section est normative.

La `one_electron_integrals` propriété de l’objet Hamilton doit être une quantité de tableau épars dont les index sont deux entiers et dont les valeurs sont des nombres.
Chaque terme doit avoir des index `[i, j]` où `i >= j` .

> OBSERVE Cela reflète la symétrie qui $h _ {IJ} = h_ {ji} $, qui est une conséquence du fait que le Hermitian de la Hamilton est le même.


###### <a name="example"></a>Exemple ######

Cette section est informatif.

La quantité de tableau fragmenté suivante représente le point de Hamilton $ $ H = \left (-5,0 (a ^ \{ \dagger \} \_ {1, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {1, \downarrow}) + 0,17 (a ^ \{ \dagger \} \_ {2, \uparrow} a \_ {1, \uparrow} + a ^ \{ \dagger \} \_ {1, \uparrow} a {2 \_ , \uparrow} + a ^ \{ \dagger \} \_ {2, \downarrow} a \_ {1, \downarrow} + a ^ \{ \dagger \} \_ {1, \downarrow} a \_ {2, \downarrow}) \right) \\ , \mathrm{ha}.
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


##### <a name="two-electron-integrals-object"></a>Objet Two-Electron intégrales #####

Cette section est normative.

La `two_electron_integrals` propriété de l’objet Hamilton doit être une grandeur de tableau épars avec une propriété supplémentaire appelée `index_convention` .
Chaque élément de la valeur de `two_electron_integrals` doit avoir quatre index.

Chaque `two_electron_integrals` propriété doit avoir une `index_convention` propriété.
La valeur de la `index_convention` propriété doit être l’une des valeurs autorisées figurant dans le tableau 1.
Si la valeur de `index_convention` est `mulliken` , pour chaque élément de la `two_electron_integrals` grandeur du tableau partiellement alloué, un analyseur chargeant un document Broombridge doit instancier un terme de Hamilton égal à l’opérateur à deux électrons $h _ {i, j, k, l} a ^ \ dagger_i un ^ \ dagger_j a_k a_l $, où $i $, $j $, $k $ et $l $ doivent être des entiers de valeur au moins 1, et où $h _ {i, j, k, l} $ est l’élément `[i, j, k, l, h(i, j, k, l)]` de la grandeur du tableau fragmenté.

###### <a name="symmetries"></a>Symmetries ######

Cette section est normative.

Si la `index_convention` propriété d’un `two_electron_integrals` objet est égale à `mulliken` , alors qu’un élément avec des index `[i, j, k, l]` est présent, les index suivants ne doivent pas être présents, sauf s’ils sont égaux à `[i, j, k, l]` :

- `[i, j, l, k]`
- `[j, i, k, l]`
- `[j, i, l, k]`
- `[k, l, i, j]`
- `[k, l, j, i]`
- `[l, k, j, i]`

> [!NOTE]
> Étant donné que la `index_convention` propriété est un objet de quantité éparse, aucun index ne peut être répété sur des éléments différents.
> En particulier, si un élément avec des index `[i, j, k, l]` est présent, aucun autre élément ne peut avoir ces index.


<!-- h_{ijkl} = h_{ijlk}=h_{jikl}=h_{jilk}=h_{klij}=h_{klji}=h_{lkji}. -->

###### <a name="example"></a>Exemple #######

Cette section est informatif.

L’objet suivant spécifie la

$ $ H = \frac12 \sum \_ {\sigma, \rho\in \\ {\uparrow, \downarrow \\ }} \Biggr (1,6 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {1, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {3, \rho} a { \_ 2, \sigma}-0,1 a ^ {\dagger} \_ {6, \sigma} a ^ {\dagger} \_ {1, \rho} a \_ {2, \rho} \_ 0,1 a ^ {\sigma}- \_ {1, \dagger} a ^ {\sigma} \_ {6, \rho} a \_ {3, \rho} a \_ {2, \sigma}-0,1 a ^ {\dagger} \_ {1, \sigma} a ^ {\dagger} \_ {6, \rho} a \_ {2, \rho} a \_ {3, \sigma} $ $ $-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {3, \sigma} a ^ {\dagger} \_ {2, \rho} a \_ {1, \rho} a \_ {6, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3 , \rho} a \_ {6, \rho} a \_ {1, \sigma}-0,1 a ^ {\dagger} \_ {2, \sigma} a ^ {\dagger} \_ {3, \rho} a \_ {1, \Rho} a \_ {6, \sigma}\Biggr) \\ , \textrm{ha}.
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

### <a name="initial-state-section"></a>Section état initial ###

Cette section est normative.

L' `initial_state_suggestion` objet dont la valeur est un tableau JSON spécifie les États de Quantum initiaux qui présentent un intérêt pour le pays de Hamilton spécifié. Chaque élément de la valeur de la `initial_state_suggestion` propriété doit être un objet JSON décrivant un État Quantum, comme décrit dans le reste de cette section.
Dans le reste de cette section, le terme « objet d’État » fait référence à un élément dans la valeur de la `initial_state_suggestion` propriété de l’objet Broombridge.

#### <a name="state-object"></a>Objet d’État ####

Cette section est normative.

Chaque objet d’État doit avoir une `label` propriété contenant une chaîne. Chaque objet d’État doit avoir une `method` propriété. La valeur de la `method` propriété doit être l’une des valeurs autorisées énumérées dans le tableau 3.
Chaque objet d’État peut avoir une propriété `energy` dont la valeur doit être un objet de quantité simple.

Si la valeur de la `method` propriété est `sparse_multi_configurational` , l’objet d’État doit avoir une `superposition` propriété contenant un tableau d’États de base et leurs amplitudes non normalisées.

Par exemple, les États initiaux $ $ \ket{G0} = \ket{G1} = \ket{G2} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} $ $ $ $ \ket{E} = \frac{0.1 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) + 0,2 (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \uparrow}a ^ {\dagger} \_ {2, \downarrow})} {\sqrt{| 0.1 | ^ 2 + | 0,2 | ^ 2}} \ket {0} , $ $ where $ \ket{E} $ a Energy $0,987 \textrm{ha} $, sont représentés par
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

Si la valeur de la `method` propriété est `unitary_coupled_cluster` , l’objet d’État doit avoir une `cluster_operator` propriété dont la valeur est un objet JSON.
L’objet JSON doit avoir une `reference_state` propriété dont la valeur est un état de base.
L’objet JSON peut avoir une `one_body_amplitudes` propriété dont la valeur est un tableau d’opérateurs de cluster à un corps et leurs amplitudes.
L’objet JSON peut avoir une `two_body_amplitudes` propriété dont la valeur est un tableau d’opérateurs de cluster à deux corps et leurs amplitudes.
contenant un tableau d’États de base et leurs amplitudes non normalisées.

Par exemple, l’État $ $ \ket{\text{Reference}} = (a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {2, \uparrow}a ^ {\dagger} \_ {2, \downarrow}) \ket {0} , $ $

$ $ \ket{\text{UCCSD}} = e ^ {T-T ^ \dagger}\ket{\text{Reference}}, $ $

$ $ T = 0,1 a ^ {\dagger} \_ {3, \uparrow}a \_ {2, \downarrow} + 0,2 a ^ {\dagger} \_ {2, \uparrow}a \_ {2, \downarrow}-0,3 a ^ {\dagger} \_ {1, \uparrow}a ^ {\dagger} \_ {3, \downarrow}a \_ {3, \uparrow}a \_ {2, \downarrow} $ $ est représenté par
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

#### <a name="basis-set-object"></a>Objet de jeu de base ####

Cette section est normative.

Chaque objet de description du problème peut avoir une `basis_set` propriété.
Si elle est présente, la valeur de la `basis_set` propriété doit être un objet avec deux propriétés, `type` et `name` .

Les fonctions de base identifiées par la valeur de la `basis_set` propriété doivent être des valeurs réelles.

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

### <a name="table-3-allowed-state-methods"></a>Tableau 3. Méthodes d’État autorisées ###

Cette section est normative.

Toute chaîne spécifiant une méthode d’État doit être l’une des suivantes :

- `sparse_multi_configurational`
- `unitary_coupled_cluster`

Cette section est informatif.

Des méthodes d’État supplémentaires peuvent être introduites dans les versions ultérieures de cette spécification.
