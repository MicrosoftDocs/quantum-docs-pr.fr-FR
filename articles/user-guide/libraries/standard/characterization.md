---
title: Caractérisation quantique et statistiques
description: Découvrez comment les statistiques de mesure des estimations de phase sont utilisées pour estimer les valeurs de résultats dans la programmation quantique.
author: bradben
uid: microsoft.quantum.libraries.characterization
ms.author: martinro
ms.date: 12/11/2017
ms.topic: article
no-loc:
- Q#
- $$v
ms.openlocfilehash: 72af3f5517b272d6d8159b158103b5af91d266b5
ms.sourcegitcommit: c48cdafccb3487bf93d67fa80cdc64768445b691
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/06/2021
ms.locfileid: "97940884"
---
# <a name="quantum-characterization-and-statistics"></a>Caractérisation quantique et statistiques #

Il est essentiel de pouvoir caractériser les effets des opérations afin de développer des algorithmes Quantum utiles.
Cela est difficile, car chaque mesure d’un système Quantum produit au plus un peu d’informations.
Pour apprendre un eigenvalue, laisser un État Quantum autonome, les résultats de nombreuses mesures doivent être regroupés afin que l’utilisateur puisse glaner les nombreux éléments d’informations nécessaires pour représenter ces concepts.
Les États quantiques sont particulièrement vexing, car le titre de [non-clonage](xref:microsoft.quantum.concepts.pauli#the-no-cloning-theorem) stipule qu’il n’existe aucun moyen d’apprendre un État Quantum arbitraire à partir d’une copie unique de l’État, car cela vous permet de créer des copies de l’État.
Cet obscurcissement de l’État Quantum de l’utilisateur est reflété dans le fait que Q# n’expose pas ou ne définit pas l’état  des programmes quantiques.
Nous allons donc aborder la caractérisation quantique en traitant les opérations et les États comme une boîte noire. Cette approche partage en grande partie en commun avec la pratique expérimentale de la caractérisation quantique, la vérification et la validation (QCVV).

La caractérisation est distincte de la plupart des autres bibliothèques présentées précédemment.
L’objectif ici est de réduire les informations classiques sur le système, plutôt que d’effectuer une transformation unitaire sur un vecteur d’État.
Ces bibliothèques doivent donc fusionner à la fois le traitement des informations de Quantum et le traitement des informations.


## <a name="iterative-phase-estimation"></a>Estimation de la phase itérative ##

L’affichage de la programmation quantique en termes de caractérisation quantique suggère une alternative utile à l’estimation de la phase Quantum.
Autrement dit, au lieu de préparer un registre $n $-qubit pour contenir une représentation binaire de la phase comme dans l’estimation de la phase Quantum, nous pouvons voir l’estimation de la phase comme processus par lequel un agent *classique* apprend les propriétés d’un système Quantum par le biais de mesures.
Nous procédons comme dans le cas Quantum en utilisant la phase Kickback pour transformer les applications d’une opération de boîte noire en rotations d’un angle inconnu, mais mesurer le qubit Ancilla que nous allons faire pivoter à chaque étape immédiatement après la rotation.
Cela présente l’avantage que nous n’avons besoin que d’un seul qubit supplémentaire pour effectuer la phase Kickback décrite dans le cas Quantum, car nous apprenons ensuite la phase des résultats de mesure à chaque étape de manière itérative.  
Chacune des méthodes proposées ci-dessous utilise une stratégie différente pour concevoir des expériences et différentes méthodes de traitement des données pour apprendre la phase.  Ils ont chacun un avantage unique, allant de l’utilisation de limites d’erreurs rigoureuses, aux capacités d’incorporation d’informations antérieures, de tolérer des erreurs ou de s’exécuter sur des ordinateurs classiques limitteds de la mémoire.

Dans le cadre de l’estimation itérative de la phase, nous allons considérer un $U unitaire $ donné comme une opération de boîte noire.
Comme décrit dans la section sur oracles dans les [structures de données](xref:microsoft.quantum.libraries.data-structures), Q# Canon modélise ces opérations par le <xref:Microsoft.Quantum.Oracles.DiscreteOracle> type défini par l’utilisateur, défini par le type de Tuple `((Int, Qubit[]) => Unit : Adjoint, Controlled)` .
Concrètement, si `U : DiscreteOracle` , `U(m)` implémente $U ^ m $ pour `m : Int` .

Une fois cette définition en place, chaque étape de l’estimation de phase itérative se poursuit en préparant un qubit auxiliaire dans l’État $ \ket{+} $ avec l’état initial $ \ket{\Phi} $ dont nous supposons qu’il s’agit d’un [extraction](xref:microsoft.quantum.concepts.matrix-advanced) de $U (m) $, par exemple $U (m) \ket{\Phi} = e ^ {im\phi} \ Ket {\ Phi} $.  
Une application contrôlée de `U(m)` est ensuite utilisée pour préparer l’État $ \left (R \_ 1 (m \Phi) \ket{+} \right) \ket{\Phi} $.
Comme dans le cas Quantum, l’effet d’une application contrôlée d’Oracle `U(m)` est exactement le même que l’application de $R _ 1 $ pour la phase inconnue sur $ \ket{+} $, de sorte que nous pouvons décrire les effets de $U $ dans cette méthode plus simple.
Si vous le souhaitez, l’algorithme fait pivoter le contrôle qubit en appliquant $R _ 1 (-m\theta) $ pour obtenir un État $ \ket{\Psi} = \left (R \_ 1 (m [\Phi-\Theta]) \ket{+} \right) \ket{\Phi} $ $.
Le qubit auxiliaire utilisé comme contrôle pour `U(m)` est ensuite mesuré dans le $X $ pour obtenir un seul classique `Result` .

À ce stade, la reconstruction de la phase à partir des `Result` valeurs obtenues par le biais d’une estimation de phase itérative est un problème d’inférence statistique classique.
La recherche de la valeur de $m $ qui maximise les informations obtenues, en fonction d’une méthode d’inférence fixe, est simplement un problème dans les statistiques.
Nous insistons sur cela en décrivant brièvement l’estimation de phase itérative à un niveau théorique dans le formalisme d’estimation du paramètre bayésien avant de continuer à décrire les algorithmes statistiques fournis dans Q# Canon pour résoudre ce problème d’inférence classique.

### <a name="iterative-phase-estimation-without-eigenstates"></a>Estimation itérative de la phase sans Eigenstates ###

Si un état d’entrée qui n’est pas un eigenstate est fourni, ce qui signifie que si $U (m) \ket{\Phi \_ j} = e ^ {im\phi \_ j} $, le processus d’estimation de phase ne redirige pas de façon déterminante l’État Quantum vers un eigenstate d’énergie unique.  Le eigenstate qui se converge finalement vers est le eigenstate qui est le plus susceptible de produire le observé `Result` .

Plus précisément, une seule étape de PE effectue la transformation non unitaire suivante sur un État \begin{align} \ sum_j \sqrt{\Pr (\Phi \_ j)} \ket{\Phi \_ j} \mapsto \sum \_ j\frac {\ sqrt {\ PR (\Phi \_ j)} \sqrt{\Pr (\text{result} | \Phi \_ j)} \Ket{\Phi \_ j}} {\sqrt{\Pr (\Phi \_ j) \sum \_ k \Pr (\text{result} | \Phi \_ k)}}.
\end{align} étant donné que ce processus est itéré sur plusieurs `Result` valeurs, les eigenstates qui n’ont pas de valeurs maximales de $ \ prod_k \pr (\text{result} \_ k | \Phi \_ j) $ seront supprimés de façon exponentielle.
Par conséquent, le processus d’inférence aura tendance à converger vers des États avec un seul eigenvalue si les expériences sont correctement choisies.

Bayes’le type d’enregistrement suggère également que l’état résultant de l’estimation de la phase soit écrit sous la forme \begin{align} \frac{\sqrt{\Pr (\Phi \_ j)} \sqrt{\Pr (\text{result} | \Phi \_ j)} \ket{\Phi \_ j}} {\sqrt{\Pr (\Phi \_ j) \Sum \_ j \Pr (\text{result} | \Phi \_ j)}} = \ sum_j \sqrt{\Pr (\Phi \_ j | \text{result})} \ket{\Phi \_ j}.
\end{align} ici $ \Pr (\Phi \_ j | \text{result}) $ peut être interprété comme la probabilité qu’un ASCRIBE à chaque hypothèse sur le eigenstates donné :

1. connaissance de l’État Quantum avant la mesure,
2. connaissance du eigenstates de $U $ et,
3. connaissance du valeurs propres de $U $.

L’apprentissage de ces trois éléments est souvent très difficile sur un ordinateur classique.
L’utilitaire de l’estimation de la phase se présente, à peu de temps, du fait qu’il peut exécuter une telle tâche d’apprentissage quantique sans en connaître aucune.
L’estimation de la phase pour cette raison s’affiche dans un certain nombre d’algorithmes Quantum qui fournissent des accélérations exponentielles.

### <a name="bayesian-phase-estimation"></a>Estimation de la phase bayésienne ###

> [!TIP]
> Pour plus d’informations sur l’estimation de la phase bayésien dans la pratique, consultez l’exemple [**PhaseEstimation**](https://github.com/microsoft/Quantum/tree/main/samples/characterization/phase-estimation) .

L’estimation de la phase bayésienne est simple.
Vous recueillez des statistiques de mesure à partir du protocole d’estimation de phase, puis vous traitez les résultats à l’aide de l’inférence Bayésienne et fournissez une estimation du paramètre.
Ce traitement vous donne une estimation des eigenvalue, ainsi que de l’incertitude dans cette estimation.
Elle vous permet également d’effectuer des expérimentations adaptatives et d’utiliser des informations antérieures.
L’inconvénient des méthodes est qu’elle exige des calculs.

Pour comprendre le fonctionnement de ce processus d’inférence Bayésienne, prenez le cas de traiter un `Zero` résultat unique.
Notez que $X = \ket{+} \bra{+}-\ket {-} \bra {-} $, de sorte que $ \ket{+} $ est le seul eigenstate positif de $X $ correspondant à `Zero` .
La probabilité d’observer `Zero` une [ `PauliX` mesure](xref:microsoft.quantum.concepts.pauli) sur le premier qubit en fonction de l’état d’entrée $ \ket{\Psi}\ket{\Phi} $ est donc \begin{Equation} \Pr (\texttt{Zero} | \Psi) = \left | \braket{+ | \Psi} \right | ^ 2.
\end{Equation} dans le cas de l’estimation itérative de la phase, nous avons \ket{\Psi} = R_1 (m [\Phi-\Theta]) \ket{+} $, de telle sorte que \begin{align} \Pr (\texttt{Zero} | \Phi ; m, \Theta) & = \left | \braket{+ | R_1 (m [\Phi-\Theta]) | +} \right | ^ 2 \\ \\ & = \left | \frac12 \left (\bra {0} + \bra {1} \right) \left (\ket {0} + e ^ {i m [\Phi-\Theta]} \ket {1} \right) \right | ^ 2 \\ \\ & = \left | \frac{1 + e ^ {i m [\phi-\theta]}} {2} \right | ^ 2 \\ \\ & = \cos ^ 2 (m [\Phi-\Theta]/2) \tag{★} \label{EQ : phase-est-vraisemblance}.
\end{align} qui est, l’estimation de la phase itérative consiste à apprendre la fréquence d’oscillation d’une fonction sinusoïdale, étant donné la capacité de retourner une pièce de monnaie avec un décalage donné par ce sinusoïdal.
À la suite de la terminologie classique traditionnelle, nous appelons $ \eqref{EQ : phase-est-vraisemblance} $ la *fonction de probabilité* pour l’estimation de la phase itérative.

Après avoir observé un `Result` à partir de la fonction de probabilité d’estimation de la phase itérative, nous pouvons ensuite utiliser la règle de Bayes pour prescrire ce que nous devrions estimer la phase à suivre.
Concrètement, \begin{Equation} \Pr (\Phi | d) = \frac{\Pr (d | \Phi) \Pr (\Phi)} {\int \Pr (d | \Phi) \Pr (\Phi) {\mathrm d} \Phi} \Pr (\Phi), \end{Equation} où $d \Dans \\ {\texttt{Zero}, \texttt{One} \\ } $ est un `Result` , et où $ \Pr (\Phi) $ décrit nos opinions antérieures sur $ \Phi $.
Cela rend ensuite la nature itérative de l’estimation de phase itérative explicite, car la distribution POSTERIEURE $ \Pr (\Phi | d) $ décrit nos points de présence qui précèdent immédiatement l’observation de la suivante `Result` .

À tout moment pendant cette procédure, nous pouvons signaler la phase $ \hat{\Phi} $ déduite par le contrôleur classique en tant que \begin{Equation} \hat{\Phi} \mathrel{ : =} \expect [\Phi | \text{Data}] = \int \Phi \Pr (\Phi | \text{Data}) {\mathrm d} \Phi, \end{Equation} où $ \text{Data} $ correspond à l’enregistrement complet de toutes les `Result` valeurs obtenues.

L’inférence Bayésienne exacte est dans la pratique inversement.
Pour voir cela, imaginez que nous souhaitons apprendre une variable de $n $-bit $x $.
La distribution antérieure $ \Pr (x) $ prend en charge plus de $2 ^ n $ valeurs hypothétiques de $x $.
Cela signifie que si nous avons besoin d’une estimation très précise de $x $, l’estimation de la phase Bayésiene peut nécessiter une mémoire et un temps de traitement prohibitifs.
Bien que pour certaines applications, telles que la simulation de Quantum, la précision limitted requise n’exclut pas ces méthodes, d’autres applications, telles que l’algorithme de Shori, ne peuvent pas utiliser l’inférence Bayésienne exacte au cours de l’étape d’estimation de la phase.  Pour cette raison, nous fournissons également des implémentations pour des méthodes Bayésienles approximatives telles que l' [estimation de phase de parcours aléatoire (RWPE)](xref:Microsoft.Quantum.Research.Characterization.RandomWalkPhaseEstimation) et également des approches non bayésienles telles que l' [estimation de phase fiable](xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation).

### <a name="robust-phase-estimation"></a>Estimation de phase robuste ###

*Une reconstruction bayésienne* au maximum d’une estimation de phase à partir des résultats de mesure est de façon exponentielle dans le pire des cas. Ainsi, la plupart des algorithmes d’estimation de la phase pratique sacrifient une certaine qualité de la reconstruction, en échange d’une quantité de traitement classique qui, à la place, s’adapte au degré polynomial avec le nombre de mesures effectuées.

L' [algorithme d’estimation de phase robuste](https://arxiv.org/abs/1502.02677), avec sa signature et ses entrées mentionnées ci-dessus, est un exemple avec une étape de traitement classique efficace. Il part du principe que les boîtiers noirs d’entrée $U $ sont empaquetés en tant que `DiscreteOracle` type et, par conséquent, interroge uniquement les valeurs entières de Control-$U $. Si l’état d’entrée dans le `Qubit[]` Registre est un eigenstate $U \ket{\Psi} = e ^ {i\phi} \ Ket {\ psi} $, l’algorithme d’estimation de phase robuste retourne une estimation $ \hat{\Phi}\in [-\pi, \pi) $ de $ \Phi $ en tant que `Double` .

La fonctionnalité la plus importante de l’estimation de phase fiable, qui est partagée avec la plupart des autres variantes utiles, est que la qualité de reconstruction de $ \hat{\Phi} $ est dans un sens Heisenberg-Limited. Cela signifie que si l’écart de $ \hat{\Phi} $ de la valeur true est $ \sigma $, alors $ \sigma $ est mis à l’échelle inversement-proportionnel au nombre total de requêtes $Q $ effectuées à Control-$U $, c’est-à-dire $ \sigma = \mathcal{O} (1/Q) $. À présent, la définition de l’écart varie selon les différents algorithmes d’estimation. Dans certains cas, cela peut signifier qu’avec au moins $ \mathcal{O} (1) $ probabilité, l’erreur d’estimation $ | \hat{\Phi}-\Phi | \_ \circ\le \sigma $ sur une mesure circulaire $ \circ $. Pour une estimation de phase robuste, l’écart est précisément l’écart $ \sigma ^ 2 = \mathbb{E} \_ \hat{\Phi} [(\mod \_ {2 \ pi} (\hat{\Phi}-\Phi + \pi)-\pi) ^ 2] $ si nous désencapsulons les phases périodiques sur un seul intervalle fini $ (-\pi, \pi] $. Plus précisément, l’écart type de l’estimation de phase fiable satisfait aux inégales $ $ \begin{align} 2,0 \pi/Q \Le \sigma \Le 2 \ pi/2 ^ {n} \Le 10.7 \ pi/Q, \end{align} $ $ où la limite inférieure est atteinte dans la limite de asymptotiquement grande $Q $, et la limite supérieure est garantie même pour les petites tailles d’échantillonnage.  Notez que $n $ sélectionné par l' `bitsPrecision` entrée, qui définit implicitement $Q $.

D’autres informations pertinentes incluent, par exemple, la surcharge de petite taille de seulement $1 $ Ancilla qubit, ou la procédure n’est pas adaptative, ce qui signifie que la séquence requise des expérimentations de Quantum est indépendante des résultats de mesure intermédiaires. Dans cet exemple et les prochains exemples où le choix de l’algorithme d’estimation de la phase est important, il est préférable de faire référence à la documentation telle que @"microsoft.quantum.characterization.robustphaseestimation" et les publications référencées dans ce document pour obtenir plus d’informations et pour leur implémentation.

> [!TIP]
> Il existe de nombreux exemples dans lesquels l’estimation de phase robuste est utilisée. Pour l’estimation de phase dans l’extraction de l’énergie d’État du sol de divers systèmes physiques, consultez l’exemple de [ **simulation H2**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/h2/command-line), l' [exemple **SimpleIsing**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/ising/simple)et l’exemple de [ **modèle Hubbard**](https://github.com/microsoft/Quantum/tree/main/samples/simulation/hubbard).


### <a name="continuous-oracles"></a>Oracle continue ###

Nous pouvons également généraliser à partir du modèle Oracle utilisé ci-dessus pour autoriser les Oracle à temps continu, modélisés par le type Canon <xref:Microsoft.Quantum.Oracles.ContinuousOracle> .
Supposons qu’au lieu d’un opérateur d’unité unique $U $, nous disposons d’une famille d’opérateurs unitaires $U (t) $ pour $t \Dans \mathbb{R} $, ce qui $U (t) U (s) $ = $U (t + s) $.
Il s’agit d’une instruction plus faible que dans le cas discret, puisque nous pouvons construire un <xref:Microsoft.Quantum.Oracles.DiscreteOracle> en restreignant $t = m \, \delta t $ pour un $ \delta t $ fixe.
Par le [fabricant de pierres](https://en.wikipedia.org/wiki/Stone%27s_theorem_on_one-parameter_unitary_groups), $U (t) = \exp (i H t) $ pour un opérateur $H $, où $ \exp $ est la matrice exponentielle comme décrit dans [matrices avancées](xref:microsoft.quantum.concepts.matrix-advanced).
Un eigenstate $ \ket{\Phi} $ de $H $ comme $H \ket{\Phi} = \Phi \ket{\Phi} $ est également une eigenstate de $U (t) $ pour tous les $t $, \begin{Equation} U (t) \ket{\Phi} = e ^ {\Phi t} \ket{\Phi}.
\end{equation}

Exactement la même analyse abordée pour l’estimation de la [phase bayésienne](#bayesian-phase-estimation) peut être appliquée, et la fonction de vraisemblance est exactement la même pour ce modèle Oracle plus général : $ $ \Pr (\texttt{Zero} | \Phi ; t, \Theta) = \cos ^ 2 \ Left (\frac{t [\Phi-\Theta]} {2} \right).
$ $ En outre, si $U $ est une simulation d’un générateur dynamique, comme c’est le cas pour la [simulation de Hamilton](xref:microsoft.quantum.libraries.applications#hamiltonian-simulation), nous interprétons $ \Phi $ comme une énergie.
Par conséquent, l’utilisation de la fonction d’estimation de phase avec des requêtes continues nous permet d’apprendre le [spectre énergétique simulé des molécules, des](https://arxiv.org/abs/quant-ph/0604193) [matériaux](https://arxiv.org/abs/1510.03859) ou des théories sur les [champs](https://arxiv.org/abs/1111.3633v2) sans avoir à compromettre notre choix d’expériences en exigeant $t $ comme un entier.

### <a name="random-walk-phase-estimation"></a>Estimation de la phase de parcours aléatoire ###

Q# fournit une approximation utile de l’estimation de la phase bayésien conçue pour une utilisation proche des appareils quantiques qui fonctionnent en conditionné un parcours aléatoire sur l’enregistrement de données obtenu à partir d’une estimation de la phase itérative.
Cette méthode est à la fois adaptative et entièrement déterministe, ce qui permet une mise à l’échelle presque optimale des erreurs dans la phase estimée $ \hat{\Phi} $ avec des surcharges de mémoire très faibles.

Le protocole utilise une méthode d’inférence Bayésienle approximative qui suppose que la distribution antérieure est gaussienne.
Cette hypothèse gaussienne nous permet d’utiliser une formule analytique pour l’expérience qui minimise la variance postérieure.
L’algorithme ensuite, en fonction du résultat de cette expérience, déplace l’estimation de $ \Phi $ Left ou Right d’une quantité prédéterminée et réduit la variance d’une quantité prédéterminée.
Cette moyenne et cette variance fournissent toutes les informations nécessaires pour spécifier une valeur gaussienne antérieure à $ \Phi $ pour l’expérience suivante.
Des échecs de mesure inattendus ou le résultat réel sur les queues de l’initiale précédente peuvent entraîner l’échec de cette méthode.
Il récupère de la défaillance en effectuant des expérimentations pour tester si la moyenne actuelle et l’écart type sont appropriés pour le système.
Si ce n’est pas le cas, l’algorithme effectue une étape inverse du parcours et le processus continue.
La possibilité de revenir en arrière permet également à l’algorithme d’apprendre même si l’écart type initial antérieur est inapropriately petit.

## <a name="calling-phase-estimation-algorithms"></a>Appel d’algorithmes d’estimation de phase ##

Chaque opération d’estimation de phase fournie avec Q# Canon prend un ensemble différent d’entrées paramétrant la qualité que nous demandons de l’estimation finale $ \hat{\Phi} $.
Ces différentes entrées, cependant, partagent toutes plusieurs entrées en commun, de telle sorte que l’application partielle sur les paramètres de qualité entraîne une signature commune.
Par exemple, l' <xref:Microsoft.Quantum.Characterization.RobustPhaseEstimation> opération décrite dans la section suivante a la signature suivante :

```qsharp
operation RobustPhaseEstimation(bitsPrecision : Int, oracle : DiscreteOracle, eigenstate : Qubit[])  : Double
```

L' `bitsPrecision` entrée est unique à `RobustPhaseEstimation` , tandis que `oracle` et `eigenstate` sont en commun.
Ainsi, comme indiqué dans **H2Sample**, une opération peut accepter un algorithme d’estimation de phase itérative avec une entrée de la forme `(DiscreteOracle, Qubit[]) => Unit` pour permettre à un utilisateur de spécifier des algorithmes d’estimation de phase arbitraires :

```qsharp
operation H2EstimateEnergy(
    idxBondLength : Int,
    trotterStepSize : Double,
    phaseEstAlgorithm : ((DiscreteOracle, Qubit[]) => Double))
: Double
```

Ces algorithmes d’estimation de myriade de phases sont optimisés pour différentes propriétés et paramètres d’entrée, qui doivent être compris pour faire le meilleur choix pour l’application cible. Par exemple, certains algorithmes d’estimation de phase sont adaptatifs, ce qui signifie que les étapes futures sont contrôlées de manière classique par les résultats de mesure des étapes précédentes. Certains requièrent la capacité d’exponentiate de son Oracle sous la boîte noire par des pouvoirs réels arbitraires, tandis que d’autres ne nécessitent que des valeurs entières, mais sont uniquement en mesure de résoudre une estimation de phase modulo $2 \ pi $. Certains requièrent un grand nombre d’qubits auxiliaires, tandis que d’autres en ont besoin.

De même, l’estimation de la phase de parcours aléatoire s’effectue de la même façon que pour les autres algorithmes fournis avec Canon :

```qsharp
operation ApplyExampleOracle(
    eigenphase : Double,
    time : Double,
    register : Qubit[])
: Unit is Adj + Ctl {
    Rz(2.0 * eigenphase * time, register[0]);
}

operation EstimateBayesianPhase(eigenphase : Double) : Double {
    let oracle = ContinuousOracle(ApplyExampleOracle(eigenphase, _, _));
    using (eigenstate = Qubit()) {
        X(eigenstate);
        // The additional inputs here specify the mean and variance of the prior, the number of
        // iterations to perform, how many iterations to perform as a maximum, and how many
        // steps to roll back on an approximation failure.
        let est = RandomWalkPhaseEstimation(0.0, 1.0, 61, 100000, 1, oracle, [eigenstate]);
        Reset(eigenstate);
        return est;
    }
}
```
