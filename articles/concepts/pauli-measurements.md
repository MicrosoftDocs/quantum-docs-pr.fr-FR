---
titre : Pauli mesures Description : Apprenez à utiliser des opérations de mesure Pauli à qubit unique et à plusieurs.
Auteur : bradben UID : Microsoft. Quantum. concepts. Pauli ms. Author : v-benbra ms. Date : 12/11/2017 ms. topic : article No-Loc :
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "\cdots"
- "bmatrix"
- "\ddots"
- "\equiv"
- "\sum"
- "\begin"
- "\end"
- "\sqrt"
- "\otimes"
- "{"
- "}"
- "\text"
- "\phi"
- "\kappa"
- "\psi"
- "\alpha"
- "\beta"
- "\gamma"
- "\delta"
- "\omega"
- "\bra"
- "\ket"
- "\boldone"
- "\\\\"
- "\\"
- "="
- "\frac"
- "\text"
- "\mapsto"
- "\dagger"
- "\to"
- "\begin{cases}"
- "\end{cases}"
- "\operatorname"
- "\braket"
- "\id"
- "\expect"
- "\defeq"
- "\variance"
- "\dd"
- "&"
- "\begin{align}"
- "\end{align}"
- "\Lambda"
- "\lambda"
- "\Omega"
- "\mathrm"
- "\left"
- "\right"
- "\qquad"
- "\times"
- "\big"
- "\langle"
- "\rangle"
- "\bigg"
- "\Big"
- "|"
- "\mathbb"
- "\vec"
- "\in"
- "\texttt"
- "\ne"
- "<"
- ">"
- "\leq"
- "\geq"
- "~~"
- "~"
- "\begin{bmatrix}"
- "\end{bmatrix}"
- "\_"

---

# <a name="pauli-measurements"></a>Mesures Pauli

Dans les discussions précédentes, nous nous sommes concentrés sur les mesures de base de calcul.
En fait, il existe d’autres mesures courantes qui se produisent dans quantum computing qui, du point de vue de la notation, sont pratiques pour exprimer en termes de mesures de la base de calcul.
À mesure que vous travaillez avec Q# , le type de mesure le plus courant dans lequel vous allez être exécuté sera probablement des *mesures Pauli*, qui généralisent les mesures de base de calcul pour inclure des mesures dans d’autres bases et de la parité entre différents qubits.
Dans ce cas, il est courant d’examiner la mesure d’un opérateur Pauli, en général un opérateur tel que $ X, Y, z $ ou $ z \otimes z, x \otimes x, x \otimes Y $ , etc.

> [!TIP]
> Dans Q# , les opérateurs Pauli multi-qubit sont généralement représentés par des tableaux de type `Pauli[]` .
> Par exemple, pour représenter $ X \otimes Z \otimes Y $ , vous pouvez utiliser le tableau `[PauliX, PauliZ, PauliY]` .

L’étude des mesures en termes d’opérateurs Pauli est particulièrement courante dans le sous-champ de la correction des erreurs Quantum.
Dans Q# , nous suivons une convention similaire. nous expliquons maintenant cette vue alternative des mesures.

Avant de plonger dans les détails sur la façon de considérer une mesure Pauli, il est utile de réfléchir à la mesure d’un qubit unique dans un ordinateur quantique à l’État Quantum.
Imaginez que nous avons un $ $ État Quantum n-qubit, puis que la mesure d’un qubit règle immédiatement la moitié des $ 2 ^ n possibilités de l' $ État.
En d’autres termes, la mesure projette l’État Quantum sur l’un des deux demi-espaces.
Nous pouvons généraliser la façon dont nous pensons à la mesure pour refléter cette intuition.

Pour identifier ces sous-espaces de manière concise, nous avons besoin d’un langage pour les décrire.
Une façon de décrire les deux sous-espaces consiste à les spécifier à l’aide d’une matrice qui a simplement deux valeurs propres uniques, pris par convention comme $ \pm 1 $ .
Pour obtenir un exemple simple de description des sous-espaces de cette manière, utilisez $ Z $ :

$$
\begin{align}
  Z & = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} .
\end{align}
$$

En lisant les éléments diagonales de la matrice Pauli- $ Z $ , nous voyons que $ Z $ a deux vecteurs propres, $ \ket { 0 } $ et $ \ket { 1 } $ , avec le valeurs propres $ \pm 1 correspondant $ .
Ainsi, si nous mesurons qubit et obtenons `Zero` (correspondant à l’état $ \ket { 0 } $ ), nous savons que l’état de notre qubit est $ + 1 $ eigenstate de l' $ $ opérateur Z.
De même, si nous obtenons `One` , nous savons que l’état de notre qubit est $ -1 $ eigenstate de $ Z $ . Ce processus est appelé dans le langage des mesures de Pauli comme « mesurant Pauli $ Z $ » et est entièrement équivalent à l’exécution d’une mesure de base de calcul.

Toute $ \times matrice 2 2 $ qui est une transformation unitaire de $ Z $ répond également à ce critère.
Autrement dit, nous pourrions également utiliser une matrice $ a = u ^ \dagger Z u $ , où $ U $ est une autre matrice unitaire, pour fournir une matrice qui définit les deux résultats d’une mesure dans son $ \pm 1 $ vecteurs propres.
La notation des mesures Pauli fait référence à cette équivalence unitaire en identifiant les $ mesures X, Y, Z $ comme des mesures équivalentes qu’il est possible d’obtenir pour obtenir des informations à partir d’un qubit.
Ces mesures sont fournies ci-dessous pour des raisons pratiques.


|Transformation d’unité de mesure Pauli ||
|-------------------|------------------------|
|$ $ Z |               $\boldone$             |
|$ $ X | $H               $                    |
|$ $ Y | $HS ^               {\dagger}$         |

Autrement dit, l’utilisation de ce langage, « Measure $ Y $ » équivaut à appliquer HS ^, puis à $ \dagger $ mesurer la base de calcul, où [`S`](xref:microsoft.quantum.intrinsic.s) est une opération quantique intrinsèque parfois appelée « porte-phase » et peut être simulée par la matrice d’unités

$$
\begin{align}
    S =\begin{bmatrix}
        1 & 0 \\\\ 0 & i \end{bmatrix} .
\end{align}
$$

Cela équivaut également à appliquer $ HS ^ \dagger $ au vecteur d’État Quantum, puis à mesurer $ Z $ , de telle sorte que l’opération suivante soit équivalente à `Measure([PauliY], [q])` :

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

L’état correct est ensuite trouvé en transformant la base de calcul, ce qui correspond à l’application de $ SH $ au vecteur d’État Quantum. dans l’extrait de code ci-dessus, la transformation en retour à la base de calcul est gérée automatiquement par l’utilisation du `within … apply` bloc.

Dans Q# , nous disons le résultat---autrement dit, les informations classiques extraites de l’interaction avec l’État---sont données par une `Result` valeur $ j \in \\ { \texttt { zéro } , l' \texttt { une } \\ } $ indiquant si le résultat se trouve dans le $ (-1) ^ j $ eigenspace de l’opérateur Pauli mesuré.


## <a name="multiple-qubit-measurements"></a>Mesures à plusieurs qubit

Les mesures des opérateurs Pauli à plusieurs qubit sont définies de la même manière, comme le montre l’exemple suivant :

$$
Z \otimes z 1 0 0 0 0 = \begin{bmatrix} & & & \\\\ & -1 & 0 0 0 0 & \\\\ & & -1 & 0 \\\\ & & & \end{bmatrix} 0 0 0 1.
$$

Ainsi, les produits tenseur de deux opérateurs Pauli- $ Z $ forment une matrice composée de deux espaces composés de $ + 1 $ et $ -1 $ valeurs propres.
Comme avec le cas qubit, les deux constituent un demi-espace, ce qui signifie que la moitié de l’espace de vecteur accessible appartient au $ + 1 $ eigenspace et la moitié restante à la $ eigenspace-1 $ .
En général, il est facile de voir à partir de la définition du produit tenseur que tout produit tenseur d’opérateurs Pauli- $ Z $ et l’identité en obéissent également.
Par exemple,

$$
\begin{align}
    \otimes \boldone Z =\begin{bmatrix}
        1 & 0 & 0 0 &\\\\
        0 &  1 &  0 &  0 \\\\
        0 & & -1 0 &\\\\
        0 0 0 & & & -1 \end{bmatrix} .
\end{align}
$$

Comme précédemment, toute transformation unitaire de ces matrices décrit également deux demi-espaces étiquetés par $ \pm 1 $ valeurs propres.
Par exemple, $ x \otimes x = h \otimes h (z \otimes z) h \otimes h $  à partir de l’identité $ Z = HxH $ .
Comme dans le cas d’une qubit, toutes les mesures Pauli à deux qubit peuvent être écrites en u $ ^ \dagger (Z \otimes \id ) u $ pour $ 4 \times 4 $ matrices unitaires $ u $ . Nous énumérons les transformations dans le tableau suivant.

> [!NOTE]
>Dans le tableau ci-dessous, nous utilisons $ \operatorname { swap } $ pour indiquer la matrice >$$
> \begin{align}
>     \operatorname{ÉCHANGE } &=
>     \left( \begin { matrice}
>1 & 0 & 0 0 &\\\\
>         0 & 0 & 1 & 0 \\\\
>         0 & 1 & 0 & 0 \\\\
>0 0 0 & & & 1 > \end { matrice } \right ) >     \end{align}
> $$
> utilisé pour simuler l’opération intrinsèque [`SWAP`](xref:microsoft.quantum.intrinsic) .

|Transformation d’unité de mesure Pauli ||
|----------------------|------------------------|
|$ \otimes \boldone Z $ | $\boldone\otimes \boldone$|
|$ \otimes \boldone X $ | $ \otimes \boldone H $|
|$ \otimes \boldone Y $ | $ HS \dagger \otimes \boldone ^ $|
|$\boldone \otimes $ | $ \operatorname { échange } Z $|
|$\boldone \otimes $ | $ \otimes \boldone \operatorname { échange } X (H $ )|
|$\boldone \otimes $ | $ \dagger \otimes \boldone \operatorname { échange } Y $ (HS ^)|
|$Z \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } $|
|$X \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } (H \otimes \boldone ) $|
|$Y \otimes Z $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes \boldone ) $|
|$Z \otimes X $ | $ \operatorname { cnotin } \_ { 10 } ( \boldone \otimes H) $|
|$X \otimes X $ | $ \operatorname { cnotin } \_ { 10 } (h \otimes h) $|
|$Y \otimes X $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes H) $|
|$Z \otimes O $ | $ \operatorname { cnotin } \_ { 10 } ( \boldone \otimes HS ^ \dagger ) $|
|$X \otimes O $ | $ \operatorname { cnotin } \_ { 10 } (H \otimes HS ^ \dagger ) $|
|$Y \otimes O $ | $ \operatorname { cnotin } \_ { 10 } (HS ^ \dagger \otimes HS ^ \dagger ) $|

Ici, l' [`CNOT`](xref:microsoft.quantum.intrinsic.cnot) opération s’affiche pour la raison suivante.
Chaque mesure Pauli qui n’inclut pas la $ \boldone $ matrice est équivalente à une unité à $ z \otimes z $ par le raisonnement ci-dessus.
Le valeurs propres de $ z \otimes z $ dépend uniquement de la parité des qubits qui composent chaque vecteur de base de calcul, et les opérations non contrôlées servent à calculer cette parité et à la stocker dans le premier bit.
Une fois le premier bit mesuré, nous pouvons récupérer l’identité du demi-espace résultant, ce qui équivaut à mesurer l’opérateur Pauli.

Une remarque supplémentaire : s’il peut être tentant de supposer que la mesure $ z \otimes z $ est identique à la mesure séquentielle de $ z \otimes \mathbb { 1, } $ puis à $ \mathbb { 1 } \otimes z $ , cette hypothèse est fausse.
La raison est que la mesure $ z \otimes z $ projette l’État Quantum dans le $ eigenstate + 1 $ ou $ -1 $ de ces opérateurs.
La mesure de $ z \otimes \mathbb { 1 } $ , puis de $ \mathbb { 1 } \otimes Z $ projette le vecteur d’État Quantum tout d’abord sur un demi-espace de $ z \otimes \mathbb { 1 } $ , puis sur un demi-espace de $ \mathbb { 1 } \otimes z $ . Étant donné qu’il y a quatre vecteurs de base de calcul, l’exécution des deux mesures permet de réduire l’État à un quart d’espace et, par conséquent, de la réduire à un vecteur de calcul unique.

## <a name="correlations-between-qubits"></a>Corrélations entre qubits
Une autre façon d’examiner la mesure des produits tenseur des matrices Pauli, tels que $ x \otimes x $ ou $ z \otimes z, $ est que ces mesures vous permettent de consulter les informations stockées dans les corrélations entre les deux qubits.
$La mesure X \otimes \id $ vous permet de consulter les informations qui sont stockées localement dans le premier qubit.
Alors que les deux types de mesures sont tout aussi utiles dans Quantum Computing, le premier éclaire la puissance de quantum computing.
Il révèle que, dans Quantum Computing, les informations que vous souhaitez apprendre ne sont pas stockées dans un qubit unique mais plutôt stockées non localement dans toutes les qubits en même temps, et par conséquent uniquement en les examinant par une mesure conjointe (p. ex. $ z \otimes z $ ). ces informations deviennent manifestes.

Par exemple, dans la correction des erreurs, nous souhaitons souvent savoir quelle erreur s’est produite lors de l’apprentissage de l’état que nous tentons de protéger.
L' [exemple de code de retournement de bits](https://github.com/microsoft/Quantum/tree/main/samples/error-correction/bit-flip-code) montre un exemple de la façon dont vous pouvez effectuer cette opération à l’aide de mesures telles que $ z z et z \otimes \otimes \id $ $ \id \otimes \otimes z $ . < --TODO : remplacez ceci par un lien vers le navigateur Samples dès que l’exemple de code de retournement de bits est intégré. -->

Les opérateurs Pauli arbitraires tels que $ X \otimes Y \otimes Z \otimes \boldone $ peuvent également être mesurés.
Tous les produits tenseur des opérateurs Pauli n’ont que deux valeurs propres $ \pm 1 $ et les deux eigenspaces constituent des demi-espaces de l’ensemble de l’espace de vecteur.
Ils coïncident donc avec les exigences indiquées ci-dessus.

Dans Q# , ces mesures retournent $ j $ si la mesure produit un résultat dans le eigenspace du signe $ (-1) ^ j $ .
Avoir des mesures Pauli comme fonctionnalité intégrée dans Q# est utile, car la mesure de ces opérateurs nécessite des chaînes longues de transformations de base et non contrôlées pour décrire le $ portail U de diagonale $ nécessaire pour exprimer l’opération en tant que produit tenseur de $ Z $ et $ \id $ .
En étant en mesure de spécifier que vous souhaitez effectuer une de ces mesures prédéfinies, vous n’avez pas besoin de vous soucier de la façon de transformer votre base de manière à ce qu’une mesure de base de calcul fournisse les informations nécessaires.
Q# gère automatiquement toutes les transformations de base nécessaires.
Pour plus d’informations, consultez [`Measure`](xref:microsoft.quantum.intrinsic.measure) les [`MeasurePaulis`](xref:microsoft.quantum.measurement.measurepaulis) opérations et.

## <a name="the-no-cloning-theorem"></a>Le pas de clonage

Les informations de Quantum sont puissantes.
Cela nous permet de faire des choses étonnantes, telles que les chiffres de facteur de façon exponentielle plus rapide que les algorithmes classiques les plus connus, ou de simuler efficacement des systèmes d’électrons corrélés qui nécessitent un coût exponentiel pour une simulation précise.
Toutefois, il existe des limitations à la puissance de quantum computing.
L’une de ces limitations est donnée par le seuil de *non-clonage*.

Le nom du terme de non-clonage est avec justesse.
Il interdit le clonage d’États de Quantum génériques par un ordinateur Quantum.
La preuve du pas de l’un est remarquablement simple.
Bien qu’une preuve complète de l’qubits de non-clonage soit un peu trop technique pour notre discussion ici, la preuve dans le cas d’un auxiliaire supplémentaire se trouve dans notre étendue (les qubits auxiliaires sont qubits utilisés pour l’espace de travail pendant un calcul et sont facilement utilisés et gérés dans Q# , consultez [qubits empruntés](xref:microsoft.quantum.guide.qubits#borrowed-qubits)).

Pour un tel ordinateur Quantum, l’opération de clonage doit être décrite par une matrice d’unités.
Nous interdisent la mesure, car cela corromprait l’État Quantum que nous essayons de cloner.
Pour simuler l’opération de clonage, nous voulons que la matrice d’unités utilise la propriété qui $$
  U \ket { \psi } \ket { 0 } = \ket { \psi }\ket{\psi}
$$
pour n’importe quel état $ \ket { \psi } $ .
La propriété de linéarité de la multiplication de matrice implique alors que pour n’importe quel autre État Quantum $ \ket { \phi } $ ,

$$
\begin{align}
    U \left [ \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ] \ket { 0}
    &= \frac{ 1 } { \sqrt { 2 } } U \ket { \phi } \ket { 0}
      + \frac{1 } { \sqrt { 2 } } U \ket { \psi } \ket { 0 }\\\\
    &= \frac{ 1 } { \sqrt { 2 } } \left ( \ket { \phi } \ket { \phi }  +  \ket { \psi }\ket{\psi}
        \right) \\\\
    &\ne \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ) \otimes \left ( \frac { 1 } { \sqrt { 2 } } \left ( \ket { \phi } + \ket { \psi } \right ) \right ).
\end{align}
$$

Cela fournit l’intuition fondamentale derrière le principe de non-clonage : tout appareil qui copie un État Quantum inconnu doit provoquer des erreurs au moins dans certains États qu’il copie.
Tandis que l’hypothèse clé selon laquelle le cloner agit de manière linéaire sur l’état d’entrée peut être violée par l’ajout et la mesure des qubits auxiliaires, ces interactions fuient également des informations sur le système via les statistiques de mesure et empêchent le clonage exact dans de tels cas.
Pour obtenir une preuve plus complète du titre de non-clonage, consultez [pour plus d’informations](xref:microsoft.quantum.more-information).

Le point de vue de la non-clonage est important pour la compréhension qualitative de l’informatique Quantum, car si vous pouviez cloner des États quantiques de façon inonéreuse, vous bénéficiez d’une capacité proche magique d’apprendre à partir des États quantiques.
En effet, vous pourriez violer le principe d’incertitude vaunted de Heisenberg.
Vous pouvez également utiliser un Cloner optimal pour obtenir un échantillon unique à partir d’une distribution de Quantum complexe et découvrir tout ce que vous pourriez savoir sur cette distribution à partir d’un seul exemple.
Cela revient à retourner une pièce de monnaie et à observer des têtes, puis à dire à un ami sur le résultat de la réponse « Ah que la distribution de cette pièce de monnaie doit être de Bernoulli avec $ p = 0.512643 \ ldots $ ! »  Une telle instruction serait non sensée, car un peu d’informations (le résultat des têtes) ne peut pas fournir les nombreux éléments d’informations nécessaires pour encoder la distribution sans aucune information préalable substantielle.
De même, sans informations préalables, nous ne pouvons pas parfaitement cloner un État Quantum, de la même façon que nous ne pouvons pas préparer un ensemble de ces pièces, sans connaître $ p $ .

Les informations ne sont pas gratuites dans quantum computing.
Chaque qubit mesuré fournit un seul bit d’informations et le principe de non-clonage indique qu’il n’existe pas de porte dérobée pouvant être exploitée pour contourner le compromis fondamental entre les informations acquises sur le système et la perturbation invoquée.
