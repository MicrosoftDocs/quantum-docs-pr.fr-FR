---
title: Notes de publication de Quantum Development Kit (préversion)
description: Notes de publication de Quantum Development Kit (préversion)
author: natke
ms.author: nakersha
ms.date: 09/30/2019
ms.topic: article
uid: microsoft.quantum.relnotes
ms.openlocfilehash: c709f1eb130d37f930ffc4acc4bd663b8b8ba24a
ms.sourcegitcommit: 27c9bf1aae923527aa5adeaee073cb27d35c0ca1
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74863161"
---
# <a name="microsoft-quantum-development-kit-release-notes"></a>Notes de publication de Microsoft Quantum Development Kit

Cet article contient des informations sur chaque version de Quantum Development Kit.

Pour obtenir des instructions d’installation, consultez le [Guide d’installation](xref:microsoft.quantum.install).

Pour obtenir des instructions de mise à jour, consultez le [Guide de mise à jour](xref:microsoft.quantum.update).

## <a name="version-01019120501"></a>Version 0.10.1912.0501

*Date de publication : 5 décembre 2019*

Cette version contient ce qui suit :

- Nouvel attribut Test pour les tests unitaires Q#, voir la documentation mise à jour sur les API [ici](https://docs.microsoft.com/qsharp/api/qsharp/microsoft.quantum.diagnostics.test) et le guide de test et débogage mis à jour [ici](xref:microsoft.quantum.techniques.testing-and-debugging)
- Ajout d’une trace de la pile dans le cas d’une erreur d’exécution du programme Q#
- Prise en charge des points d’arrêt dans Visual Studio Code en raison d’une mise à jour dans l’[extension OmniSharp C# Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp)

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), le [compilateur](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), le [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) et les [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-01019111607"></a>Version 0.10.1911.1607

*Date de publication : 17 novembre 2019*

Cette version contient ce qui suit :

- Correctif des performances pour [Quantum Katas](https://github.com/Microsoft/QuantumKatas) et les notebooks Jupyter

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), le [compilateur](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), le [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) et les [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  


## <a name="version-0101911307"></a>Version 0.10.1911.307

*Date de publication : 1er novembre 2019*

Cette version contient ce qui suit :

- Mises à jour apportées aux extensions Visual Studio et Visual Studio Code pour déployer le serveur de langage comme exécutable autonome, éliminant la dépendance à la version du SDK .NET Core  
- Migration vers .NET Core 3.0
- Changement cassant de Microsoft.Quantum.Simulation.Core.IOperationFactory avec introduction de la nouvelle méthode `Fail`. Ce changement affecte uniquement les simulateurs personnalisés qui n’étendent pas SimulatorBase. Pour plus d’informations, consultez la [page sur la demande de tirage (pull request) sur GitHub](https://github.com/microsoft/qsharp-runtime/pull/59).
- Nouvelle prise en charge des attributs dépréciés

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), le [compilateur](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), le [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) et les [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-0919093002"></a>Version 0.9.1909.3002

*Date de publication : 30 septembre 2019*

Cette version contient ce qui suit :

- Nouvelle prise en charge de la complétion de code Q# dans Visual Studio 2019 (versions 16.3 et ultérieures) et Visual Studio Code
- Nouveau [Kata Quantum](https://github.com/Microsoft/QuantumKatas) pour les additionneurs quantiques

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), le [compilateur](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), le [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) et les [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-09-packagereference-0919082902"></a>Version 0.9 (*PackageReference 0.9.1908.2902*)

*Date de publication : 29 août 2019*

Cette version contient ce qui suit :

- Nouvelle prise en charge des [instructions de conjugaison](xref:microsoft.quantum.language.statements#conjugations) en Q#
- Nouvelles actions de code dans le compilateur, comme : « replace with » (remplacer par), « add documentation » (ajouter une documentation) et une mise à jour des éléments d’un tableau simple
- Ajout de commandes de modèle d’installation et de nouveau projet à l’extension Visual Studio Code
- Ajout de nouvelles variantes du combinateur ApplyIf, comme [Microsoft.Quantum.Canon.ApplyIfOne](xref:microsoft.quantum.canon.applyifone)
- [Katas Quantum](https://github.com/Microsoft/QuantumKatas) supplémentaires convertis en notebooks Jupyter
- L’extension Visual Studio nécessite désormais Visual Studio 2019

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed), le [compilateur](https://github.com/microsoft/qsharp-compiler/pulls?q=is%3Apr+is%3Aclosed), le [runtime](https://github.com/microsoft/qsharp-runtime/pulls?q=is%3Apr+is%3Aclosed), les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed) et les [katas](https://github.com/microsoft/QuantumKatas/pulls?q=is%3Apr+is%3Aclosed).  

Les changements sont résumés ici ; vous trouvez aussi des instructions pour la mise à niveau de vos programmes existants.  Pour plus d’informations sur ces changements, consultez le [blog sur le développement en Q#](https://devblogs.microsoft.com/qsharp).

## <a name="version-08-packagereference-0819071701"></a>Version 0.8 (*PackageReference 0.8.1907.1701*)

*Date de publication : 12 juillet 2019*

Cette version contient ce qui suit :

- Nouveaux emplacements d’indexation pour la division des tableaux. Pour plus d’informations, [consultez les informations de référence sur le langage](xref:microsoft.quantum.language.expressions#array-slices).
- Ajout de Dockerfile hébergé sur le [Microsoft Container Registry](https://github.com/microsoft/ContainerRegistry) ; pour plus d’informations, consultez le [dépôt IQ#](https://github.com/microsoft/iqsharp/blob/master/README.md)
- Changement cassant pour [le simulateur de traces](xref:microsoft.quantum.machines.qc-trace-simulator.intro), mise à jour les paramètres de configuration, changements de noms ; consultez le [navigateur de l’API .NET pour les noms mis à jour](https://docs.microsoft.com/dotnet/api/microsoft.quantum.simulation.simulators.qctracesimulators.qctracesimulatorconfiguration).

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) et les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

## <a name="version-07-packagereference-0719053109"></a>Version 0.7 (*PackageReference 0.7.1905.3109*)

*Date de publication : 31 mai 2019*

Cette version contient ce qui suit :
- Ajouts au langage Q# 
- Mises à jour de la bibliothèque de chimie, 
- Nouvelle bibliothèque de valeurs numériques.

Consultez la liste complète des demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) et les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Les changements sont résumés ici ; vous trouvez aussi des instructions pour la mise à niveau de vos programmes existants.  Pour plus d’informations sur ces changements, consultez le [blog sur le développement en Q#](https://devblogs.microsoft.com/qsharp).

### <a name="q-language-syntax"></a>Syntaxe du langage Q#
Cette version ajoute une nouvelle syntaxe du langage Q# :
* Ajout d’éléments nommés pour les [types définis par l’utilisateur](xref:microsoft.quantum.language.type-model#user-defined-types).  
* Les constructeurs de types définis par l’utilisateur peuvent désormais être utilisés en tant que fonctions.
* Ajout de la prise en charge de [copier-et-mettre-à-jour](xref:microsoft.quantum.language.expressions#copy-and-update-expressions) et de [appliquer-et-réaffecter]((xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols)) dans les types définis par l’utilisateur.
* Le bloc de correction pour la boucle [répéter-jusqu’à-réussite](xref:microsoft.quantum.language.statements#repeat-until-success-loop) est désormais facultatif.
* Nous prenons désormais en charge les boucles while dans les fonctions (mais pas dans les opérations).

### <a name="library"></a>Bibliothèque 

Cette version ajoute une bibliothèque de valeurs numériques : Découvrez plus d’informations sur la façon d’[utiliser la nouvelle bibliothèque de valeurs numériques](xref:microsoft.quantum.numerics.usage) et essayez les [nouveaux exemples](https://github.com/microsoft/quantum/tree/master/Numerics).  [Demande de tirage #102](https://github.com/Microsoft/QuantumLibraries/pull/102).  

Cette version réorganise, étend et met à jour la bibliothèque de chimie :
* Améliore la modularité des composants, l’extensibilité, le nettoyage de code général.  [Demande de tirage #58](https://github.com/microsoft/QuantumLibraries/pull/58).
* Ajout de la prise en charge des [fonctions d’onde à plusieurs références](xref:microsoft.quantum.chemistry.concepts.multireference), à la fois les fonctions d’onde à plusieurs références éparses et un cluster à couplage unitaire.  [Demande de tirage #110](https://github.com/Microsoft/QuantumLibraries/pull/110).
* (Merci !) Contributeur [1QBit](https://1qbit.com) ([@valentinS4t1qbit](https://github.com/ValentinS4t1qbit)) : Évaluation de l’énergie avec un ansatz variationnel. [Demande de tirage #120](https://github.com/Microsoft/QuantumLibraries/pull/120).
* Mise à jour du schéma de [Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge) vers la nouvelle [version 0.2](xref:microsoft.quantum.libraries.chemistry.schema.spec_v_0_2), ajout d’une spécification de cluster à couplage unitaire. [Problème #65](https://github.com/microsoft/QuantumLibraries/issues/65).
* Ajout de l’interopérabilité Python aux fonctions de la bibliothèque de chimie. Essayez cet [exemple](https://github.com/microsoft/Quantum/tree/master/Chemistry/PythonIntegration). [Problème #53](https://github.com/microsoft/QuantumLibraries/issues/53) [Demande de tirage #110](https://github.com/Microsoft/QuantumLibraries/pull/110).

## <a name="version-061905"></a>Version 0.6.1905

*Date de publication : 3 mai 2019*

Cette version contient ce qui suit :
- Modifications apportées au langage Q# 
- Restructuration des bibliothèques du Quantum Development Kit 
- Ajout de nouveaux exemples 
- Correction de bogues  Plusieurs demandes de tirage fermées pour les [bibliothèques](https://github.com/Microsoft/QuantumLibraries/pulls?q=is%3Apr+is%3Aclosed) et les [exemples](https://github.com/Microsoft/Quantum/pulls?q=is%3Apr+is%3Aclosed).  

Les changements sont résumés ici ; vous trouvez aussi des instructions pour la mise à niveau de vos programmes existants.  Pour plus d’informations sur ces changements, consultez devblogs.microsoft.com/qsharp.

### <a name="q-language-syntax"></a>Syntaxe du langage Q#
Cette version ajoute une nouvelle syntaxe du langage Q# :
* Ajout d’une [façon raccourcie d’exprimer des spécialisations d’opérations quantiques](xref:microsoft.quantum.language.type-model#functors) (contrôle et assistants) avec des opérateurs `+`.  L’ancienne syntaxe est dépréciée.  Les programmes qui utilisent l’ancienne syntaxe (par exemple `: adjoint`) continuent de fonctionner, mais un avertissement est généré lors de la compilation.  
* Ajout d’un nouvel opérateur pour [copier-et-mettre-à-jour](xref:microsoft.quantum.language.expressions#copy-and-update-expressions), `w/`, qui peut être utilisé pour exprimer la création d’un tableau en tant que modification d’un tableau existant.
* Ajout de l’[instruction appliquer-et-mettre-à-jour](xref:microsoft.quantum.language.statements#rebinding-of-mutable-symbols) commune, par exemple `+=`, `w/=`.
* Ajout d’un moyen de spécifier un nom abrégé pour les espaces de noms dans les [directives open](xref:microsoft.quantum.language.file-structure#open-directives).

Avec cette version, nous n’autorisons plus la spécification d’un élément de tableau sur le côté gauche d’une instruction set.  La raison en est que cette syntaxe implique que les tableaux soient modifiables, alors qu’en fait, le résultat de l’opération a toujours été la création d’un nouveau tableau avec la modification.  Au lieu de cela, une erreur de compilateur est générée avec la suggestion d’utiliser le nouvel opérateur copier-et-mettre-à-jour, `w/`, pour produire le même résultat.  

### <a name="library-restructuring"></a>Restructuration des bibliothèques
Cette version réorganise les bibliothèques pour en permettre la croissance cohérente :
* Renommage de l’espace de noms Microsoft.Quantum.Primitive en Microsoft.Quantum.Intrinsic.  Ces opérations sont implémentées par la machine cible.  L’espace de noms Microsoft.Quantum.Primitive est déprécié.  Un avertissement à l’exécution vous indique quand les programmes appellent des opérations et des fonctions qui utilisent des noms dépréciés.

* Renommage du package Microsoft.Quantum.Canon en Microsoft.Quantum.Standard.  Ce package contient des espaces de noms communs à la plupart des programmes Q#.  notamment :  
    - Microsoft.Quantum.Canon pour les opérations courantes
    - Microsoft.Quantum.Arithmetic pour les opérations arithmétiques à usage général
    - Microsoft.Quantum.Preparation pour les opérations utilisées pour préparer l’état des qubits
    - Microsoft.Quantum.Simulation pour la fonctionnalité de simulation

Avec cette modification, les programmes qui incluent une seule instruction « open » pour l’espace de noms Microsoft.Quantum.Canon peuvent rencontrer des erreurs de build si le programme référence des opérations qui ont été déplacées vers les trois autres nouveaux espaces de noms.  L’ajout des instructions open supplémentaires pour les trois nouveaux espaces de noms est un moyen simple de résoudre ce problème.  

* Plusieurs espaces de noms ont été dépréciés, car les opérations qui s’y déroulaient ont été réorganisées et déplacées vers d’autres espaces de noms. Les programmes qui utilisent ces espaces de noms continuent de fonctionner, et un avertissement au moment de la compilation indique l’espace de noms où l’opération est définie.  

* L’espace de noms Microsoft.Quantum.Arithmetic a été normalisé de façon à utiliser le type défini par l’utilisateur <xref:microsoft.quantum.arithmetic.littleendian>. Utilisez la fonction [BigEndianAsLittleEndian](xref:microsoft.quantum.arithmetic.bigendianaslittleendian) quand c’est nécessaire pour convertir au format Little Endian.  

* Les noms de plusieurs éléments appelables (fonctions et opérations) ont été modifiés de façon à être conformes au [Guide de style Q#](xref:microsoft.quantum.contributing.style).  Les anciens noms des éléments appelables sont dépréciés.  Les programmes qui utilisent les anciens éléments appelables continuent de fonctionner, avec un avertissement au moment de la compilation. 

### <a name="new-samples"></a>Nouveaux exemples

Nous avons ajouté un [exemple d’utilisation de Q# avec le pilote F#](https://github.com/Microsoft/Quantum/pull/164).  

**Merci** au contributeur suivant à notre code base ouvert sur http://github.com/Microsoft/Quantum. Ces contributions représentent des ajouts significatifs aux nombreux exemples de code Q# :

* Mathias Soeken ([@msoeken](https://github.com/msoeken)) : Synthèse des fonctions Oracle. [Demande de tirage #135](https://github.com/Microsoft/Quantum/pull/135).

### <a name="migrating-existing-projects-to-061905"></a>Migration des projets existants vers 0.6.1905.

Consultez le [Guide d’installation](xref:microsoft.quantum.install) pour mettre à jour QDK.
  
Si vous avez des projets Q# existants avec la version 0.5 de Quantum Development Kit, suivez les étapes ci-dessous pour migrer ces projets vers la version la plus récente.

    1. Les projets doivent être mis à niveau dans l’ordre.  Si vous avec une solution avec plusieurs projets, mettez à jour chaque projet dans l’ordre où ils sont référencés.
    2. À partir d’une ligne de commande, exécutez `dotnet clean` pour supprimer tous les fichiers binaires et les fichiers intermédiaires existants.
    3. Dans un éditeur de texte, modifiez le fichier .csproj pour remplacer la version de tous les `PackageReference` « Microsoft. Quantum » par la version 0.6.1904, et remplacez le nom du package « Microsoft.Quantum.Canon » par « Microsoft.Quantum.Standard », par exemple :

         ```xml
        <PackageReference Include="Microsoft.Quantum.Standard" Version="0.6.1905.301" />
        <PackageReference Include="Microsoft.Quantum.Development.Kit" Version="0.6.1905.301" />
        ```
    4. À partir de la ligne de commande, exécutez cette commande : `dotnet msbuild`  
    5. Après l’exécution de cette commande, il peut encore être nécessaire de résoudre manuellement des erreurs dues aux changements listés ci-dessus.  Dans de nombreux cas, ces erreurs sont également signalées par IntelliSense dans Visual Studio ou Visual Studio Code.
        - Ouvrez le dossier racine du projet ou la solution qui le contient dans Visual Studio 2019 ou Visual Studio Code.
        - Après avoir ouvert un fichier .qs dans l’éditeur, vous devez voir la sortie de l’extension du langage Q# dans la fenêtre de sortie.
        - Une fois que le projet a été chargé avec succès (ce qui est indiqué dans la fenêtre de sortie), ouvrez chaque fichier et résolvez manuellement tous les problèmes restants.

> [!NOTE]
> * Pour la version 0.6, le serveur de langage inclus avec Quantum Development Kit ne prend pas en charge les espaces de travail multiples.
> * Pour pouvoir travailler avec un projet dans Visual Studio Code, ouvrez le dossier racine contenant le projet lui-même et tous les projets référencés.   
> * Pour pouvoir travailler avec une solution dans Visual Studio, tous les projets contenus dans la solution doivent se trouver dans le même dossier que la solution ou dans un de ses sous-dossiers.  
> * Les références entre les projets migrés vers la version 0.6 et ultérieure, et les projets qui utilisent des versions plus anciennes du package ne sont **pas** prises en charge.

## <a name="version-051904"></a>Version 0.5.1904

*Date de publication : 15 avril 2019*

Cette version contient des correctifs de bogues.


## <a name="version-051903"></a>Version 0.5.1903

*Date de publication : 27 mars 2019*

Cette version contient ce qui suit :

- Ajout de la prise en charge de Jupyter Notebook, qui offre un excellent moyen d’en savoir plus sur Q#.  [Consultez les nouveaux exemples Jupyter Notebook et découvrez comment écrire vos propres notebooks](xref:microsoft.quantum.install). 

- Ajout à la bibliothèque Canon d’une arithmétique d’additionneur d’entiers.  Consultez aussi un notebook Jupyter qui [décrit comment utiliser les nouveaux additionneurs d’entiers](https://github.com/microsoft/Quantum/blob/master/samples/arithmetic/AdderExample.ipynb).

- Résolution du bogue pour le problème de DumpRegister signalé par la communauté ([#148](https://github.com/Microsoft/Quantum/issues/148)).

- Ajout de la possibilité de retourner depuis une [instruction using](xref:microsoft.quantum.language.statements).

- Reconception du [Guide de mise en route](xref:microsoft.quantum.install)


## <a name="version-051902"></a>Version 0.5.1902

*Date de publication : 27 février 2019*

Cette version contient ce qui suit :

- Ajoute la prise en charge d’un hôte Python multiplateforme.  Le package `qsharp` pour Python facilite la simulation des opérations et des fonctions Q# dans Python. Découvrez plus d’informations sur l’[interopérabilité Python](xref:microsoft.quantum.install). 

- Les extensions Visual Studio et Visual Studio Code prennent désormais en charge le renommage des symboles (par exemple les fonctions et les opérations).

- L’extension Visual Studio peut désormais être installée sur Visual Studio 2019.

## <a name="version-041901"></a>Version 0.4.1901

*Date de publication : 30 janvier 2019*

Cette version contient ce qui suit :

- Ajout de la prise en charge d’un nouveau type primitif, BigInt, qui représente un entier signé d’une taille arbitraire.  Découvrez plus d’informations sur le [type BigInt](xref:microsoft.quantum.language.type-model).
- Ajoute un nouveau simulateur Toffoli, un simulateur rapide spécial qui peut simuler des opérations quantiques X, CNOT et X multicontrôlées avec un très grand nombre de qubits.  Découvrez plus d’informations sur le [simulateur Toffoli](xref:microsoft.quantum.machines.toffoli-simulator).
- Ajoute un estimateur de ressources simple qui estime les ressources nécessaires pour exécuter une instance donnée d’une opération Q# sur un ordinateur quantique.  Découvrez plus d’informations sur l’[estimateur de ressources](xref:microsoft.quantum.machines.resources-estimator).


## <a name="version-0318112802"></a>Version 0.3.1811.2802

*Date de publication : 28 novembre 2018*

Même si notre extension VS Code ne l’utilisait pas, elle a été marquée et supprimée de la Place de marché lors de [l’élimination des extensions](https://code.visualstudio.com/blogs/2018/11/26/event-stream) liées au package NPM `event-stream`. Cette version supprime toutes les dépendances du runtime qui pouvaient provoquer le déclenchement d’indicateurs « rouges » par l’extension.

Si vous avez déjà installé l’extension, vous devez la réinstaller en accédant à l’extension [Microsoft Quantum Development Kit pour Visual Studio Code](vscode:extension/quantum.quantum-devkit-vscode) sur Visual Studio Marketplace et en cliquant sur Install (Installer). Nous sommes désolés pour ce désagrément.


## <a name="version-0318111511"></a>Version 0.3.1811.1511

*Date de publication : 20 novembre 2018*

Cette version corrige un bogue qui empêchait certains utilisateurs de charger correctement l’extension Visual Studio.

Si vous effectuez une mise à niveau à partir d’une version 0.2 de Quantum Development Kit, découvrez plus d’informations sur les [modifications du langage Q# et la migration de votre programme Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-031811203"></a>Version 0.3.1811.203

*Date de publication : 2 novembre 2018*

Cette version inclut quelques correctifs de bogues, notamment :

* L’appel de `DumpMachine` peut modifier l’état du simulateur dans certaines situations.
* Suppression des avertissements de compilation lors de la génération de projets avec une version de .NET Core antérieure à 2.1.403.
* Toilettage de la documentation, en particulier les info-bulles affichées lors du pointage avec la souris dans VS Code ou Visual Studio.

Si vous effectuez une mise à niveau à partir d’une version 0.2 de Quantum Development Kit, découvrez plus d’informations sur les [modifications du langage Q# et la migration de votre programme Q#](xref:microsoft.quantum.relnotes.migration-0-3).

## <a name="version-0318102508"></a>Version 0.3.1810.2508

*Date de publication : 29 octobre 2018*

Cette version comprend de nouvelles fonctionnalités du langage et une expérience de développement améliorée :

* Cette version comprend un serveur de langage pour Q# ainsi que les intégrations du client pour Visual Studio et Visual Studio Code. Ceci active un nouvel ensemble de fonctionnalités IntelliSense ainsi qu’un feedback en direct au moment de la frappe sous forme de soulignements ondulés des erreurs et des avertissements. 
* Cette mise à jour améliore considérablement les messages de diagnostic en général, avec une navigation facile et des plages précises pour les diagnostics, et des détails supplémentaires dans les informations affichées dans les info-bulles.
* Le langage Q# a été étendu de manière à unifier les façons dont les développeurs peuvent effectuer les opérations courantes, et à apporter de nouvelles améliorations aux fonctionnalités du langage pour exprimer les calculs quantiques de façon plus puissante.  Cette version apporte un certain nombre de changements cassants du langage Q#.   

Découvrez plus d’informations sur les [modifications apportées au langage Q# et sur la migration de votre programme Q#](xref:microsoft.quantum.relnotes.migration-0-3).

Cette version comprend également une nouvelle bibliothèque de chimie quantique :

* La bibliothèque de chimie contient de nouvelles fonctionnalités de simulation hamiltonienne, notamment :
    - Des intégrateurs Trotter-Suzuki d’ordre de parité arbitraire pour améliorer la précision de la simulation.
    - Une technique de simulation de qubitisation avec des optimisations spécifiques à la chimie pour réduire la complexité des portes $T$.
* Un nouveau schéma open source, appelé « schéma Broombridge » (en référence à un [lieu emblématique](https://en.wikipedia.org/wiki/Broom_Bridge) célébré comme lieu de naissance des opérateurs hamiltoniens), est introduit pour l’importation de représentations de molécules et leur simulation.
* Plusieurs représentations chimiques définies avec le schéma Broombridge sont fournies.  Ces modèles ont été générés par [NWChem](http://www.nwchem-sw.org/), un outil de calcul haute performance open source utilisé dans la chimie.
* Des tutoriels et des exemples expliquent comment utiliser la bibliothèque de chimie et les modèles de données Broombridge pour :
    - Construire des opérateurs hamiltoniens simples avec la bibliothèque de chimie
    - Visualiser les énergies fondamentales et excitées de Lithium Hydride avec l’estimation des phases.
    - Effectuer des estimations de ressources pour la simulation en chimie quantique.
    - Estimer les niveaux d’énergie des molécules représentées par le schéma Broombridge.
* La documentation explique comment utiliser NWChem pour générer des modèles chimiques supplémentaires pour la simulation quantique avec Q#.

Découvrez plus d’informations sur la [bibliothèque de chimie du Quantum Development Kit](xref:microsoft.quantum.chemistry.concepts.intro).

Avec la nouvelle bibliothèque de chimie, nous mettons à part les bibliothèques dans un nouveau dépôt GitHub, [Microsoft/QuantumLibraries](https://github.com/Microsoft/QuantumLibraries).  Les exemples restent dans le dépôt [Microsoft/Quantum](https://github.com/Microsoft/Quantum).  Les contributions aux deux dépôts sont les bienvenues !

Cette version comprend des correctifs de bogues et des fonctionnalités pour des problèmes signalés par la communauté :

* IntelliSense pour Q# ? ([UserVoice](https://quantum.uservoice.com/forums/906943/suggestions/32656918)).
* Fichiers .qs ([UserVoice](https://quantum.uservoice.com/forums/906097/suggestions/32593049)).
* Amélioration du message d’erreur quand des accolades sont abrégées dans une instruction if ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/34718518)).
* Prise en charge de la déconstruction de tuple à (re)liaison modifiable ([UserVoice](https://quantum.uservoice.com/forums/906208/suggestions/35020444)).
* Erreur lors de l’exécution du BitFlipCode fourni ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).
* H2SimulationGUI affiche parfois des pics élevés ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34668370)).

### <a name="community-contributions"></a>Contributions de la communauté

**Merci** aux contributeurs suivants à notre code base ouvert sur http://github.com/Microsoft/Quantum. Ces contributions représentent des ajouts significatifs aux nombreux exemples de code Q# :

* Rolf Huisman ([@RolfHuisman](https://github.com/RolfHuisman)) : Amélioration de l’expérience des développeurs QASM/Q# grâce à la création d’un traducteur de QASM vers Q#. [Demande de tirage #58](https://github.com/Microsoft/Quantum/pull/58).

* Andrew Helwer ([@ahelwer](https://github.com/ahelwer)) :  A contribué via un exemple d’implémentation du jeu CHSH, un jeu quantique relatif à la non-localité.  [Demande de tirage #84](https://github.com/Microsoft/Quantum/pull/84).

Merci également à Rohit Gupta ([@guptarohit](https://github.com/guptarohit),[Demande de tirage #90](https://github.com/Microsoft/quantum/pull/90)), à Tanaka Takayoshi ([@tanaka-takayoshi](https://github.com/tanaka-takayoshi),[Demande de tirage #289](https://github.com/MicrosoftDocs/quantum-docs-pr/pull/289)) et à Lee James O’Riordan ([@mlxd](https://github.com/mlxd),[Demande de tirage #96](https://github.com/Microsoft/Quantum/pull/96)) pour leur travail visant à améliorer le contenu pour nous tous via des corrections de la documentation, de l’orthographe et des fautes de frappe ! 

## <a name="version-021809701"></a>Version 0.2.1809.701

*Date de publication : 10 septembre 2018*

Cette version comprend des correctifs de bogues pour des problèmes signalés par la communauté. Il s’agit notamment de :

* Impossible d’utiliser l’opérateur de décalage ([GitHub](https://github.com/Microsoft/Quantum/issues/75)).
* `DumpMachine` / `DumpRegister` échoue sur `QCTraceSimulator` lors de l’affichage sur la console ([UserVoice](https://quantum.uservoice.com/forums/906946/suggestions/34709680)).
* Autorisation de l’allocation de 0 qubit ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34768069-allow-allocating-0-qubits)).
* `AssertQubitState` nécessite un appel de Complex() explicite ([UserVoice](https://quantum.uservoice.com/forums/906208-q-language/suggestions/34713733-assertqubitstate-requires-explicit-complex-call)).
* L’opération `Measure` retourne toujours `One` sur macOS ([UserVoice](https://quantum.uservoice.com/forums/906940/suggestions/35008546)).

Merci ! 

## <a name="version-0218063001"></a>Version 0.2.1806.3001

*Date de publication : 30 juin 2018*

Cette version est seulement un correctif rapide pour le [problème #48 signalé sur GitHub](https://github.com/Microsoft/Quantum/issues/48) (La compilation Q# échoue si le nom d’utilisateur contient un espace). Suivez les mêmes instructions de mise à jour que pour `0.2.1806.1503` avec la nouvelle version correspondante (`0.2.1806.3001-preview`).

## <a name="version-0218061503"></a>Version 0.2.1806.1503

*Date de publication : 22 juin 2018*

Cette version comprend plusieurs contributions de la communauté, et offre une expérience de débogage améliorée et de meilleures performances.  Plus précisément :

* Améliorations des performances sur les petites et les grandes simulations pour la machine cible de QuantumSimulator.
* Amélioration des fonctionnalités de débogage.
* Contributions de la communauté pour des correctifs de bogues, de nouvelles fonctions d’assistance, des opérations et de nouveaux exemples.

### <a name="performance-improvements"></a>Amélioration des performances

Cette mise à jour comprend des améliorations significatives des performances pour la simulation de grands nombres et de petits nombres de qubits pour toutes les machines cibles.  Cette amélioration est facilement visible avec la simulation H<sub>2</sub>, qui est un exemple standard du Quantum Development Kit.

### <a name="improved-debugging-functionality"></a>Amélioration des fonctionnalités de débogage

Cette mise à jour ajoute de nouvelles fonctionnalités de débogage :
* Ajout de deux nouvelles opérations, @"microsoft.quantum.extensions.diagnostics.dumpmachine" et @"microsoft.quantum.extensions.diagnostics.dumpregister", qui produisent des informations sur la fonction d’onde (wave) à propos de la machine quantique cible à un moment donné.  
* Dans Visual Studio, la probabilité de mesurer un $\ket{1}$ sur un qubit est désormais montrée automatiquement dans la fenêtre de débogage pour la machine cible de QuantumSimulator.
* Dans Visual Studio, l’affichage des propriétés des variables dans les fenêtres de débogage **Automatique** et **Variables locales** a été amélioré. 

Découvrez plus d’informations sur [les tests et le débogage](xref:microsoft.quantum.techniques.testing-and-debugging).

### <a name="community-contributions"></a>Contributions de la communauté

La communauté des codeurs en Q# s’accroît : nous sommes très contents de voir les premières bibliothèques et les premiers exemples qui ont été soumis par les utilisateurs qui y ont contribué à notre code base ouvert sur http://github.com/Microsoft/quantum.  **Un grand merci** aux contributeurs suivants :
* Mathias Soeken ([@msoeken](https://github.com/msoeken)) : a fourni un exemple définissant une méthode de synthèse logique basée sur une transformation qui construit des réseaux Toffoli pour implémenter une permutation donnée. Le code est écrit entièrement avec des fonctions et des opérations Q#.  [Demande de tirage #41](https://github.com/Microsoft/Quantum/pull/41).
* RolfHuisman ([@RolfHuisman](https://github.com/RolfHuisman)) : Rolf Huisman (Microsoft MVP) a fourni un exemple qui génère du code QASM plat à partir du code Q# pour une classe restreinte de programmes qui n’ont pas un flux de contrôle classique et des opérations quantiques limitées. [Demande de tirage #59](https://github.com/Microsoft/Quantum/pull/59)
* Sarah Kasier ([@crazy4pi314](https://github.com/crazy4pi314)) : a aidé à améliorer notre code base en soumettant une fonction de bibliothèque pour les opérations contrôlées. [Demande de tirage #53](https://github.com/Microsoft/Quantum/pull/53)
* Jessica Lemieux ([@Lemj3111](https://github.com/Lemj3111)) : a corrigé @"microsoft.quantum.canon.quantumphaseestimation" et a créé de nouveaux test unitaires.  [Demande de tirage #54](https://github.com/Microsoft/Quantum/pull/54)
* Tama McGlinn ([@TamaHobbit](https://github.com/TamaHobbit)) : a nettoyé l’exemple de téléportation en vérifiant que l’instance de QuantumSimulator est bien supprimée. [Demande de tirage #20](https://github.com/Microsoft/Quantum/pull/20)

En outre, un grand **merci** à ces ingénieurs logiciels Microsoft des contributeurs de l’équipe des services d’ingénierie commerciale qui ont apporté des modifications importantes à notre documentation pendant leur hackathon.  Leurs modifications ont considérablement amélioré la clarté et l’expérience d’intégration pour nous tous :
* Sascha Corti
* Mihaela Curmei
* John Donnelly
* Kirill Logachev
* Jan Pospisil
* Anita Ramanan
* Frances Tibble
* Alessandro Vozza

### <a name="update-existing-projects"></a>Mettre à jour des projets existants

Cette version est entièrement compatible avec les versions antérieures. Il vous suffit de mettre à jour les packages NuGet dans vos projets vers la version `0.2.1806.1503-preview` et de procéder à une **regénération complète** pour garantir que tous les fichiers intermédiaires sont regénérés.

Dans Visual Studio, suivez les instructions normales sur la façon de [mettre à jour un package](https://docs.microsoft.com/nuget/tools/package-manager-ui#updating-a-package).

Pour mettre à jour les modèles de projet pour la ligne de commande, exécutez la commande suivante :
```
dotnet new -i "Microsoft.Quantum.ProjectTemplates::0.2.1806.1503-preview"
```

Après l’exécution de cette commande, tous les nouveaux projets créés avec `dotnet new <project-type> -lang Q#` utilisent automatiquement cette version du Quantum Development Kit.

Pour mettre à jour un projet existant afin d’utiliser la version la plus récente, exécutez la commande suivante à partir du répertoire de chaque projet :

```
dotnet add package Microsoft.Quantum.Development.Kit -v "0.2.1806.1503-preview"
dotnet add package Microsoft.Quantum.Canon -v "0.2.1806.1503-preview"
```

Si un projet existant utilise également l’intégration XUnit pour les tests unitaires, une commande similaire peut être utilisée pour mettre à jour ce package également :
```
dotnet add package Microsoft.Quantum.Xunit -v "0.2.1806.1503-preview"
```

Selon la version de XUnit que votre projet de test utilise, il peut aussi être nécessaire de mettre à jour XUnit vers 2.3.1 :
```
dotnet add package xunit -v "2.3.1" 
```

Après la mise à jour, veillez à supprimer tous les fichiers temporaires générés par la version précédente en procédant comme suit :
```
dotnet clean 
```

### <a name="known-issues"></a>Problèmes connus

Aucun autre problème connu à signaler.


## <a name="version-0218022202"></a>Version 0.2.1802.2202

*Date de publication : 26 février 2018*

Cette version offre la charge du développement sur un plus grand nombre de plateformes, l’interopérabilité des langages et des améliorations des performances. Plus précisément :

- Prise en charge du développement basé sur macOS et Linux. 
- Compatibilité .NET Core, notamment la prise en charge de Visual Studio Code sur plusieurs plateformes.
- Une licence open source complète pour les bibliothèques du Quantum Development Kit.
- Amélioration des performances du simulateur sur les projets nécessitant 20 qubits ou plus.
- Interopérabilité avec le langage Python (préversion disponible sur Windows).

### <a name="net-editions"></a>Éditions de .NET

La plate-forme .NET est disponible via deux éditions différentes : le .NET Framework qui fourni avec Windows, et le .NET Core open source, qui est disponible sur Windows, macOS et Linux.
Avec cette version, la plupart des composants du Quantum Development Kit sont fournis en tant que bibliothèques pour .NET Standard, l’ensemble des classes communes à .NET Framework et à .NET Core.
Ces bibliothèques sont donc compatibles avec les versions récentes de .NET Framework ou de .NET Core.

Ainsi, pour faire en sorte que les projets écrits avec le Quantum Development Kit soient aussi portables que possible, nous recommandons que les projets de bibliothèque écrits avec le Quantum Development Kit ciblent .NET Standard, et que les applications console ciblent .NET Core.
Comme les versions précédentes du Quantum Development Kit ne prenaient en charge que .NET Framework, il peut être nécessaire de migrer vos projets existants. Pour plus d’informations sur la procédure à suivre, reportez-vous à ce qui est décrit ci-dessous.

### <a name="project-migration"></a>Migration des projets

Les projets créés avec des versions précédentes du Quantum Development Kit continueront de fonctionner tant que vous ne mettez pas à jour les packages NuGet qui y sont utilisés. Pour migrer le code existant vers la nouvelle version, effectuez les étapes suivantes :
1. Créez un projet .NET Core en utilisant le type approprié de modèle de projet Q# (Projet d’application, de bibliothèque ou de test).
2. Copiez les fichiers .qs et .cs/.fs existants de l’ancien projet vers le nouveau projet (en utilisant Ajouter > Élément existant). Ne copiez pas le fichier AssemblyInfo.cs.
3. Générez et exécutez le nouveau projet.

Notez que l’opération RandomWalkPhaseEstimation de l’espace de noms Microsoft.Quantum.Canon a été déplacée dans l’espace de noms Microsoft.Research.Quantum.RandomWalkPhaseEstimation dans le dépôt [Microsoft/Quantum-NC](https://github.com/microsoft/quantum-nc).

### <a name="known-issues"></a>Problèmes connus

- L’option `--filter` pour `dotnet test` ne fonctionne pas correctement pour les tests écrits en Q#.
  Par conséquent, les tests unitaires individuels ne peuvent pas être exécutés dans Visual Studio Code ; nous recommandons d’utiliser `dotnet test` sur la ligne de commande pour réexécuter tous les tests.

## <a name="version-0118011707"></a>Version 0.1.1801.1707

*Date de publication : 18 janvier 2018*

Cette version corrige certains problèmes signalés par la communauté. En l’occurrence :

- Le simulateur fonctionne désormais avec les processeurs plus anciens non compatibles AVX.
- Les paramètres décimaux régionaux n’entraînent pas l’échec de l’analyseur Q#.
- L’opération primitive `SignD` retourne désormais `Int` au lieu de `Double`.


## <a name="version-011712901"></a>Version 0.1.1712.901

*Date de publication : 11 décembre 2017*

### <a name="known-issues"></a>Problèmes connus

#### <a name="hardware-and-software-requirements"></a>Configuration matérielle et logicielle requise

- Le simulateur inclus dans le Quantum Development Kit nécessite une installation 64 bits de Microsoft Windows pour fonctionner.
- Le simulateur quantique de Microsoft, installé avec le Quantum development kit, utilise les extensions AVX (Advanced Vector Extensions) et nécessite un processeur compatible AVX. Les processeurs Intel livrés au premier trimestre 2011 (Sandy Bridge) ultérieurement prennent en charge AVX. Nous évaluons la prise en charge des processeurs antérieurs et nous sommes susceptibles d’annoncer des informations détaillées ultérieurement.

#### <a name="project-creation"></a>Création de projet

- Quand vous créez une solution (.sln) qui utilise Q#, elle doit se trouver dans un répertoire d’un niveau supérieur à chaque projet (.csproj) de cette solution. À la création d’une solution, vous pouvez le faire en vérifiant que la case « Créer le répertoire pour la solution » de la boîte de dialogue « Nouveau projet » est cochée. Si vous ne procédez pas ainsi, vous devez installer manuellement les packages NuGet du Quantum Development Kit .

#### <a name="q"></a>Q#

- IntelliSense n’affiche pas les erreurs appropriées pour le code Q#. Vérifiez que vous affichez les erreurs de build dans la liste d’erreurs Visual Studio pour voir les erreurs Q# correctes. Notez également que les erreurs Q# ne s’affichent pas tant que vous n’avez pas effectué une build.
- L’utilisation d’un tableau modifiable dans une application partielle peut entraîner un comportement inattendu.
- La liaison d’un tableau non modifiable à un tableau modifiable (let a = b, où b est un tableau modifiable) peut entraîner un comportement inattendu.
- Le profilage, la couverture du code et d’autres plug-ins de Visual Studio peuvent ne pas toujours compter les lignes et les blocs Q# avec précision.
- Le compilateur Q# ne vérifie pas les chaînes interpolées. Il est possible de créer des erreurs de compilation C# en orthographiant incorrectement des noms de variables ou en utilisant des expressions dans des chaînes interpolées Q#.

#### <a name="simulation"></a>Simulation

- Le simulateur quantique utilise OpenMP pour paralléliser l’algèbre linéaire nécessaire. Par défaut, OpenMP utilise tous les threads matériels disponibles, ce qui signifie que les programmes avec un petit nombre de qubits s’exécutent souvent lentement, car la coordination nécessaire va prendre le pas sur le travail réel. Vous pouvez résoudre ce problème en définissant la variable d’environnement OMP_NUM_THREADS sur une valeur peu élevée. En règle générale, 1 thread convient pour jusqu’à environ 4 qubits, puis un thread supplémentaire par qubit convient, bien que cela dépende fortement de votre algorithme.

#### <a name="debugging"></a>Débogage

- F11 (pas à pas détaillé) ne fonctionne pas dans le code Q#.
- La mise en surbrillance du code dans le code Q# à un point d’arrêt ou une pause à une seule étape est parfois inexacte. La ligne correcte est mise en surbrillance mais parfois, la mise en surbrillance commence et se termine à des colonnes incorrectes sur la ligne.

#### <a name="testing"></a>Test

- Les tests doivent être exécutés en mode 64 bits. Si vos tests échouent avec BadImageFormatException, accédez au menu Tester et sélectionnez Paramètres de test > Architecture de processeur par défaut > X64.
- Certains tests prennent un temps assez long (possiblement jusqu’à 5 minutes en fonction de votre ordinateur) pour s’exécuter. Ceci est normal, car certains tests utilisent plus de vingt qubits ; notre plus grand test s’exécute actuellement sur 23 qubits.

#### <a name="samples"></a>Exemples

- Sur certaines machines, certains petits exemples peuvent s’exécuter lentement, sauf si la variable d’environnement OMP_NUM_THREADS est définie sur « 1 ». Consultez également la note de publication sous « Simulation ».

#### <a name="libraries"></a>Bibliothèques

- Il existe une hypothèse implicite selon laquelle les qubits passés à une opération dans des arguments différents sont tous distincts. Par exemple, toutes les opérations de la bibliothèque (et toutes celles des simulateurs) supposent que les deux qubits passés à un NOT contrôlé sont des qubits différents. Une violation de cette hypothèse peut entraîner un comportement imprévisible. Il est possible de tester ceci en utilisant le simulateur de traces de l’ordinateur quantique.
- La fonction Microsoft.Quantum.Bind peut ne pas fonctionner comme attendu dans tous les cas.
- Dans l’espace de noms Microsoft.Quantum.Extensions.Math, la fonction SignD retourne un type Double au lieu d’un type Int, bien que la fonction System.Math.Sign sous-jacente retourne toujours un entier. Il est possible de comparer le résultat à « 1,0 », à « -1,0 » et à « 0,0 », car ces entiers doubles ont tous des représentations binaires exactes.
