---
title: De bout en bout avec NWChem | Microsoft Docs
description: De bout en bout avec NWChem docs
author: cgranade
ms.author: chgranad@microsoft.com
ms.date: 10/23/2018
uid: microsoft.quantum.chemistry.examples.endtoend
ms.openlocfilehash: 8f727ea4599e06b41ced561c624c4e773b9887d9
ms.sourcegitcommit: 8becfb03eb60ba205c670a634ff4daa8071bcd06
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73185815"
---
# <a name="end-to-end-with-nwchem"></a>De bout en bout avec NWChem #

Dans cette page, nous allons passer en revue un exemple d’obtention du nombre de portes pour la simulation de la chimie quantique, à partir d’un pont d’entrée [NWChem](http://www.nwchem-sw.org/index.php/Main_Page) .
Avant de poursuivre avec cet exemple, assurez-vous que vous avez installé l’ancrage, conformément au [Guide d’installation et de validation](xref:microsoft.quantum.chemistry.concepts.installation).

Pour plus d'informations :
- [Structure des ponts d’entrée NWChem](https://github.com/nwchemgit/nwchem/wiki/Getting-Started#input-file-structure)
    - [Commandes de pont d’entrée à utiliser avec le kit de développement quantique](https://github.com/nwchemgit/nwchem/tree/master/contrib/quasar)
- [Installation de la bibliothèque chimie et des dépendances](xref:microsoft.quantum.chemistry.concepts.installation)
- [Comptage des ressources](xref:microsoft.quantum.chemistry.examples.resourcecounts)

> [!NOTE]
> Cet exemple nécessite l’exécution de Windows PowerShell Core.
> Téléchargez PowerShell Core pour Windows, macOS ou Linux sur https://github.com/PowerShell/PowerShell.

## <a name="importing-required-powershell-modules"></a>Importation des modules PowerShell requis ##

Si vous ne l’avez pas déjà fait, clonez le [référentiel Microsoft/Quantum](https://github.com/Microsoft/Quantum), qui contient des exemples et des utilitaires pour travailler avec le kit de développement Quantum :

```powershell
git clone https://github.com/Microsoft/Quantum
```

Une fois que vous avez cloné `Microsoft/Quantum`, effectuez des `cd` dans le dossier `utilities/` et importez le module PowerShell pour l’utilisation de Dockr et NWChem :

```powershell
cd utilities
Import-Module InvokeNWChem.psm1
```

> [!NOTE]
> Par défaut, Windows empêche l’exécution de scripts ou de modules comme mesure de sécurité.
> Pour autoriser l’exécution de modules tels que `Invoke-NWChem.psm1` sous Windows, vous devrez peut-être modifier la stratégie d’exécution.
> Pour ce faire, exécutez la commande `Set-ExecutionPolicy` :
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope Process
> ```
> La stratégie d’exécution est ensuite rétablie lorsque vous quittez PowerShell.
> Si vous souhaitez enregistrer la stratégie d’exécution, utilisez une valeur différente pour `-Scope`:
> ```powershell
> Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```

La commande `Convert-NWChemToBroombridge` doit maintenant être disponible :

```powershell
Get-Command -Module InvokeNWChem
```

Ensuite, nous allons importer la commande `Get-GateCount` fournie avec l’exemple **GetGateCount** .
Pour plus d’informations, consultez les [instructions fournies avec l’exemple](https://github.com/Microsoft/Quantum/tree/master/Chemistry/GetGateCount).
Ensuite, exécutez la commande suivante, en remplaçant `<runtime>` par `win10-x64`, `osx-x64`ou `linux-x64`, en fonction de votre système d’exploitation :

```powershell
cd ../Chemistry/GetGateCount
dotnet publish --self-contained -r <runtime>
Import-Module ./bin/Debug/netcoreapp2.1/<runtime>/publish/get-gatecount.dll
```

La commande `Get-GateCount` doit maintenant être disponible :

```powershell
Get-Command Get-GateCount
```

## <a name="input-decks"></a>Jeux d’entrée ##

Le package NWChem prend un fichier texte appelé « _pont d’entrée_ » qui spécifie un problème de chimie quantique à résoudre, ainsi que d’autres paramètres tels que les paramètres d’allocation de mémoire.
Pour cet exemple, nous allons utiliser l’un des jeux de données prédéfinis fournis avec NWChem.
Tout d’abord, clonez le [référentiel nwchemgit/nwchem](https://github.com/nwchemgit/nwchem):

> [!NOTE]
> Étant donné qu’il s’agit d’un référentiel très volumineux, nous pouvons effectuer un clone superficiel pour économiser de la bande passante et de l’espace disque à l’aide de l’argument `--depth 1`.
> Toutefois, cette option est facultative.
> Le clonage fonctionne parfaitement sans `--depth 1`.

```powershell
git clone https://github.com/nwchemgit/nwchem --depth 1
```

Le référentiel de `nwchemgit/nwchem` est fourni avec une variété de jeux d’entrée destinés à être utilisés avec le kit de développement quantique, listé dans le [dossier`QA/chem_library_tests`](https://github.com/nwchemgit/nwchem/tree/master/QA/chem_library_tests).
Pour cet exemple, nous allons utiliser le jeu de `H4` d’entrée :

```powershell
cd nwchem/QA/chem_library_tests/H4
Get-Content h4_sto6g_0.000.nw
```

La molécule en question est un système de 4 atomes d’hydrogène organisés dans une certaine géométrie qui dépend d’un angle, le paramètre `alpha` comme indiqué dans le nom `h4_sto6g_alpha.nw` du jeu. H4 est un [test moléculaire](https://onlinelibrary.wiley.com/doi/abs/10.1002/qua.560180511) connu pour la chimie de calcul depuis les années 1970. Le paramètre `sto6g` indique que le jeu met en œuvre une représentation en ce qui concerne un Slater orbital, en particulier une représentation par rapport à une [base arrêt-ng définie](https://en.wikipedia.org/wiki/STO-nG_basis_sets) avec 6 fonctions de base gaussienne. Ce pont d’entrée contient en outre plusieurs instructions pour le NWChem tenseur Contracting Engine (TCE) qui dirige NWChem pour produire les informations nécessaires à l’interopérabilité avec le kit de développement Quantum :

```
...
set tce:print_integrals T
set tce:qorb 18
set tce:qela  9
set tce:qelb  9
```

## <a name="producing-and-consuming-broombridge-output-from-nwchem"></a>Production et consommation de la sortie Broombridge à partir de NWChem ##

Nous disposons maintenant de tout ce dont nous avons besoin pour produire et consommer des documents Broombridge.
Pour exécuter NWChem et produire un document Broombridge pour le jeu d’entrée `h4_sto6g_0.000.nw`, exécutez `Convert-NWChemToBroombridge`:

> [!NOTE]
> La première fois que vous exécutez cette commande, Dockr télécharge l’image de `nwchemorg/nwchem-qc` pour vous.
> Cela peut prendre un peu de temps, en fonction de la vitesse de votre connexion, ce qui vous donne la possibilité d’obtenir une tasse de café.

```powershell
Convert-NWChemToBroombridge h4_sto6g_0.000.nw 
```

Cela produira un document Broombridge appelé `h4_sto6g_0.000.yaml` que nous pouvons utiliser avec `Get-GateCount`:

```powershell
Get-GateCount -Format YAML h4_sto6g_0.000.yaml
```

Vous devez maintenant voir la sortie de la console qui contient l’estimation des ressources, comme T-Count, le nombre de rotations, le nombre de CNOTIN, etc. pour diverses méthodes de simulation de Quantum :

```powershell 
IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Trotter
TCount              : 0
RotationsCount      : 92
CNOTCount           : 520
ElapsedMilliseconds : 327

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Qubitization
TCount              : 438
RotationsCount      : 516
CNOTCount           : 2150
ElapsedMilliseconds : 528

IntegralDataPath    : C:\Users\martinro\REPOS\nwchem\qa\chem_library_tests\h4\h4_sto6g_0.000.yaml
HamiltonianName     : hamiltonian_0
SpinOrbitals        : 8
Method              : Optimized Qubitization
TCount              : 3540
RotationsCount      : 18
CNOTCount           : 7932
ElapsedMilliseconds : 721
```

Il y a beaucoup de choses à faire à partir d’ici : 
- Essayez différents jeux d’entrée prédéfinis, par exemple, en modifiant le paramètre `alpha` dans `h4_sto6g_alpha.nw`, 
- Essayez de modifier les jeux de cartes en modifiant directement les jeux NWChem, par exemple, en explorant les modèles de `STO-nG` pour différents choix de n, 
- Essayez d’autres jeux d’entrée NWChem prédéfinis qui sont disponibles sur `nwchem/qa/chem_library_tests`,
- Essayez une suite de tests d’évaluation Broombridge YAML prédéfinis qui ont été générés à partir de NWChem et qui sont disponibles dans le cadre du [référentiel Microsoft/Quantum](https://github.com/Microsoft/Quantum/tree/master/Chemistry/IntegralData/YAML). Ces tests d’évaluation sont les suivants : 
    - petites molécules telles que l’hydrogène moléculaire (H2), le beryllium (a), le lithium-hydrure (LiH),
    - des molécules plus grandes telles que l’ozone (O3), bêta-carotène, cytosine et bien d’autres. 
- Essayez les flèches graphiques frontales [EMSL](https://arrows.emsl.pnnl.gov/api/qsharp_chem) qui intègrent une interface au Microsoft Quantum Development Kit. 


## <a name="producing-broombridge-output-from-emsl-arrows"></a>Génération de la sortie Broombridge à partir de flèches EMSL ##

Pour vous familiariser avec les flèches EMSL front end basées sur le Web, accédez à un navigateur [ici](https://arrows.emsl.pnnl.gov/api/qsharp_chem). 

> [!NOTE]
> L’exécution des flèches EMSL dans un navigateur Web requiert l’activation de JavaScript. Pour plus d’informations sur l’activation de JavaScript dans votre navigateur, reportez-vous à ces [instructions](https://www.enable-javascript.com/) . 

Tout d’abord, entrez une molécule dans la zone de requête qui indique ``Enter an esmiles, esmiles reaction, or other Arrows input, then push the "Run Arrows" button.`` 

Vous pouvez entrer de nombreuses molécules par leur nom commun, tel que « caféine » au lieu de « 1, 3, 7-Trimethylxanthine ». 

Ensuite, cliquez sur le bouton qui indique ``theory{qsharp_chem}``. Cela remplira davantage la zone de requête avec une instruction qui indique à l’exécution d’exporter la sortie au format Broombridge YAML. 

À présent, Clock on ``Run Arrows``. Selon la taille de l’entrée, cette opération peut prendre un certain temps. Ou, au cas où le modèle particulier a déjà été calculé précédemment, il peut être fait extrêmement rapide, car il ne se limite qu’à une recherche dans une base de données. Dans les deux cas, vous êtes dirigé vers une nouvelle page qui contient une multitude d’informations sur l’exécution particulière de NWChem sur le jeu de données spécifié par votre entrée. 

Vous pouvez télécharger et enregistrer le fichier Broombridge YAML à partir de la section qui commence par l’en-tête suivant : 
```powershell
+==================================================+
||              Molecular Calculation             ||
+==================================================+

Id     = 48443

NWOutput = Link to NWChem Output (download)

Datafiles:
qsharp_chem.yaml-2018-10-23-14:37:42 (download)
...
```

Cliquez sur ``download``, ce qui permet d’enregistrer une copie locale avec un nom de fichier unique, tel que ``qsharp_chem48443.yaml`` (le nom particulier sera différent pour chaque exécution). Vous pouvez ensuite traiter ce fichier comme indiqué ci-dessus, par exemple, avec 
```powershell
Get-GateCount -Format YAML qsharp_chem48443.yaml
```
pour connaître le nombre de ressources. 

Vous pouvez apprécier le générateur de molécules 3D accessible à partir de l’onglet ``Arrows Entry - 3D Builder`` de la page de démarrage flèches EMSL. Le fait de cliquer sur l’image 3D [JSMol](http://wiki.jmol.org/index.php/JSmol) de la molécule affichée vous permet de la modifier. Vous pouvez déplacer des atomes, faire glisser des atomes pour que leurs distances inter-moléculaires changent, ajouter/supprimer des atomes, etc. Pour chacun de ces choix, une fois que vous avez ajouté ``theory{qsharp_chem}`` dans la zone de requête, vous pouvez générer une instance du schéma Broombridge YAML et l’Explorer à l’aide de la bibliothèque de chimie Quantum. 