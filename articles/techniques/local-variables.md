---
title: 'Variables locales-techniques Q #'
description: 'Découvrez comment définir et utiliser des variables locales dans Q #.'
author: QuantumWriter
ms.author: Christopher.Granade@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.techniques.local-variables
ms.openlocfilehash: cb6c662137c31a13c3dd6e9ca3f67879c469f788
ms.sourcegitcommit: 6ccea4a2006a47569c4e2c2cb37001e132f17476
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/28/2020
ms.locfileid: "77906863"
---
# <a name="local-variables"></a><span data-ttu-id="93cfe-103">Variables locales</span><span class="sxs-lookup"><span data-stu-id="93cfe-103">Local Variables</span></span> #

<span data-ttu-id="93cfe-104">Une valeur de n’importe quel type dans Q # peut être assignée à une variable pour être réutilisée au sein d’une opération ou d’une fonction à l’aide du mot clé `let`.</span><span class="sxs-lookup"><span data-stu-id="93cfe-104">A value of any type in Q# can be assigned to a variable for reuse within an operation or function by using the `let` keyword.</span></span>
<span data-ttu-id="93cfe-105">Exemple :</span><span class="sxs-lookup"><span data-stu-id="93cfe-105">For instance:</span></span>

```qsharp
let measurementOperator = [PauliX, PauliZ, PauliZ, PauliX, PauliI];
```

<span data-ttu-id="93cfe-106">Cela affecte un tableau particulier d’opérateurs Pauli à une variable appelée `measurementOperator`.</span><span class="sxs-lookup"><span data-stu-id="93cfe-106">This assigns a particular array of Pauli operators to a variable called `measurementOperator`.</span></span>

> [!TIP]
> <span data-ttu-id="93cfe-107">Notez que nous n’avons pas besoin de spécifier explicitement le type de notre nouvelle variable, car l’expression sur le côté droit de l’instruction `let` n’est pas ambiguë et le type est déduit par le compilateur.</span><span class="sxs-lookup"><span data-stu-id="93cfe-107">Note that we did not need to explicitly specify the type of our new variable, as the expression on the right-hand side of the `let` statement is unambiguous and the type is inferred by the compiler.</span></span> 

<span data-ttu-id="93cfe-108">Les variables dans Q # sont *immuables*, ce qui signifie qu’une fois qu’une variable a été définie de cette façon, elle ne peut plus être modifiée.</span><span class="sxs-lookup"><span data-stu-id="93cfe-108">Variables in Q# are *immutable*, meaning that once a variable has been defined in this way, it can no longer be changed in any way.</span></span>
<span data-ttu-id="93cfe-109">Cela permet d’effectuer plusieurs optimisations bénéfiques, notamment l’optimisation de la logique classique agissant sur les variables à réorganiser pour l’application de la `Adjoint` variante d’une opération.</span><span class="sxs-lookup"><span data-stu-id="93cfe-109">This allows for several beneficial optimizations, including optimization of the classical logic acting on variables to be reordered for applying the `Adjoint` variant of an operation.</span></span>

<span data-ttu-id="93cfe-110">Les variables définies à l’aide de la liaison `let` comme ci-dessus sont locales à une portée particulière, telles que le corps d’une opération ou le contenu d’une boucle `for`.</span><span class="sxs-lookup"><span data-stu-id="93cfe-110">Variables defined using the `let` binding as above are local to a particular scope, such as the body of an operation or the contents of a `for` loop.</span></span>


## <a name="mutability"></a><span data-ttu-id="93cfe-111">Mutabilité</span><span class="sxs-lookup"><span data-stu-id="93cfe-111">Mutability</span></span> ##

<span data-ttu-id="93cfe-112">En guise d’alternative à la création d’une variable avec `let`, le mot clé `mutable` crée une variable mutable spéciale qui peut être reliée après sa création initiale à l’aide du mot clé `set`.</span><span class="sxs-lookup"><span data-stu-id="93cfe-112">As an alternative to creating a variable with `let`, the `mutable` keyword will create a special mutable variable that can be re-bound after it is initially created by using the `set` keyword.</span></span>

```qsharp
operation RandomInts(maxInt : Int, nrSamples : Int) : Int[] {
    mutable samples = new Int[0];
    for (i in 1 .. nrSamples) {
        set samples += [RandomInt(maxInt)];
    }
    return samples;
}
```

<span data-ttu-id="93cfe-113">Tous les types dans Q #, y compris les tableaux, suivent la sémantique des valeurs.</span><span class="sxs-lookup"><span data-stu-id="93cfe-113">All types in Q#, including arrays, follow value semantics.</span></span> <span data-ttu-id="93cfe-114">En particulier, il n’est pas possible de mettre à jour les éléments d’un tableau.</span><span class="sxs-lookup"><span data-stu-id="93cfe-114">In particular, it is not possible to update array items.</span></span> <span data-ttu-id="93cfe-115">Pour modifier un tableau existant, vous devez tirer parti d’un mécanisme de copie et de mise à jour semblable à F#celui des enregistrements dans.</span><span class="sxs-lookup"><span data-stu-id="93cfe-115">To modify an existing array requires leveraging a copy-and-update mechanism much like the one for records in F#.</span></span> <span data-ttu-id="93cfe-116">À l’aide des outils de bibliothèque pour les tableaux fournis dans [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), nous pouvons, par exemple, définir facilement une fonction qui retourne un tableau de Paulis où le Pauli à l’index `i` prend la valeur donnée et toutes les autres entrées sont l’identité :</span><span class="sxs-lookup"><span data-stu-id="93cfe-116">Using the library tools for arrays provided in [`Microsoft.Quantum.Arrays`](xref:microsoft.quantum.arrays), we can e.g. easily define a function that returns an array of Paulis where the Pauli at index `i` takes the given value and all other entries are the identity:</span></span> 

```qsharp
function EmbedPauli (pauli : Pauli, i : Int, n : Int) : Pauli[] {
    
    let arr = ConstantArray(n, PauliI); // creates an array of filled with PauliI
    return arr w/ i <- pauli; // constructs a new array based on arr except that entry i is set to pauli
}
```

<span data-ttu-id="93cfe-117">Nous étudierons plus en détail l’utilisation des tableaux lors de l’examen des instructions et expressions Q #.</span><span class="sxs-lookup"><span data-stu-id="93cfe-117">We will elaborate more on how to work with arrays when discussing Q# statements and expressions.</span></span> 

<span data-ttu-id="93cfe-118">La mutabilité dans Q # est un concept qui s’applique à un *symbole* plutôt qu’à un type ou une valeur.</span><span class="sxs-lookup"><span data-stu-id="93cfe-118">Mutability within Q# is a concept that applies to a *symbol* rather than a type or value.</span></span> <span data-ttu-id="93cfe-119">Plus précisément, il n’a pas de représentation dans le système de type, implicitement ou explicitement, et si une liaison est mutable (comme indiqué par le mot clé `mutable`) ou immuable (comme indiqué par `let`) ne modifie pas le type de la ou des variables liées.</span><span class="sxs-lookup"><span data-stu-id="93cfe-119">Specifically, it does not have a representation in the type system, implicitly or explicitly, and whether or not a binding is mutable (as indicated by the `mutable` keyword) or immutable (as indicated by `let`) does not change the type of the bound variable(s).</span></span> <span data-ttu-id="93cfe-120">Cela offre un moyen important d’isoler la mutabilité dans des fonctions et des opérations spécialisées.</span><span class="sxs-lookup"><span data-stu-id="93cfe-120">This provides an important way to isolate mutability inside specialized functions and operations.</span></span>
<span data-ttu-id="93cfe-121">En particulier, même si une spécialisation voisine d’une opération qui utilise une variable mutable ne peut pas être générée automatiquement, la génération automatique fonctionne correctement pour une opération qui appelle une fonction qui utilise mutabilité.</span><span class="sxs-lookup"><span data-stu-id="93cfe-121">In particular, even though an adjoint specialization for an operation which uses a mutable variable cannot be auto-generated, auto-generation works fine for an operation calling a function which uses mutability.</span></span>
<span data-ttu-id="93cfe-122">Pour cette raison, il est recommandé de faire en sorte que les fonctions et les opérations qui utilisent la mutabilité soient courtes et compactes, afin que le reste du programme Quantum puisse être écrit à l’aide de variables immuables ordinaires.</span><span class="sxs-lookup"><span data-stu-id="93cfe-122">For this reason, it is a good practice to make functions and operations which use mutability as short and compact as possible, so that the rest of the quantum program can be written using ordinary immutable variables.</span></span>


## <a name="deconstruction"></a><span data-ttu-id="93cfe-123">Déconstruction</span><span class="sxs-lookup"><span data-stu-id="93cfe-123">Deconstruction</span></span> ##

<span data-ttu-id="93cfe-124">Outre l’affectation d’une seule variable, les mots clés `let` et `mutable`, ou en fait, toute autre construction de liaison, permettent également de décompresser le contenu d’un [type de tuple](xref:microsoft.quantum.language.type-model#tuple-types).</span><span class="sxs-lookup"><span data-stu-id="93cfe-124">In addition to assigning a single variable, the `let` and `mutable` keywords - or in fact any other binding construct - also allow for unpacking the contents of a [tuple type](xref:microsoft.quantum.language.type-model#tuple-types).</span></span>
<span data-ttu-id="93cfe-125">Une assignation de ce formulaire est dite pour *déconstruire* les éléments de ce tuple.</span><span class="sxs-lookup"><span data-stu-id="93cfe-125">An assignment of this form is said to *deconstruct* the elements of that tuple.</span></span>
<span data-ttu-id="93cfe-126">Par exemple, si nous modélisons un terme dans un même lieu par un tuple, nous pouvons utiliser la déconstruction pour accéder aux différentes données que nous devons simuler sous ce terme :</span><span class="sxs-lookup"><span data-stu-id="93cfe-126">For instance, if we model a term in a Hamiltonian by a tuple, then we can use deconstruction to access the different data that we need to simulate under that term:</span></span>

```qsharp
// Represents H = 3.1 X_0 Z_1.
let (_, (paulis, idxQubits)) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // paulis and idxQubits are both immutable variables
mutable ((c1, c2), _) = ((3.1, 1.0), ([PauliX, PauliZ], [0, 1])); // c1 and c2 are both mutable variables
```


