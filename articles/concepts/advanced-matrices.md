---
title : description des concepts avancés de la matrice : en savoir plus sur les fonctionnalités exponentielles de vecteurs propres, de valeurs propres et de matrice, les outils fondamentaux utilisés pour décrire et simuler des algorithmes Quantum.
Auteur : QuantumWriter UID : Microsoft. Quantum. concepts. Matrix-Advanced ms. Auteur : nawiebe@microsoft.com ms. Date : 12/11/2017 ms. topic : article No-Loc :
- "Q#"
- "$$v"
- "$$"
- "$$"
- "$"
- "$"
- "$"
- "$$"
- "$$$"
- "$$$"
- "$$$"
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
# <a name="advanced-matrix-concepts"></a>Concepts avancés de la matrice #

Nous étendons maintenant notre manipulation de matrices à [*valeurs propres, vecteurs propres*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) et [*exponentiels*](https://en.wikipedia.org/wiki/Matrix_exponential) , qui constituent un ensemble fondamental d’outils dont nous avons besoin pour décrire et implémenter des algorithmes Quantum.

## <a name="eigenvalues-and-eigenvectors"></a>Valeurs propres et vecteurs propres ##

Supposons $ que M est $ une matrice carrée et $ $ que v soit un vecteur qui n’est pas le vecteur de zéros tous (c’est-à-dire, le vecteur avec toutes les entrées égales à $ 0 $ ).

Nous disons que $ v $ est un [*extraction*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) de $ M $ si $ MV = CV $ pour un nombre $ c $ . Nous disons que $ c $ est le [*eigenvalue*](https://en.wikipedia.org/wiki/Eigenvalues_and_eigenvectors) correspondant à extraction $ v $ . En général, une matrice $ M $ peut transformer un vecteur en un autre vecteur, mais un extraction est spécial, car il reste inchangé, sauf s’il est multiplié par un nombre. Notez que si $ v $ est un extraction avec eigenvalue $ c $ , $ l’AV $ est également un extraction (pour toute valeur différente $ de zéro $ ) avec le même eigenvalue.

Par exemple, pour la matrice d’identité, chaque vecteur $ v $ est un extraction avec eigenvalue $ 1 $ .

En guise d’autre exemple, considérez une [*matrice diagonale*](https://en.wikipedia.org/wiki/Diagonal_matrix) $ D $ qui n’a que des entrées autres que zéro sur la diagonale :

$$
\begin{bmatrix}
d_1 & 0 0 0 & d_2 0 0 0 \\\\ & & \\\\ & & D_3 \end{bmatrix} .
$$

Les vecteurs

$$\begin{bmatrix}1 \\\\ 0 \\\\ 0 \end{bmatrix} , \begin{bmatrix} 0 \\\\ 1 \\\\ 0 \end{bmatrix} et \begin{bmatrix} 0 \\\\ 0 \\\\ 1\end{bmatrix}$$

sont vecteurs propres de cette matrice avec valeurs propres $ d_1 $ , $ d_2 $ et $ D_3 $ , respectivement. Si $ d_1 $ , $ d_2 $ et $ D_3 $ sont des nombres distincts, ces vecteurs (et leurs multiples) sont les seuls vecteurs propres de la matrice $ d $ . En général, pour une matrice diagonale, il est facile de lire les valeurs propres et les vecteurs propres. Les valeurs propres sont tous des nombres apparaissant sur la diagonale, et leurs vecteurs propres respectifs sont les vecteurs d’unité avec une entrée égale à $ 1 $ et les entrées restantes égales à $ 0 $ .

Notez dans l’exemple ci-dessus que le vecteurs propres de $ D $ constitue une base pour les $ $ vecteurs à trois dimensions. Une base est un ensemble de vecteurs, de sorte que tout vecteur peut être écrit comme une combinaison linéaire de ces vecteurs. Plus explicitement, $ V_1 $ , $ V_2 $ et $ V_3 $ forment une base si un vecteur $ v $ peut être écrit sous la forme $ v = A_1 v_1 + a_2 V_2 + A_3 V_3 $ pour certains nombres $ A_1 $ , $ a_2 $ et $ A_3 $ .

Rappelez-vous qu’une matrice Hermitian (également appelée autojoint) est une matrice carrée complexe égale à sa propre transposer un conjugué complexe, tandis qu’une matrice d’unités est une matrice carrée complexe dont l’inverse est égal à sa transforme de conjuguée voisine ou complexe.
Pour les matrices Hermitian et Unit, qui sont essentiellement les seules matrices rencontrées dans Quantum Computing, il existe un résultat général connu sous le nom d’un type d’unité de commande [*spectrale*](https://en.wikipedia.org/wiki/Spectral_theorem), qui déclare les éléments suivants : pour une matrice de Hermitian ou d’unité $ $ , il existe un $ u unitaire $ tel que $ M = u ^ \dagger D u $ pour une matrice diagonale $ D $ . En outre, les entrées diagonales de $ D $ seront les valeurs propres de $ M $ .

Nous savons déjà comment calculer le valeurs propres et le vecteurs propres d’une matrice diagonale $ D $ . À l’aide de cette aide, nous savons que si $ v $ est un extraction de $ D $ avec eigenvalue $ c $ , par exemple $ DV = CV $ , $ U ^ \dagger v sera $ un extraction de $ M $ avec eigenvalue $ c $ . Cela est dû au fait que

$$M (U ^ \dagger v) = u ^ \dagger d u (u ^ \dagger v) = U ^ \dagger d (u u ^ \dagger ) v = u ^ \dagger D v = c u ^ \dagger v.$$

## <a name="matrix-exponentials"></a>Exponentiels de la matrice
Une [*matrice exponentielle*](https://en.wikipedia.org/wiki/Matrix_exponential) peut également être définie en analogie exacte avec la fonction exponentielle.  La valeur exponentielle de la matrice $ a $ peut être exprimée sous la forme

$$
e ^ A = \boldone + a + \frac { a ^ 2 } { 2 ! } + \frac { Un ^ 3 } { 3 !}+\cdots
$$

Cela est important, car l’évolution du temps de Quantum mécanique est décrite par une matrice d’unités au format $ e ^ { IB } $ pour la matrice Hermitian $ B $ .  C’est la raison pour laquelle l’exécution de la fonction exponentiels de matrice est une partie fondamentale de l’informatique Quantum et, en tant que telles, Q# offre des routines intrinsèques pour décrire ces opérations.
Il existe de nombreuses façons de calculer un exponentiel de matrice sur un ordinateur classique, et en général, une approximation approximative d’un tel exponentiel est chargée avec les risques.  Consultez [*Cleve mole et Charles Van Loan. « Dix-neuf façons douteuse de calculer l’exponentiel d’une matrice. » SIAM révision 20,4 (1978) : 801-836*](https://doi.org/10.1137/S00361445024180) pour plus d’informations sur les défis impliqués.

Le moyen le plus simple de comprendre comment calculer l’exponentiel d’une matrice consiste à utiliser les valeurs propres et les vecteurs propres de cette matrice.  Plus précisément, le point de vue spectral évoqué ci-dessus indique que, pour chaque Hermitian ou matrice unitaire $ a $ , il existe une matrice unitaire $ u $ et une matrice diagonale $ D $ telle qu' $ un u = ^ \dagger D u $ .  En raison des propriétés de unitarity, nous disposons d' $ un ^ 2 = u ^ \dagger d ^ 2 u $ et de la même façon pour toute alimentation $ p $ $ A ^ p = u ^ \dagger d ^ p u $ .  Si nous le remplaçons par la définition d’opérateur de l’opérateur exponentiel, nous obtenons :

$$
e ^ A = U ^ \dagger \left ( \boldone + d + \frac { d ^ 2 } { 2 ! } + \cdots \right ) U = u ^ \dagger \begin{bmatrix} \exp (d_ { 11 } ) & 0 & \cdots & 0 \\\\ 0 & \exp (d_ { 22 } ) & \cdots & 0 \\\\ \vdots & \vdots & \ddots & \vdots \\\\ 0 & 0 & \cdots & \exp (d_ { nn } ) \end{bmatrix} U.$$

En d’autres termes, si vous transformez vers le eigenbasis de la matrice $ A, $ le calcul de la valeur exponentielle de la matrice est équivalent au calcul de la valeur exponentielle ordinaire du valeurs propres de la matrice.  Dans la mesure où de nombreuses opérations dans quantum computing impliquent l’exécution de matrices exponentielles, cette astuce de transformation en eigenbasis d’une matrice pour simplifier l’exécution de l’opérateur exponentiel apparaît fréquemment et constitue la base de nombreux algorithmes Quantum tels que les méthodes de simulation de quantum de type Trotter – Suzuki décrites plus loin dans ce guide.

Une autre propriété utile est si $ B est à la $ fois unitéal et Hermitian, C.-à-d. $ b = b ^ { -1 } = b ^ \dagger $ Then $ b ^ 2 = \boldone $ . En appliquant cette règle à l’expansion ci-dessus de la matrice exponentielle et en regroupant les $ \boldone $ $ termes et B $ ensemble, vous pouvez constater que pour toute valeur réelle $ x $ l’identité

$$e ^ { iBx } = \boldone \cos (x) + iB\sin (x)$$


comprend. Cette astuce est particulièrement utile, car elle permet de tenir compte des actions exponentielles de la matrice, même si la dimension de $ b $ est exponentiellement grande, pour le cas particulier quand $ b est à la $ fois uniténelle et Hermitian.
