---
titre : qubit dans quantum computing Description : en savoir plus sur qubits, l’unité fondamentale des informations dans quantum computing.
Auteur : QuantumWriter UID : Microsoft. Quantum. concepts. qubit ms. Author : v-benbra ms. Date : 12/11/2017 ms. rubrique : Conceptual No-Loc :
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
# <a name="the-qubit"></a>Qubit

Tout comme bits est l’objet fondamental des informations dans l’informatique classique, [*qubits*](https://en.wikipedia.org/wiki/Qubit) (bits quantiques) est l’objet fondamental des informations dans quantum computing.  Pour comprendre cette correspondance, examinons l’exemple le plus simple : un qubit unique.

## <a name="representing-a-qubit"></a>Représentation d’un qubit

Si un bit, ou un chiffre binaire, peut avoir la valeur $ 0 $ ou $ 1 $ , un qubit peut avoir une valeur qui correspond à l’un ou l’autre ou à une superposition Quantum égale à $ 0 $ et $ 1 $ .

L’état d’un seul qubit peut être décrit par un vecteur de colonne à deux dimensions de la norme d’unité, autrement dit, l’amplitude du carré de ses entrées doit être additionnée à $ 1 $ . Ce vecteur, appelé vecteur d’État Quantum, contient toutes les informations nécessaires pour décrire le système Quantum qubit tout comme un bit unique contient toutes les informations nécessaires pour décrire l’état d’une variable binaire.

Tout vecteur de colonne à deux dimensions de nombres réels ou complexes avec $ la norme 1 $ représente un État Quantum possible détenu par un qubit. $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ Représente donc un État qubit si $ \alpha $ et $ \beta $ sont des nombres complexes qui répondent à $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .   Voici quelques exemples de vecteurs d’État Quantum valides représentant qubits.

$$\begin{bmatrix}1 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} , \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { 1 2 } { \sqrt { } } \end{bmatrix} , \begin{bmatrix} \frac { 1 2 } { \sqrt { } } \\\\ \frac { -1 } { \sqrt { 2 } } \end{bmatrix} , \text { et } \begin{bmatrix} \frac { 1 } { \sqrt { 2 } } \\\\ \frac { i } { \sqrt { 2 } } \end{bmatrix} .      $$

Les vecteurs d’État Quantum $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ et $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ prennent un rôle spécial. Ces deux vecteurs forment une base pour l’espace vectoriel qui décrit l’état de qubit. Cela signifie que tout vecteur d’état quantique peut être écrit sous la forme d’une somme de ces vecteurs de base. Plus précisément, le vecteur $ \begin{bmatrix} x \\\\ y \end{bmatrix} $ peut être écrit sous la forme $ x \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} + y \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Alors qu’une rotation de ces vecteurs ferait office de base parfaitement valide pour le qubit, nous choisissons d’en faire un privilège, en l’appelant comme *base de calcul*.

Nous prenons ces deux États Quantum pour correspondre aux deux États d’un bit classique, à savoir $ 0 $ et $ 1 $ . La Convention standard consiste à choisir

$$0 \equiv \begin{bmatrix} 1 \\\\  0 \end{bmatrix} , \qquad 1 \equiv \begin{bmatrix} 0 \\\\  1 \end{bmatrix} ,$$

Bien que le choix opposé puisse également être pris. Ainsi, en dehors du nombre infini de vecteurs d’État Quantum uniques possibles, seuls deux correspondent aux États des bits classiques ; ce n’est pas le cas de tous les autres États Quantum.

## <a name="measuring-a-qubit"></a>Mesure d’un qubit

Maintenant que nous savons comment représenter un qubit, nous pouvons obtenir des intuitions pour ce que ces États représentent en discutant du concept de [*mesure*](https://en.wikipedia.org/wiki/Measurement_in_quantum_mechanics). Une mesure correspond à l’idée informelle de « regarder » sur un qubit, qui réduit immédiatement l’État Quantum à l’un des deux États classiques $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ou $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Lorsqu’un qubit donné par le vecteur d’État Quantum $ \begin{bmatrix} \alpha \\\\ \beta \end{bmatrix} $ est mesuré, nous obtenons le résultat $ 0 $ avec la probabilité $ | \alpha | ^ 2 $ et le résultat $ 1 $ avec la probabilité $ | \beta | ^ 2 $ .   Au résultat $ 0 $ , le nouvel État du qubit est $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ; sur le résultat $ 1 $ son état est $ \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} $ . Notez que ces probabilités sont totalisées jusqu’à $ 1 en $ raison de la condition de normalisation $ | \alpha | ^ 2 + | \beta | ^ 2 = 1 $ .

Les propriétés de mesure signifient également que le signe global du vecteur d’État Quantum n’est pas pertinent. Le fait de nier un vecteur équivaut à une flèche $ \alpha \right \alpha $ et une $ \beta \right flèche \beta $ . Étant donné que la probabilité de la mesure $ 0 $ et $ 1 $ dépend de l’amplitude des termes, l’insertion de tels signes ne change pas les probabilités. Ces phases sont communément appelées [ `` « *phases globales*»](https://en.wikipedia.org/wiki/Phase_factor) et, plus généralement, elles peuvent être de la forme $ e ^ { i \phi } $ plutôt que simplement $ \pm 1 $ .

Une dernière propriété importante de la mesure est qu’elle n’endommage pas nécessairement tous les vecteurs d’état de Quantum. Si nous commençons par un qubit dans l’état $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ , qui correspond à l’État classique $ 0 $ , la mesure de cet État produira toujours le résultat $ 0 $ et laissait l’État Quantum inchangé. Dans ce sens, si nous avons uniquement des bits classiques (c’est-à-dire des qubits qui sont $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} $ ou $ \begin{bmatrix} 0 \\\\ 1), \end{bmatrix} $ la mesure n’endommage pas le système. Cela signifie que nous pouvons répliquer les données classiques et les manipuler sur un ordinateur Quantum comme un ordinateur classique. Toutefois, la capacité à stocker des informations dans les deux États à la fois est celle qui élève l’informatique Quantum au-delà de ce qui est possible de manière classique et prive les ordinateurs Quantum de la capacité à copier des données de quantum de manière non discriminatoire. Consultez également le titre de [non-clonage](https://en.wikipedia.org/wiki/No-cloning_theorem).

## <a name="visualizing-qubits-and-transformations-using-the-bloch-sphere"></a>Visualisation des qubits et des transformations à l’aide de la sphère Bloch

Qubits peut également être représenté en $ 3 $ D à l’aide de la représentation de la [*sphère Bloch*](https://en.wikipedia.org/wiki/Bloch_sphere) .  La sphère Bloch permet de décrire un État Quantum à qubit unique (qui est un vecteur complexe à deux dimensions) sous la forme d’un vecteur à valeurs réelles en trois dimensions.  C’est important, car cela nous permet de visualiser les États qubit et de développer ainsi un raisonnement qui peut être très utile pour comprendre les États multiqubits (où la représentation de la sphère Bloch s’arrête).  La sphère Bloch peut être visualisée comme suit :

<!--- ![](.\media\bloch.svg) { largeur = 50%} --->
![Sphère Bloch](~/media/concepts_bloch.png)

Les flèches de ce diagramme affichent la direction dans laquelle le vecteur d’État Quantum pointe et chaque transformation de la flèche peut être considérée comme une rotation autour de l’un des axes Cardinal.
Tout en pensant à un calcul de Quantum comme une séquence de rotations est un outil d’intuition puissant, il est difficile d’utiliser cette intuition pour concevoir et décrire des algorithmes. Q# atténue ce problème en fournissant un langage pour décrire de telles rotations.

## <a name="single-qubit-operations"></a>Opérations de Single-Qubit

Les ordinateurs quantiques traitent les données en appliquant un ensemble universel de portes de Quantum qui peuvent émuler n’importe quelle rotation du vecteur d’État Quantum.
Cette notion d’universalité est similaire à la notion d’universalité pour le calcul traditionnel (c’est-à-dire classique) où un ensemble de portes est considéré comme universel si chaque transformation des bits d’entrée peut être effectuée à l’aide d’un circuit de longueur finie.
Dans Quantum Computing, les transformations valides que nous sommes autorisés à effectuer sur un qubit sont des transformations et des mesures unitaires.
L' *opération joint* ou le TransType de conjugué complexe revêt une importance capitale pour le quantum computing car il est nécessaire d’inverser les transformations de Quantum.

Il n’y a que quatre fonctions qui mappent un bit à un bit sur un ordinateur classique. En revanche, il existe un nombre infini de transformations unitaires sur un seul qubit sur un ordinateur quantique. Par conséquent, aucun jeu fini d’opérations quantiques primitives, nommé [*portes*](https://en.wikipedia.org/wiki/Quantum_logic_gate), ne peut répliquer exactement l’ensemble infini de transformations unitaires autorisées dans quantum computing. Cela signifie, contrairement à l’informatique classique, qu’il est impossible pour un ordinateur quantique d’implémenter chaque programme Quantum possible avec un nombre fini de portes. Ainsi, les ordinateurs quantiques ne peuvent pas être universels dans le même sens que les ordinateurs classiques. Par conséquent, lorsque nous disons qu’un ensemble de portes est *universel* pour le quantum computing, nous avons en fait un peu plus faible que cela signifie l’informatique classique.
Pour l’universalité, nous exigeons qu’un ordinateur quantique se *rapproche* uniquement de chaque matrice unitaire dans le cas d’une erreur finie à l’aide d’une séquence de porte de longueur finie.
En d’autres termes, un ensemble de portes est un ensemble de portes universelles si une transformation unitaire peut être approximativement écrite en tant que produit de portes à partir de cet ensemble. Nous avons besoin que pour toute erreur liée, il existe des portes $ g_ { 1 } , g_ { 2 } , \ldots, G_N $ à partir de l’ensemble de portes,

$$
G_N G_ { N-1 } \cdots G_2 G_1 \approx U. $$

Notez que, étant donné que la Convention pour la multiplication de matrice est de multiplier de droite à gauche la première opération de porte de cette séquence, $ G_N $ , est en fait le dernier appliqué au vecteur d’État Quantum. Plus formellement, nous disons qu’un tel ensemble de portes est universel si pour chaque tolérance d’erreur $ \epsilon > 0 $ il existe $ G_1, \ldots, G_N de $ telle sorte que la distance entre $ G_N \ldots G_1 $ et $ U $ est au plus $ \epsilon $ . Dans l’idéal, la valeur de $ N $ nécessaire pour atteindre cette distance de \epsilon doit mettre à l' $ échelle le $ poly-logarithmique avec $ 1/\ Epsilon $ .

À quoi ressemble un tel ensemble de portes universelles ?  Le plus simple de ces portes universelles pour les portes à qubit unique est constitué uniquement de deux portes : la porte Hadarmard $ $ et la porte appelée $ T $ -Gate (également appelée « $ porte-pi/8 » $ ) :

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ & -1 \end{bmatrix} , \qquad T = \begin{bmatrix} 1 & 0 \\\\ 0 & e ^ { i \ pi/4 } \end{bmatrix} .
$$

Toutefois, pour des raisons pratiques liées à la correction des erreurs Quantum, il peut être plus pratique de prendre en compte un plus grand ensemble de portes, à savoir un ensemble qui peut être généré à l’aide de $ H $ et $ T $ . Nous pouvons classer les portes de Quantum en deux catégories : Clifford Gates et le $ T $ -Gate.
Cette sous-division est utile, car dans de nombreux schémas de correction des erreurs Quantum, les portes Clifford sont faciles à implémenter, ce qui signifie qu’elles nécessitent très peu de ressources en termes d’opérations et de qubits pour implémenter la tolérance de panne, tandis que les portes non Clifford sont coûteuses en cas de demande de tolérance de panne. L’ensemble standard de portes Clifford à qubit unique, [inclus par défaut dans Q# ](xref:microsoft.quantum.libraries.standard.prelude), inclut

$$
H = \frac { 1 } { \sqrt { 2 } } \begin{bmatrix} 1 & 1 \\\\ & -1 \end{bmatrix} , \qquad S = \begin{bmatrix} 1 & 0 \\\\ 0 & i \end{bmatrix} = T ^ 2, \qquad X = \begin{bmatrix} 0 & 1 \\\\ 1 & 0 \end{bmatrix} = HT ^ 4H,$$

$$
Y = \begin{bmatrix} 0 & -i \\\\ & 0 \end{bmatrix} = T ^ 2HT ^ 4 HT ^ 6, \qquad Z = \begin{bmatrix} 1 & 0 \\\\ 0 & -1 \end{bmatrix} = T ^ 4.
$$

Ici, les opérations $ X $ , $ Y $ et $ Z $ sont utilisées particulièrement fréquemment et sont appelées [*opérateurs Pauli*](https://en.wikipedia.org/wiki/Pauli_matrices) après leur Creator Wolfgang Pauli.
Avec la porte non Clifford (le $ T $ -Gate), ces opérations peuvent être composées pour rapprocher toute transformation unitaire sur un qubit unique.

Pour plus d’informations sur ces opérations, sur les représentations et les implémentations de la sphère Bloch Q# , consultez [opérations et fonctions intrinsèques](xref:microsoft.quantum.libraries.standard.prelude#intrinsic-operations-and-functions).

À titre d’exemple de la façon dont les transformations unitaires peuvent être créées à partir de ces primitives, les trois transformations illustrées dans les Blochs ci-dessus correspondent à la séquence de la porte $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \mapsto HZH \begin{bmatrix} 1 \\\\ 0 0 \end{bmatrix} = \begin{bmatrix} \\\\ 1 \end{bmatrix} $ .

Tandis que le précédent constitue les portes primitives les plus populaires pour décrire les opérations sur le niveau logique de la pile (imaginez le niveau logique comme le niveau de l’algorithme Quantum), il est souvent pratique de prendre en compte moins d’opérations de base au niveau algorithmique, par exemple les opérations plus proches du niveau de description de la fonction. Heureusement, Q# possède également des méthodes permettant d’implémenter des unités de niveau supérieur, qui à leur tour permettent d’implémenter des algorithmes de haut niveau sans décomposer explicitement tous les éléments en Clifford et en $ T $ -Gates.

La seule primitive la plus simple est la rotation qubit unique. Trois rotations à qubit unique sont généralement considérées comme : $ R_x $ , $ R_y $ et $ R_z $ . Pour visualiser l’action de la R_x de rotation $ (\Theta) $ , par exemple, imaginez que vous pointez votre curseur vers la droite le long de la direction de l' $ $ axe x de la sphère Bloch et que vous faites pivoter le vecteur avec votre main à l’aide d’un angle de $ \ Theta/2 $ radians. Ce facteur confus de $ 2 $ vient du fait que les vecteurs orthogonaux sont $ en fait 180 ^ \circ $ lorsqu’ils sont tracés sur la sphère Bloch, mais qu’ils sont en fait de $ 90 ^ \circ $ degrés séparés géométriques. Les matrices unitaires correspondantes sont les suivantes :

\begin{align *} 
 & R_z (\Theta) = e ^ { -i\theta z/2 } = \begin{bmatrix} e ^ { -i \ Theta/2 } & 0 \\\\ 0 & e ^ { i \ Theta/2 } \end{bmatrix} , \\\\ 
 & R_x (\Theta) = e ^ { -i\theta x/2 } = HR_z (\Theta) H = \begin{bmatrix} \cos (\ Theta/2) & -i\sin (\ Theta/2) \\\\ -i\sin (\ Theta/2) & \cos (\ Theta/2) \end{bmatrix} , \\\\ 
 & R_y (\Theta) = e ^ { -i\theta y/2 } = SHR_z (\Theta) HS ^ \dagger = \begin{bmatrix} \cos (\ Theta/2) & -\sin (\ Theta/2) \\\\ \sin (\ Theta/2) & \cos (\ Theta \end{bmatrix} \end { /2). aligner*}

Tout comme les trois rotations peuvent être combinées pour effectuer une rotation arbitraire dans trois dimensions, il peut être vu à partir de la représentation Bloch Sphere que toute matrice unitaire peut être écrite sous la forme d’une séquence de trois rotations également. Plus précisément, pour chaque matrice d’unités, $ $ ,, $ \alpha \beta \gamma \delta $ par exemple, $ u = e ^ { i \alpha } R_x ( \beta ) R_z () \gamma R_x () \delta $ . Ainsi, $ R_z (\Theta) $ et $ H $ forment également un ensemble de portes universelles bien qu’il ne s’agisse pas d’un jeu discret, car $ \Theta $ peut prendre n’importe quelle valeur. Pour cette raison, et en raison des applications dans la simulation quantique, ces portes continues sont cruciales pour le calcul quantique, en particulier au niveau de la conception de l’algorithme Quantum. Pour obtenir une implémentation matérielle tolérante aux pannes, elles seront finalement compilées en séquences de grille discrètes qui se rapprochent de ces rotations.
