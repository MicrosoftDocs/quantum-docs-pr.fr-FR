---
title: Dirac notation | Microsoft Docs
description: Notation Dirac
author: QuantumWriter
uid: microsoft.quantum.concepts.dirac
ms.author: nawiebe@microsoft.com
ms.date: 12/11/2017
ms.topic: article
ms.openlocfilehash: 33d964d079c94bd947e35d2c09516b29df1bba11
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/28/2019
ms.locfileid: "73184761"
---
# <a name="dirac-notation"></a>Notation Dirac

Bien que la notation de vecteur de colonne soit omniprésente en algébrique linéaire, elle est souvent lourde dans l’informatique Quantum, en particulier lors du traitement de plusieurs qubits.  Par exemple, quand nous définissons $ \Psi $ comme un vecteur, il n’est pas évident de savoir explicitement si $ \Psi $ est un vecteur de ligne ou de colonne.  Par conséquent, si $ \Phi $ et $ \Psi $ sont des vecteurs, il est tout aussi inclair si $ \Phi \Psi $ est même défini, car les formes de $ \Phi $ et $ \Psi $ peuvent ne pas être claires dans le contexte.  Au-delà de l’ambiguïté sur les formes de vecteurs, l’expression de vecteurs simples à l’aide de la notation algébrique linéaire introduite plus tôt peut être très lourde. Par exemple, si nous souhaitons décrire un $n État $-qubit où chaque qubit prend la valeur $0 $, alors nous exprimerions formellement l’État en 

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix}. $$  

Bien entendu, l’évaluation de ce produit tenseur est impossible, car le vecteur se trouve dans un espace de grande ampleur et cette notation est en fait la meilleure description de l’État qui peut être donnée à l’aide de la notation précédente.  

La [*notation Dirac*](https://en.wikipedia.org/wiki/Bra%E2%80%93ket_notation) résout ces problèmes en présentant un nouveau langage pour répondre aux besoins précis des mécanismes quantiques.  Pour cette raison, nous recommandons que le lecteur n’affiche pas les exemples de cette section comme une prescription rigide sur la manière de décrire les États de Quantum, mais plutôt d’encourager le lecteur à les afficher comme des suggestions qui peuvent être utilisées pour exprimer de façon concise des idées de Quantum.

Il existe deux types de vecteurs dans la notation Dirac : le vecteur *Bra* et le vecteur *Ket* , donc nommé, car lorsqu’ils sont réunis, ils forment un *frein* ou un produit interne.  Si $ \Psi $ est un vecteur de colonne, nous pouvons l’écrire dans la notation Dirac sous la forme $ \ket{\Psi} $, où $ \ket{\cdot} $ indique qu’il s’agit d’un vecteur de colonne d’unité, c’est-à-dire un vecteur *Ket* .  De même, le vecteur de ligne $ \Psi ^ \dagger $ est exprimé sous la forme $ \bra{\Psi} $. En d’autres termes, $ \Psi ^ \dagger $ est obtenu en appliquant une conjugaison complexe d’entrée aux éléments de la transpose de $ \Psi $. La notation Bra-Ket implique directement que $ \braket{\Psi | \Psi} $ est le produit interne de Vector $ \Psi $ avec lui-même, qui est par définition $1 $.  

Plus généralement, si $ \Psi $ et $ \Phi $ sont des vecteurs d’État Quantum, leur produit interne est $ \braket{\Phi | \Psi} $, ce qui implique que la probabilité de mesurer l’État $ \ket{\Psi} $ pour être $ \ket{\Phi} $ est $ | \braket{\Phi | \Psi} | ^ 2 $.  

La Convention suivante est utilisée pour décrire les États de Quantum qui encodent les valeurs de zéro et un (les États de la base de calcul qubit simple) :

$ $ \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0}, \qquad \begin{bmatrix} 0 \\\\ 1 \end{bmatrix} = \ket{1}.
$$

### <a name="example-representing-the-hadamard-operation-with-dirac-notation"></a>Exemple : représentation de l’opération Hadarmard avec la notation Dirac

La notation suivante est souvent utilisée pour décrire les États qui résultent de l’application de la porte Hadarmard à $ \ket{0}$ et $ \ket{1}$ (qui correspondent aux vecteurs d’unités dans les directions $ + x $ et $-x $ sur la sphère Bloch) :

$ $ \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\ 1 \end{bmatrix} = H\ket{0} = \ket{+}, \qquad \frac{1}{\sqrt{2}} \begin{bmatrix} 1 \\\\-1 \end{bmatrix} = H\ket{1} = \ket{-} .
$$

Ces États peuvent également être développés à l’aide de la notation Dirac comme sommes de $ \ket{0}$ et $ \ket{1}$ :

$ $ \ket{+} = \frac{1}{\sqrt{2}} (\ket{0} + \ket{1}), \qquad \ket{-} = \frac{1}{\sqrt{2}} (\ket{0}-\ket{1}).
$$

### <a name="computational-basis-vectors"></a>Vecteurs de base de calcul
Cela démontre pourquoi ces États sont souvent appelés « *calcul*» : chaque état quantique peut toujours être exprimé sous la forme de sommes de vecteurs de calcul et ces sommes sont facilement exprimées à l’aide de la notation Dirac.  L’inverse est également vrai dans le fait que les États $ \ket{+} $ et $ \ket{-}$ constituent également une base pour les États quantiques.  Vous pouvez le voir à partir du fait que

$ $ \ket{0} = \frac{1}{\sqrt{2}} (\ket{+} + \ket{-}), \qquad \ket{1} = \frac{1}{\sqrt{2}} (\ket{+}-\ket{-}).
$$

En guise d’exemple de notation Dirac, considérez le frein $ \braket{0 | 1} $, qui est le produit interne entre $0 $ et $1 $.  Il peut être écrit comme 

$ $ \braket{0 | 1} = \begin{bmatrix} 1 & 0 \end{bmatrix}\begin{bmatrix}0\\\\ 1 \ end {bmatrix} = 0. $ $

Cela indique que $ \ket{0}$ et $ \ket{1}$ sont des vecteurs orthogonaux, ce qui signifie que $ \braket{0 | 1} = \braket{1 | 0} = $0.  De même, par définition $ \braket{0 | 0} = \braket{1 | 1} = 1 $, ce qui signifie que les deux vecteurs de base de calcul peuvent également être appelés *orthonormal*.
Ces propriétés orthonormal sont utiles dans l’exemple suivant. Si nous avons un État $ \ket{\Psi} = {\frac{3}{5}} \ket{1} + {\frac{4}{5}} \ket{0}$, car $ \braket{1 | 0} = $0 la probabilité de mesurer $1 $ est  

$ $ \big | \braket{1 | \Psi}\big | ^ 2 = \left | \frac{3}{5}\braket{1 | 1} + \frac{4}{5}\braket{1 | 0} \right | ^ 2 = \frac{9}{25}. $ $ 

### <a name="tensor-product-notation"></a>Notation de produit tenseur
La notation Dirac comprend également une structure de produit tenseur implicite.  Cela est important, car dans Quantum Computing, le vecteur d’état décrit par deux registres quantiques non corrélés est les produits tenseur des deux vecteurs d’État.  La description concise de la structure du produit tenseur, ou de son manque, est vitale si vous souhaitez expliquer un calcul quantique.  La structure du produit tenseur implique que nous pouvons écrire $ \Psi \otimes \Phi $ pour deux vecteurs d’État Quantum $ \Phi $ et $ \Psi $ comme $ \ket{\Psi} \ket{\Phi} $, parfois explicitement écrits sous la forme $ \ket{\Psi} \otimes \ket{\Phi} $, toutefois par Convention, en écrivant $ \otimes $ entre les vecteurs n’est pas nécessaire.  Par exemple, l’état avec deux qubits initialisé à l’état zéro est fourni par

$ $ \begin{bmatrix} 1 \\\\ 0 \\\\ 0 \\\\ 0 \end{bmatrix} = \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} \otimes \begin{bmatrix} 1 \\\\ 0 \end{bmatrix} = \ket{0} \ otimes \ket{0}= \ket{0} \ket{0}.
$$

De même, l’État $ \ket{p} $ pour Integer $p $ représente un État Quantum qui encode en représentation binaire l’entier $p $.  Par exemple, si nous souhaitons exprimer le nombre $5 $ à l’aide d’un encodage binaire non signé, nous pourrions l’exprimer tout aussi

$ $ \ket{1}\ket{0}\ket{1} = \ket{101} = \ket{5}.
$$

Au sein de cette notation, $ \ket{0}$ ne doit pas faire référence à un seul État qubit, mais plutôt un *enregistrement qubit* stockant un encodage binaire de $0 $.  Les différences entre ces deux notations sont généralement claires du contexte.  Cette Convention est utile pour simplifier le premier exemple qui peut être écrit de l’une des manières suivantes :

$ $ \begin{bmatrix}1 \\\\ 0 \end{bmatrix}\otimes \cdots \otimes\begin{bmatrix}1 \\\\ 0 \end{bmatrix} = \ket{0} \otimes \cdots \otimes \ket{0}= | 0 \ cdots 0 \ rangle = \ket{0}^ {\otimes n} = \ket{0}.
$$

### <a name="example-describing-superposition-with-dirac-notation"></a>Exemple : description de la superposition avec la notation Dirac
Voici un autre exemple de la façon dont vous pouvez utiliser la notation Dirac pour décrire un État Quantum, prenez en compte les méthodes équivalentes suivantes pour écrire un État Quantum qui est une superposition égale sur chaque chaîne de bits possible de longueur $n $

$ $ H ^ {\otimes n} \ket{0} = \frac{1}{2 ^ {n/2}} \sum_{j = 0} ^ {2 ^ n-1} \ket{j} = \ket{+} ^ {\otimes n}.
$$

Vous vous demandez peut-être pourquoi la somme va de $0 $ à $2 ^ {n}-$1 pour $n $ bits.  Notez d’abord qu’il y a au plus 2 ^ {n} $ configurations différentes que $n $ bits peut prendre.  Vous pouvez voir cela en notant qu’un bit peut prendre $2 valeurs $, mais deux bits peuvent prendre $4 $ valeurs, et ainsi de suite. En général, cela signifie qu’il y a au plus 2 ^ n $ différentes chaînes de bits possibles, mais la plus grande valeur encodée dans l’une d’entre elles $1 \ cdots 1 = 2 ^ n-$1 et par conséquent, il s’agit de la limite supérieure de la somme.
En guise de note, dans cet exemple, nous n’avons pas utilisé $ \ket{+} ^ {\otimes n} = \ket{+} $ en analogie avec $ \ket{0}^ {\otimes n} = \ket{0}$, car cette Convention notation est généralement réservée pour l’état de la base de calcul avec chaque qubit initialisé à zéro.  Bien qu’une telle convention soit rationnelle dans ce cas, elle n’est pas utilisée dans la documentation quantum computing.

### <a name="expressing-linearity-with-dirac-notation"></a>Expression de linéarité avec la notation Dirac
Une autre fonctionnalité intéressante de la notation Dirac est le fait qu’elle est linéaire.  Si nous souhaitons écrire pour les quatre vecteurs d’État Quantum, 

$ $ (\alpha \ket{\Psi} + \beta\ket{\Phi}) \otimes (\gamma \ket{\chi} + \delta \ket{\omega}) = \alpha\gamma \ket{\Psi}\ket{\chi} + \alpha\delta \ket{\Psi}\ket{\omega} + \beta\gamma\ket{\Phi}\ket{\chi} + \beta\delta\ket{\Phi}\ket{\omega}. $ $

Autrement dit, vous pouvez distribuer la notation de produit tenseur dans la notation Dirac afin que la réalisation de produits tenseur entre les vecteurs d’État se termine comme une multiplication ordinaire.

Les vecteurs Bra suivent une convention similaire pour les vecteurs Ket.  Par exemple, le vecteur $ \bra{\Psi}\bra{\Phi} $ est équivalent au vecteur d’État $ \Psi ^ \dagger \otimes \Phi ^ \dagger = (\psi\otimes \Phi) ^ \dagger $. Si le vecteur Ket $ \ket{\Psi} $ est $ \alpha \ket{0} + \beta \ket{1}$, la version du vecteur Bra du vecteur est $ \bra{\Psi} = \ket{\Psi} ^ \dagger = (\bra{0}\alpha ^ * + \bra{1}\beta ^ *) $.

Par exemple, imaginez que nous souhaitons calculer la probabilité de mesurer l’État $ \ket{\Psi} = \frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}$ à l’aide d’un programme Quantum pour mesurer les États en tant que $ \ket{+} $ ou $ \ket{-}$. La probabilité que l’appareil produise la sortie de l’État est $ \ket{-}$ est 

$ $ | \braket{-| \Psi} | ^ 2 = \left | \frac{1}{\sqrt{2}} (\bra{0}-\bra{1}) (\frac{3}{5} \ket{1} + \frac{4}{5} \ket{0}) \right | ^ 2 = \left |-\frac{3}{5 \ sqrt{2}} + \frac{4}{5 \ sqrt{2}} \right | ^ 2 = \frac{1}{50}. $ $

Le fait que le signe négatif apparaisse dans le calcul de la probabilité est une manifestation d’interférence quantique, qui est l’un des mécanismes par lequel quantum computing gagne en avantages par rapport à l’informatique classique.

## <a name="ketbra-or-outer-product"></a>ketbra ou produit externe
L’élément final justifiant une discussion en notation Dirac est le produit *ketbra* ou externe.  Le produit externe est représenté dans les notations Dirac en tant que $ \ket{\Psi} \bra{\Phi} $, et parfois appelé ketbras, car les bras et Kets se produisent dans l’ordre inverse comme brakets.  Le produit externe est défini via la multiplication de matrice en tant que $ \ket{\Psi} \bra{\Phi} = \Psi \Phi ^ \dagger $ pour les vecteurs d’État Quantum $ \Psi $ et $ \Phi $.  L’exemple le plus simple et le plus courant de cette notation est

$ $ \ket{0} \bra{0} = \begin{bmatrix}1\\\\ 0 \end{bmatrix}\begin{bmatrix}1 & 0 \end{bmatrix} = \begin{bmatrix}1 & 0\\\\ 0 & 0 \ end {bmatrix} \qquad \ket{1} \bra{1} = \begin{bmatrix}0\\\\ 1 \end{bmatrix}\begin{bmatrix}0 & 1 \end{bmatrix} = \begin{bmatrix}0 & 0\\\\ 0 & 1 \ end {bmatrix}.
$$

Les Ketbras sont souvent appelés projecteurs, car ils projetent un État Quantum sur une valeur fixe.  Étant donné que ces opérations ne sont pas unitaires (et ne préservent même pas la norme d’un vecteur), il ne faut pas surprenant qu’un ordinateur quantique ne puisse pas appliquer de façon déterminante un projecteur.  Toutefois, les projecteurs font un beau travail pour décrire l’action que la mesure a sur un État Quantum.  Par exemple, si nous mesurons un État $ \ket{\Psi} $ sur $0 $, la transformation résultante que l’État rencontre à la suite de la mesure est

  $ $ \ket{\Psi} \rightarrow \frac{(\ket{0} \bra{0}) \ket{\Psi}}{| \braket{0 | \Psi} |} = \ket{0}, $ $

comme nous l’avons prévu, si vous devez mesurer l’État et le trouver comme étant $ \ket{0}$.  Pour rappeler, ces projecteurs ne peuvent pas être appliqués sur un état d’un ordinateur quantique de manière déterministe.  Au lieu de cela, ils peuvent au mieux être appliqués de façon aléatoire avec le résultat $ \ket{0}$ apparaissant avec une probabilité fixe.  La probabilité d’une telle mesure réussie peut être écrite en tant que valeur de l’attente du projecteur quantique dans l’État

$ $ \bra{\Psi} (\ket{0} \bra{0}) \ket{\Psi} = | \braket{\Psi | 0} | ^ 2, $ $

qui illustre que les projecteurs offrent simplement un nouveau moyen d’exprimer le processus de mesure.

Si, au lieu de cela, nous envisageons de mesurer le premier qubit d’un État qubit à $1 $, nous pouvons également décrire ce processus facilement à l’aide de projecteurs et de la notation Dirac :

$ $ P (\text{First qubit = 1}) = \bra{\Psi}\left (\ket{1}\bra{1}\otimes \boldone ^ {\otimes n-1} \right) \ket{\Psi}.
$$

Ici, la matrice d’identité peut être écrite facilement en notation Dirac comme

$ $ \boldone = \ket{0} \bra{0}+ \ket{1} \bra{1}= \begin{bmatrix}1 & 0\\\\ 0 & 1 \end{bmatrix}.
$$

Pour le cas où il y a deux qubits, le projecteur peut être développé comme 

$ $ \ket{1} \bra{1} \otimes \ID = \ket{1}\bra{1} \otimes (\ket{0} \bra{0}+ \ket{1} \bra{1}) = \ket{10}\bra{10} + \ket{11}\bra{11}.
$$

Nous pouvons ensuite constater que cela est cohérent avec la discussion sur les probabilités de mesure pour les États multiqubit à l’aide de la notation de vecteur de colonne :

$ $ P (\text{First qubit = 1}) = \Psi ^ \dagger (e\_{10}e\_{10}^ \dagger + e\_{11}e\_{11}^ \dagger) \Psi = | e\_{10}^ \dagger \Psi | ^ 2 + | e\_{11}^ \ poignard \Psi | ^ 2, $ $

qui correspond à la discussion sur la mesure qubit.  La généralisation de ce résultat au cas qubit, cependant, est légèrement plus simple à exprimer à l’aide de la notation Dirac que la notation de vecteur de colonne et est entièrement équivalente au traitement précédent.

## <a name="density-operators"></a>Opérateurs de densité

Un autre opérateur utile pour exprimer l’utilisation de la notation Dirac est un *opérateur de densité*, parfois également appelé *opérateur d’État*.
Un opérateur de densité pour un vecteur d’état quantique prend la forme $ \rho = \ket{\Psi} \bra{\Psi} $.
Ce concept de représentation de l’État sous la forme d’une matrice, plutôt que d’un vecteur, est souvent pratique, car il offre un moyen pratique de représenter des calculs de probabilité et permet également de décrire l’incertitude statistique, ainsi que l’incertitude du quantum. dans le même formalisme.
Les opérateurs d’État Quantum généraux, plutôt que les vecteurs, sont omniprésents dans certains domaines de l’informatique Quantum, mais ils ne sont pas nécessaires pour comprendre les principes de base du champ.
Pour le lecteur intéressé, nous vous recommandons de lire l’un des ouvrages de référence fournis dans [pour plus d’informations](xref:microsoft.quantum.more-information).

## <a name="q-gate-sequences-equivalent-to-quantum-states"></a>Q # séquences de la porte équivalentes aux États quantiques
Un dernier point intéressant la notation Quantum et le langage de programmation Q # : au début de ce document, nous avons mentionné que l’État Quantum est l’objet fondamental des informations dans quantum computing.  Il peut alors s’avérer surprenant que dans Q #, il n’y ait pas de notion d’État Quantum.  Au lieu de cela, tous les États sont décrits uniquement par les opérations utilisées pour les préparer.  L’exemple précédent est une excellente illustration.  Au lieu d’exprimer une superposition uniforme sur chaque chaîne de bits Quantum dans un registre, nous pouvons représenter le résultat sous la forme $H ^ {\otimes n} \ket{0}$.  Cette description exponentiellement plus concise de l’état présente non seulement l’avantage que nous pouvons en raison de la raison classique, mais elle définit également de manière concise les opérations nécessaires pour être propagées via la pile de logiciels pour implémenter l’algorithme.  Pour cette raison, Q # est conçu pour émettre des séquences de porte plutôt que des États quantiques. Toutefois, à un niveau théorique, les deux perspectives sont équivalentes.
