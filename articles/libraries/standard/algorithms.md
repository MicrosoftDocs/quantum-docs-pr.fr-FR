---
title: 'Algorithmes Quantum dans Q #'
description: Découvrez les algorithmes de quantum computing fondamentaux, y compris l’amplification d’amplitude, les transformations de Fourier, les ajouts de Draper et de Beauregard et l’estimation de phase.
author: QuantumWriter
ms.author: martinro@microsoft.com
ms.date: 12/11/2017
ms.topic: article
uid: microsoft.quantum.libraries.standard.algorithms
ms.openlocfilehash: 8b8a9019e8bc419f42b0c6f7558354d19a157917
ms.sourcegitcommit: d61b388651351e5abd4bfe7a672e88b84a6697f8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2020
ms.locfileid: "79402848"
---
# <a name="quantum-algorithms"></a>Algorithmes Quantum #

## <a name="amplitude-amplification"></a>Amplification d’amplitude ##

L' *amplification d’amplitude* est l’un des outils fondamentaux de quantum computing. Il s’agit de l’idée fondamentale qui repose sur la recherche de Grover, l’estimation de l’amplitude et de nombreux algorithmes Quantum Machine Learning.  Il existe de nombreuses variantes, et dans Q #, nous fournissons une version générale basée sur l’amplification de l’amplitude oublie avec des réflexions partielles pour permettre le plus grand éventail d’applications.

L’idée centrale derrière l’amplification d’amplitude consiste à amplifier la probabilité qu’un résultat escompté se produise en effectuant une séquence de réflexions.  Ces réflexions font pivoter l’état initial vers un État cible souhaité, souvent appelé état marqué.  Plus précisément, si la probabilité de la mesure de l’état initial dans un État marqué est $ \sin ^ 2 (\Theta) $, après l’application de l’amplification d’amplitude $m $ fois la probabilité de réussite devient $ \sin ^ 2 ((2m + 1) \Theta) $.  Cela signifie que si $ \Theta = \ pi/[2 (2n + 1)] $ pour une valeur de $n $ Then amplification d’amplitude est capable d’augmenter la probabilité de réussite à $100\\% $ après $n $ itérations d’amplification d’amplitude.  Dans la mesure où $ \Theta = \sin ^{-1}(\sqrt{\Pr (Success)}) $, cela signifie que le nombre d’itérations nécessaires pour obtenir un succès déterministe est augmentera inférieur au nombre attendu requis pour trouver un État marqué non déterministe à l’aide d’un échantillonnage aléatoire.

Chaque itération de l’amplification d’amplitude requiert la spécification de deux opérateurs de réflexion. Plus précisément, si $Q $ est l’itération d’amplification d’amplitude et $P _0 $ est un opérateur de projecteur dans le sous-espace initial et $P 1 _ 1 est le projecteur sur le sous-espace marqué, $Q =-(\boldone-2P_0) (\boldone-2P_1) $.  Rappelez-vous qu’un projecteur est un opérateur Hermitian dont les valeurs propres $ + $1 et $0 $ et, par conséquent, $ (\boldone-2P_0) $ est unitaire parce qu’il comporte des valeurs propres racines d’Unity (dans ce cas, $ \pm $1). Par exemple, considérez le cas de la recherche de Grover avec l’état initial $H ^ {\otimes n} \ket{0}$ et l’État marqué $ \ket{m} $, $P _0 = H ^ {\otimes n} \ket{0}\bra{0}H ^ {\otimes n} $ et $P _ 1 = \ket{m}\bra{m} $.  Dans la plupart des applications d’amplification d’amplitude $P _0 $ sera un projecteur dans un état initial signifiant que $P _0 = \boldone-2 \ Ket {\ PSI} \ Bra {\ PSI} $ pour un vecteur $ \ket{\Psi} $; Toutefois, pour oublie amplitude amplication $P _0 $ se projette généralement sur de nombreux États quantiques (c’est-à-dire, la multiplicité de la eigenvalue $ + $1 de $P _0 $ est supérieure à $1 $).

La logique derrière l’amplification d’amplitude suit directement à partir de la vecteurs-Decomposition de $Q $.  En particulier, le vecteurs propres de $Q $ pour lequel l’état initial a une prise en charge différente de zéro peut s’afficher comme des combinaisons linéaires du vecteurs propres $ + $1 de $P _0 $ et $P _ 1 $.  Plus précisément, l’état initial de l’amplification d’amplitude (en supposant qu’il s’agit d’un extraction $ + $1 de $P _0 $) peut être écrit sous la forme $ $ \ket{\Psi} = \frac{-i}{\sqrt{2}} \left (e ^ {i\theta} \ Ket {\ psi_ +} + e ^ {-i\theta} \ Ket {\ psi_-} \right), $ $ where $ \ket{\ psi_ \pm} $ sont vecteurs propres de $Q $ avec valeurs propres $e ^ {\pm 2i \ thêta} $ et ne prennent en charge que sur le $ + $1 vecteurs propres de $P _0 $ et $P 1 1 $.  Le fait que les valeurs propres sont $e ^ {\pm i \Theta} $ signifie que l’opérateur $Q $ effectue une rotation dans un sous-espace à deux dimensions spécifié par les deux projecteurs et l’état initial où l’angle de rotation est de $2 \ Theta $.  C’est pourquoi, après $m $ iterations de $Q $, la probabilité de réussite est de $ \sin ^ 2 ([2m + 1] \Theta) $.

Une autre propriété utile est que le eigenvalue $ \Theta $ est directement lié à la probabilité que l’état initial soit marqué (dans le cas où $P _0 $ est un projecteur sur uniquement l’état initial).  Étant donné que le eigenphases de $Q $ est égal à $2 \ Theta = 2 \ Sin ^{-1}(réussite)}), il suit ensuite que si nous appliquons l’estimation de phase à $Q $, nous pouvons apprendre la probabilité de réussite pour une procédure de Quantum unitaire.  Cela est utile, car il nécessite que augmentera moins d’applications de la procédure Quantum pour apprendre la probabilité de réussite que cela serait autrement nécessaire.

Q # introduit l’amplification d’amplitude comme une spécialisation de l’amplification de l’amplitude oublie.  L’amplification oublie amplitude gagne ce moniker car le projecteur sur le eigenspace initial n’a pas besoin d’être un projecteur à l’état initial.  Dans ce sens, le protocole est oublie à l’état initial.  L’application clé de l’amplification de l’amplitude oublie est dans certaines *combinaisons linéaires de méthodes de simulation d’unités de* la même manière, où l’état initial est inconnu, mais qui est associé à un registre Ancilla dans le protocole de simulation.  Si ce registre Ancilla doit être mesuré comme une valeur fixe, par exemple, $0 $, ces méthodes de simulation appliquent la transformation d’unité souhaitée au qubits restant (appelé Registre système).  Toutefois, tous les autres résultats de mesure provoquent une défaillance.  L’amplification d’amplitude oublie permet de renforcer la probabilité de réussite de cette mesure à $100\\% $ en utilisant le raisonnement ci-dessus.  En outre, l’amplification d’amplitude ordinaire correspond au cas où le registre système est vide.  C’est pourquoi Q # utilise oublie amplitude amplification comme sous-routine d’amplification d’amplitude fondamentale.

La routine générale (`AmpAmpObliviousByReflectionPhases`) a deux registres que nous appelons `ancillaRegister` et `systemRegister`. Il accepte également deux Oracle pour les réflexions nécessaires. Le `ReflectionOracle` agit uniquement sur le `ancillaRegister`, tandis que le `ObliviousOracle` agit conjointement sur les deux registres. L’entrée à `ancillaRegister` doit être initialisée à-1 eigenstate du premier opérateur de réflexion $ \boldone-2P_1 $.

En règle générale, Oracle prépare l’État dans la base de calcul $ \ket{0...0} $. Dans notre implémentation, le `ancillaRegister` est constitué d’un qubit (`flagQubit`) qui contrôle l' `stateOracle` et le reste du ancillas souhaité. Le `stateOracle` est appliqué lorsque la `flagQubit` est $ \ket{1}$.

Il est également possible de fournir des `StateOracle` Oracle et des `ObliviousOracle` au lieu de réflexions via un appel à `AmpAmpObliviousByOraclePhases`.

Comme nous l’avons vu précédemment, l’amplification d’amplitude traditionnelle n’est qu’un cas particulier de ces routines où `ObliviousOracle` est l’opérateur d’identité et qu’il n’y a pas de qubits système (autrement dit, `systemRegister` est vide). Si vous souhaitez obtenir des phases pour les réflexions partielles (par exemple, pour la recherche Grover), la fonction `AmpAmpPhasesStandard` est disponible. Reportez-vous à `DatabaseSearch.qs` pour obtenir un exemple d’implémentation de l’algorithme de Grover.

Nous associons les phases de rotation qubit aux phases de l’opérateur de réflexion, comme décrit dans le document de [G.H. Low, I. L. Chuang](https://arxiv.org/abs/1707.05391). Les phases à virgule fixe utilisées sont détaillées dans [Yoder, Low et Chuang](https://arxiv.org/abs/1409.3305) , ainsi que les phases dans [Low, Yoder et Chuang](https://arxiv.org/abs/1603.03996).

Pour l’arrière-plan, vous pouvez commencer à partir de l’amplification de l' [amplitude standard](https://arxiv.org/abs/quant-ph/0005055) , puis passer à une introduction à l’amplification de l' [amplitude oublie](https://arxiv.org/abs/1312.1414) et enfin aux généralisations présentées dans [Low et Chuang](https://arxiv.org/abs/1610.06546). Une présentation intéressante de la totalité de cette zone (par opposition à la simulation de Hamilton) a été fournie par [Dominic Berry](http://www.dominicberry.org/presentations/Durban.pdf).

## <a name="quantum-fourier-transform"></a>Transformation de Fourier quantique ##

La transformation de Fourier est un outil fondamental de l’analyse classique et est tout aussi importante pour les calculs Quantum.
En outre, l’efficacité de la *transformation de Fourier quantique* (QFT) dépasse ce qui est possible sur une machine classique, ce qui en fait un des premiers outils de choix lors de la conception d’un algorithme Quantum.

En guise de généralisation approximative de la QFT, nous fournissons l’opération <xref:microsoft.quantum.canon.approximateqft> qui permet d’effectuer d’autres optimisations en affinant les rotations qui ne sont pas strictement nécessaires pour la précision algorithmique souhaitée.
Le QFT approximatif requiert l’opération dyadic $Z $-rotation <xref:microsoft.quantum.intrinsic.rfrac> ainsi que l’opération <xref:microsoft.quantum.intrinsic.h>.
L’entrée et la sortie sont supposées être encodées au format d’encodage Big endian---autrement dit, le qubit avec l’index `0` est encodé dans le bit le plus à gauche (le plus élevé) de la représentation d’entier binaire.
Cela s’aligne avec la [notation Ket](xref:microsoft.quantum.concepts.dirac), dans la mesure où un registre de trois qubits à l’État $ \ket{100}$ correspond à $q _0 $ se trouve dans l’État $ \ket{1}$, tandis que $q _ 1 $ et $q _2 $ sont tous deux dans l’État $ \ket{0}$.
Le paramètre approximatif $a $ détermine le niveau de nettoyage des $Z $-rotations, c’est-à-dire $a \Dans [0.. n] $.
Dans ce cas, tous les $Z $-rotations $2 \ pi/2 ^ k $ où $k > un $ sont supprimés du circuit QFT.
Il est connu que pour $k \ge \ log_2 (n) + \ log_2 (1/\epsilon) + $3. Il est possible de lier $\\| \operatorname{QFT}-\operatorname{AQFT} \\| < \epsilon $.
Ici $\\| \cdot\\| $ est la norme d’opérateur qui, dans ce cas, correspond à la racine carrée de la plus grande [eigenvalue](xref:microsoft.quantum.concepts.matrix-advanced) de $ (\Operatorname{QFT}-\operatorname{AQFT}) (\Operatorname{QFT}-\operatorname{AQFT}) ^ \dagger $.

## <a name="arithmetic"></a>Arithmétique ##

Tout comme l’arithmétique joue un rôle central dans l’informatique classique, elle est également indispensable dans quantum computing.  Les algorithmes tels que l’algorithme de factorisation de Shori, les méthodes de simulation quantique et de nombreux algorithmes Oracular s’appuient sur des opérations arithmétiques cohérentes.  La plupart des approches de la génération arithmétique sur les circuits d’Adder quantique.  L’Adder le plus simple accepte une entrée classique $b $ et ajoute la valeur à un État Quantum contenant un entier $ \ket{a} $.  Mathématiquement, l’Adder (que nous désignerons $ \operatorname{Add} (b) $ pour l’entrée classique $b $) a la propriété qui

$ $ \operatorname{Add} (b) \ket{a} = \ket{a + b}.
$ $ Ce circuit d’Adder de base est plus un incrémenteur qu’un Adder.
Il peut être converti en un Adder qui a deux entrées Quantum via $ $ \operatorname{Add}\ket{a}\ket{b} = \ket{a}\ket{a + b}, $ $ à l’aide d' $n les applications contrôlées par les & de la forme \begin{align} \operatorname{Add} \ket{a} \ket{b} = \Lambda\_{a\_0} \left (\operatorname{Add} (1) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (4) \right) \cdots \Lambda\_{a\_{n-1}} \left (\ operatorName {Add} ({{n-1}}) \right) \ket{a}\ket{b} \\\\ & = \ket{a} \ket{b + a}, \end{align} pour $n entiers $ bits $a $ et $b $ et addition modulo $2 ^ n $.  Souvenez-vous que la notation $ \Lambda\_x (A) $ fait référence, pour toute opération $A $, à la version contrôlée de cette opération avec le contrôle $x $ As qubit.

De même, une multiplication contrôlée de manière classique (une forme modulaire de qui est essentielle pour l’algorithme de factorisation de Shori) peut être effectuée à l’aide d’une série similaire d’ajouts contrôlés : \begin{align} \operatorname{Mult} (a) \ket{x}\ket{b} & = \Lambda\_{x\_0} \left (\operatorname{Add} (2 ^ 0 a) \right) \Lambda\_{a\_1} \left (\operatorname{Add} (2 ^ 1a) \right) \Lambda\_{a\_2} \left (\operatorname{Add} (2 ^ 2 a) \right \cdots\_{x\_{ n-1}} \left (\operatorname{Add} ({2 ^ {n-1}} a) \right) \ket{x}\ket{b} \\\\ & = \ket{x}\ket{b + ax}.
\end{align} il existe une subtilité avec multiplication sur les ordinateurs quantiques que vous pouvez remarquer à partir de la définition de $ \operatorname{Mult} $ ci-dessus.  Contrairement à l’addition, la version Quantum de ce circuit stocke le produit des entrées dans un registre accessoire plutôt que dans le registre d’entrée.  Dans cet exemple, le Registre est initialisé avec la valeur $b $, mais il commence généralement à contenir la valeur zéro.  Cela est nécessaire dans, car en général, il n’y a pas d’inverse multiplicatif pour général $a $ et $x $.  Étant donné que toutes les opérations de Quantum, enregistrer les mesures, sont réversibles, nous devons conserver suffisamment d’informations pour inverser la multiplication.  Pour cette raison, le résultat est stocké dans un tableau séparé.  Cette astuce d’enregistrement de la sortie d’une opération irréversible, comme la multiplication, dans un registre distinct, est appelée « Astuce Bennett » après Charlie Bennett et est un outil fondamental dans le calcul réversible et le traitement quantique.

De nombreux circuits quantiques ont été proposés pour l’ajout et chacun d’entre eux explore un autre compromis en termes de nombre d’qubits (espace) et le nombre d’opérations de la porte (Time) requises.  Nous examinons deux ajouts de plus en plus d’espace sous le nom d’Adder Draper et l’Adder Beauregard.

### <a name="draper-adder"></a>Draper Adder ###

L’Adder Draper est sans doute l’un des compléments quantiques les plus élégants, car il appelle directement les propriétés Quantum pour effectuer l’addition.  L’idée de l’Adder Draper est que la transformation de Fourier peut être utilisée pour convertir les décalages de phase en un décalage binaire.  Il suit ensuite cela en appliquant une transformation de Fourier, en appliquant des décalages de phase appropriés, puis en annulant la transformation de Fourier, vous pouvez implémenter un Adder.  Contrairement à de nombreux autres ajouts qui ont été proposés, l’Adder Draper utilise explicitement les effets Quantum introduits via la transformation de Fourier quantique.  Elle n’a pas d’équivalent classique naturel.  Les étapes spécifiques de l’Adder Draper sont indiquées ci-dessous.

Supposons que vous avez deux $n des registres qubit $-bit qui stockent les entiers $a $ et $b $ pour tous les $a $ $ $ \operatorname{QFT}\ket{a} = \frac{1}{\sqrt{2 ^ n}} \sum\_{j = 0} ^ {2 ^ n-1} e ^ {i2\pi (AJ)/2 ^ n} \ket{j}.
$ $ Si nous définissons $ $ \ket{\Phi\_k (a)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi a/2 ^ k} \ket{1} \right), $ $ puis, après une algèbre, vous pouvez constater que $ $ \operatorname{QFT}\ket{a} = \ket{\Phi\_1 (a)} \otimes \cdots \otimes \ket{\Phi\_n (a)}.
$ $ Le chemin vers l’exécution d’un Adder devient clair après avoir observé que la somme des entrées peut être écrite sous la forme $ $ \ket{a + b} = \operatorname{QFT} ^{-1}\ket{\Phi\_1 (a + b)} \otimes \cdots \otimes \ket{\Phi\_n (a + b)}.
$ $ Les entiers $b $ et $a $ peuvent ensuite être ajoutés en effectuant une rotation en phase contrôlée sur chaque qubits de la décomposition en utilisant les bits de $b $ comme contrôles.

Cette expansion peut être simplifiée en notant que pour tout entier $j $ et nombre réel $x $, $e ^ {i2\pi (x + j)} = e ^ {i2\pi x} $.  Cela est dû au fait que si vous faites pivoter $360 ^ {\circ} $ degrees ($ 2 \ pi $ radians) dans un cercle, vous obtenez précisément l’emplacement où vous avez commencé.  La seule partie importante de $x $ pour $e ^ {i2\pi x} $ est donc la partie fractionnaire de $x $.  Plus précisément, si nous avons une expansion binaire de la forme $x = y +0. x\_0x\_2 \ ldots x\_n $, $e ^ {i2\pi x} = e ^ {i2\pi (0. x\_0x\_2 \ ldots x\_{n-1})} $ et, par conséquent, $ $ \ket{\Phi\_k (a + b)} = \frac{1}{\sqrt{2}} \left (\ket{0} + e ^ {i2\pi [a/2 ^ k +0. b\_k\ldots b\_1]} \ket{1} \right). $ $ cela signifie que si nous effectuons l’addition en incrémentant chacun des facteurs tenseur dans l’expansion de la transformation de Fourier de-\ket{a} $, alors le le nombre de rotations diminue de $k $ diminue.  Cela réduit considérablement le nombre de portes de Quantum nécessaires dans l’Adder.  Nous dénotarons la transformation de Fourier, l’ajout de phase et les étapes de transformation de Fourier inverse qui composent l’Adder Draper en tant que $ \operatorname{QFT} ^{-1} \left (\Phi\\\!\operatorname{ADD}\right) \operatorname{QFT} $. Un circuit quantique qui utilise cette simplification pour implémenter l’ensemble du processus peut être consulté ci-dessous.

![Draper Adder affiché sous forme de diagramme de circuit](~/media/draper.svg)

Chaque porte contrôlée $e ^ {I2 \ pi/k} $ dans le circuit fait référence à une porte de phase contrôlée.  Ces portes ont la propriété qui se trouve sur la paire de qubits sur laquelle elles agissent, $ \ket{00}\mapsto \ket{00}$ mais $ \ket{11}\mapsto e ^ {I2 \ pi/k} \ Ket{11}$.  Ce circuit nous permet d’effectuer une addition à l’aide d’un qubits supplémentaire, à l’exception de ceux qui sont nécessaires pour stocker les entrées et les sorties.

### <a name="beauregard-adder"></a>Beauregard Adder ###

L’Adder Beauregard est un Adder modulaire quantique qui utilise l’Adder Draper pour effectuer l’addition de modulo $N $ pour un entier positif de valeur arbitraire $N $.  L’importance des compléments modulaires quantiques, tels que l’Beauregard Adder, est importante dans une large mesure de leur utilisation dans l’étape d’élévation modulaire de l’algorithme de Shori pour la factorisation.  Un Adder modulaire Quantum a l’action suivante pour l’entrée Quantum $ \ket{b} $ et l’entrée classique $a $ où $a $ et $b $ sont promis d’être des entiers mod $N $, ce qui signifie qu’ils se trouvent dans l’intervalle $ [0, \ldots, N-1] $.

$ $ \ket{b}\rightarrow \ket{b + a \text{mod} N} = \begin{cases} \ket{b + a}, & b + a < N\\\\ \ket{b + a-N}, & (b + a) \ge N \end{cases}.
$$

L’Adder Beauregard utilise l’Adder Draper, ou plus spécifiquement $ \Phi\\\!\operatorname{ADD} $, pour ajouter $a $ et $b $ en phase.  Il utilise ensuite la même opération pour déterminer si $a + b < N $ en soustrayant $N $ et en testant si $a + b-N < 0 $.  Le circuit stocke ces informations dans un qubit auxiliaire, puis ajoute $N $ Back au Registre si $a + b < N $.  Il conclut ensuite en décalculant ce bit accessoire (cette étape est nécessaire pour s’assurer que le Ancilla peut être désalloué après l’appel de l’Adder).  Le circuit de l’Adder Beauregard est indiqué ci-dessous.

![Beauregard Adder affiché sous forme de diagramme de circuit](~/media/beau.svg)

Ici, la porte $ \Phi\\\!\operatorname{ADD} $ prend la même forme que $ \Phi\\\!\operatorname{ADD} $, sauf que dans ce contexte, l’entrée est classique plutôt que Quantum.  Cela permet de remplacer les phases contrôlées dans $ \Phi\\\!\operatorname{ADD} $ par les portes de phase qui peuvent ensuite être compilées en moins d’opérations pour réduire à la fois le nombre de qubits et le nombre de portes nécessaires pour l’Adder.

Pour plus d’informations, consultez [M. Roetteler, Th. Beth](http://doi.org/10.1007/s00200-008-0072-2 ) et [D. Coppersmith](https://arxiv.org/abs/quant-ph/0201067).

### <a name="quantum-phase-estimation"></a>Estimation des phases quantiques ###

Une application particulièrement importante de la transformation de Fourier quantique consiste à apprendre le valeurs propres d’opérateurs unitaires, un problème connu sous le nom d' *estimation de phase*.
Imaginez un $U unitaire $ et un État $ \ket{\Phi} $, de sorte que $ \ket{\Phi} $ est un eigenstate de $U $ avec eigenvalue $ \Phi $, \begin{Equation} U\ket {\ Phi} = \phi\ket{\Phi}. inconnu.
\end{Equation} si nous avons uniquement accès à $U $ en tant qu’Oracle, nous pouvons apprendre la phase $ \Phi $ en utilisant que $Z $ rotations appliqué à la cible d’une opération contrôlée se propage à nouveau sur le contrôle.

Supposons que $V $ est une application contrôlée de $U $, telle que \begin{align} V (\ket{0} \otimes \ket{\Phi}) & = \ket{0} \otimes \ket{\Phi} \\\\ \textrm{et} V (\ket{1} \otimes \ket{\Phi}) & = e ^ {i \Phi} \ket{1} \otimes \ket{\Phi}.
\end{align} ensuite, par linéarité, \begin{align} V (\ket{+} \otimes \ket{\Phi}) & = \frac{(\ket{0} \otimes \ket{\Phi}) + e ^ {\Phi} (\ket{1} \otimes \ket{\Phi})} {\sqrt{2}}.
\end{align} nous pouvons collecter des termes pour déterminer que \begin{align} V (\ket{+} \otimes \ket{\Phi}) & = \frac{\ket{0} + e ^ {i \Phi} \ket{1}} {\sqrt{2}} \otimes \ket{\Phi} \\\\ & = (R_1 (\Phi) \ket{+}) \otimes \ket{\Phi}, \end{align} où $R 1 1 $ est l’unité appliquée par l’opération <xref:microsoft.quantum.intrinsic.r1>.
Autrement dit, l’effet de l’application de $V $ est précisément identique à l’application de $R 1 _ 1 $ avec un angle inconnu, même si nous n’avons accès qu’à $V $ en tant qu’Oracle.
Ainsi, dans le reste de cette discussion, nous aborderons l’estimation de phase en termes de $R _ 1 (\Phi) $, que nous implémentons à l’aide de la *phase Kickback*.

Dans la mesure où le contrôle et le registre cible ne sont pas transformés après ce processus, nous pouvons réutiliser $ \ket{\Phi} $ comme cible d’une application contrôlée de $U ^ $2 pour préparer un deuxième qubit de contrôle à l’état $R _ 1 (2 \Phi) \ket{+} $.
En continuant ainsi, nous pouvons obtenir un registre au format \begin{align} \ket{\Psi} & = \ sum_ {j = 0} ^ n R_1 (2 ^ j \Phi) \ket{+} \\\\ & \propto \ bigotimes_ {j = 0} ^ {n} \left (\ket{0} + \exp (i 2 ^ {j} \Phi) \ket{1}\right) \\\\ & \propto \ sum_ {k = 0} ^ {2 ^ n-1} \exp (i \Phi k) \ket{k} \end{align} où $n $ est le nombre de bits de précision dont nous avons besoin. et où nous avons utilisé ${} \propto {}$ pour indiquer que nous avons supprimé le facteur de normalisation de $1/\sqrt {2 ^ n} $.

Si nous supposons que $ \Phi = 2 \pi p/2 ^ k $ pour un entier $p $, nous le reconnaissons comme $ \ket{\Psi} = \operatorname{QFT} \ket{p_0 p_1 \dots p_n} $, où $p _J $ est le $j ^ {\textrm{th}} $ bit de $2 \pi \Phi $.
En appliquant le voisin de la transformation de Fourier quantique, nous obtenons donc la représentation binaire de la phase encodée comme un État Quantum.

Dans Q #, elle est implémentée par l’opération <xref:microsoft.quantum.characterization.quantumphaseestimation>, qui prend un <xref:microsoft.quantum.oracles.discreteoracle> implémentant l’application de $U ^ m $ comme fonction des entiers positifs $m $.
