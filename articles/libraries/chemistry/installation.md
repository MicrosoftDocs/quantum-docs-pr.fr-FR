---
title: Installation et validation de la bibliothèque chimie | Microsoft Docs
description: Installation et validation de la bibliothèque chimie
author: guanghaolow
ms.author: gulow
ms.date: 10/12/2018
ms.topic: article
uid: microsoft.quantum.chemistry.concepts.installation
ms.openlocfilehash: de13d1814821c612ed74a347dc8ffb5881063576
ms.sourcegitcommit: 5094c0a60cbafdee669c8728b92df281071259b9
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "77036472"
---
# <a name="chemistry-library-installation-and-validation"></a>Installation et validation de la bibliothèque chimie

Le kit de développement Quantum prend en charge les applications de la chimie quantique par le biais du package NuGet [`Microsoft.Quantum.Chemistry`](https://www.nuget.org/packages/Microsoft.Quantum.Chemistry) .
Comme avec les autres packages NuGet, il est simple d’ajouter la bibliothèque chimie à votre projet.

**Visual Studio 2019 :** Si vous utilisez Visual Studio 2019, vous pouvez ajouter les packages de chimie des quantums à l’aide du gestionnaire de package NuGet.
Pour ouvrir le gestionnaire de package, cliquez avec le bouton droit sur le projet auquel vous souhaitez ajouter la bibliothèque de chimie, puis sélectionnez « gérer les packages NuGet... » comme dans la capture d’écran ci-dessous.

![](~/media/vs2017-nuget-manage-packages.png)

Dans l’onglet Parcourir, recherchez le nom du package « Microsoft. Quantum. chimie ».

> [!NOTE]
> Veillez à cocher « inclure la version préliminaire ».

![](~/media/vs2017-nuget-package-search.png)

Cela permet de répertorier les packages disponibles au téléchargement.
Cliquez sur « Microsoft. Quantum. chimie dans le volet gauche, sélectionnez la version préliminaire la plus récente dans le volet droit, puis cliquez sur «installer » :

![](~/media/vs2017-nuget-select-chem.png)

Pour plus d’informations, consultez le Guide de l' [interface utilisateur du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-ui).

Vous pouvez également utiliser la console du gestionnaire de package pour ajouter la bibliothèque de chimie Quantum à votre projet à l’aide d’une interface de ligne de commande.

![](~/media/vs2017-nuget-console-menu.png)

À partir de la console du gestionnaire de package, exécutez la commande suivante :

```
Install-Package Microsoft.Quantum.Chemistry
```

Pour plus d’informations, consultez le Guide de la [console du gestionnaire de package](https://docs.microsoft.com/nuget/tools/package-manager-console).

**Ligne de commande ou Visual Studio code :** En utilisant la ligne de commande seule ou dans Visual Studio Code, vous pouvez utiliser la commande `dotnet` pour ajouter la référence de package NuGet à votre projet :

```dotnetcli
dotnet add package Microsoft.Quantum.Chemistry
```

## <a name="verifying-your-installation"></a>Vérification de votre installation 

À l’instar du reste du kit de développement quantique, la bibliothèque Quantum chimie est fournie avec un certain nombre d’exemples entièrement documentés pour vous aider à devenir rapidement opérationnel.
Pour tester votre installation à l’aide de ces exemples, clonez le [référentiel d’exemples principal](https://github.com/Microsoft/Quantum), puis exécutez l’un des exemples.  Par exemple, pour exécuter l’exemple de [`MolecularHydrogen`](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/MolecularHydrogen) :

```bash
git clone https://github.com/Microsoft/Quantum.git
cd Quantum/samples/chemistry/MolecularHydrogen
dotnet run
```

Pour vérifier l’installation de la bibliothèque de chimie quantique à l’aide d’Microsoft Visual Studio après le clonage du référentiel :
    1. Ouvrez la solution ChemistrySamples. sln dans le dossier chimie.  
    2. Sélectionnez Samples/1. Molécules/MolecularHydrogen simples comme projet de démarrage.
    3. Appuyez sur F5 pour exécuter la démonstration de l’estimation de la phase Quantum d’hydrogène moléculaire.

Pour plus d’informations sur l’estimation des valeurs des niveaux d’énergie, consultez [obtention d’estimations au niveau](xref:microsoft.quantum.chemistry.examples.energyestimate) de l’énergie.   


## <a name="using-the-quantum-development-kit-with-nwchem"></a>Utilisation du kit de développement quantique avec NWChem ##

L’exemple MolecularHydrogen utilise des données d’entrée moléculaires configurées manuellement.  Bien que cela soit parfait pour les petits exemples, la chimie quantique à l’échelle nécessite Hamiltonians avec des millions ou des milliards de termes. Ces Hamiltonians, générés par des packages de chimie de calcul évolutif, sont trop volumineux pour être importés manuellement. 

La bibliothèque Quantum chimie pour le kit de développement quantique est conçue pour fonctionner correctement avec les packages de chimie de calcul, notamment la plateforme de calcul de calcul [**NWChem**](http://www.nwchem-sw.org/) développée par le laboratoire Environmental-Sciences Environmental (EMSL) au laboratoire national du Nord-Ouest du Pacifique.
En particulier, le package `Microsoft.Quantum.Chemistry` fournit des outils pour le chargement d’instances de problèmes de simulation de la chimie Quantum représentés dans le [schéma Broombridge](xref:microsoft.quantum.libraries.chemistry.schema.broombridge), également pris en charge pour l’exportation par les versions récentes de NWChem.

Pour être opérationnel à l’aide de NWChem avec le kit de développement Quantum, nous vous suggérons l’une des méthodes suivantes :
- Commencez à utiliser les fichiers Broombridge existants fournis avec les exemples sur [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML).
- Utilisez le [Générateur de flèches EMSL pour le Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) qui est un serveur frontal Web à NWChem pour générer de nouveaux fichiers d’entrée moléculaire avec format Broombridge.  
- Utilisez l' [image de l’arrimeur](https://hub.docker.com/r/nwchemorg/nwchem-qc/) fournie par PNNL pour exécuter NWChem, ou
- [Compilez NWChem](http://www.nwchem-sw.org/index.php/Compiling_NWChem) pour votre plateforme.

Pour plus d’informations sur l’utilisation de NWChem sur des modèles chimiques à des fins d’analyse avec la bibliothèque de modèles de développement quantique, consultez la page de [bout en bout avec NWChem](xref:microsoft.quantum.chemistry.examples.endtoend) .

### <a name="getting-started-using-broombridge-files-provided-with-the-samples"></a>Prise en main des fichiers Broombridge fournis avec les exemples

Le dossier [IntegralData/YAML](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/IntegralData/YAML) du référentiel d’exemples du kit de développement Quantum contient des fichiers de données de molécule en format Broombridge.  

En guise d’exemple simple, utilisez l’exemple de bibliothèque chimie [GetGateCount](https://github.com/microsoft/Quantum/tree/master/samples/chemistry/GetGateCount) pour charger le modèle Hamilton à partir de l’un des fichiers Broombridge et effectuer des estimations de la porte de la simulation de Quantum algorigthms :

```bash
cd Quantum/Chemistry/GetGateCount
dotnet run -- --path=../IntegralData/YAML/h2.yaml --format=YAML
```

Pour plus d’informations sur la façon d’entrer des molécules représentées par le schéma Broombridge, consultez chargement d’un modèle de niveau de données [à partir d’un fichier](xref:microsoft.quantum.chemistry.examples.loadhamiltonian) .  

Pour plus d’informations sur l’estimation des ressources, consultez [obtention du nombre de ressources](xref:microsoft.quantum.chemistry.examples.resourcecounts) .  

### <a name="getting-started-using-the-emsl-arrows-builder"></a>Prise en main du générateur de flèches EMSL

EMSL Arrows est un outil qui utilise des bases de données de calcul NWChem et Chemical pour générer des données de molécule.  [Le générateur de flèches EMSL pour la Microsoft Quantum Development Kit](https://arrows.emsl.pnnl.gov/api/qsharp_chem) vous permet d’entrer votre modèle à l’aide de plusieurs générateurs de modèles moléculaires et de générer le fichier de fichier Broombridge à utiliser par le kit de développement quantique.  

Dans la page EMSL, cliquez sur l’onglet ['instructions'] et suivez les instructions ['exemples simples'] pour générer des fichiers Broombridge.  Essayez ensuite d’exécuter ['GetGateCount'] pour voir les estimations de la ressource Quantum pour ces molécules.

### <a name="installing-nwchem-from-source"></a>Installation de NWChem à partir de la source

Des instructions complètes sur l’installation de NWChem à partir de la source [sont fournies par PNNL](http://www.nwchem-sw.org/index.php/Compiling_NWChem).

> [!TIP]
> Si vous souhaitez utiliser NWChem à partir de Windows 10, le sous-système Windows pour Linux est une option intéressante.
> Une fois que vous avez installé [Ubuntu 18,04 LTS pour Windows](https://www.microsoft.com/en-us/p/ubuntu-1804-lts/9n9tngvndl3q#activetab=pivot:overviewtab), exécutez `ubuntu18.04` à partir de votre terminal préféré et suivez les instructions ci-dessus pour installer NWChem à partir de la source.

Une fois que vous avez compilé NWChem à partir de la source, vous pouvez exécuter le script de `yaml_driver` fourni avec NWChem pour produire rapidement des instances Broombridge à partir de jeux d’entrée NWChem :

```bash
$NWCHEM_TOP/contrib/quasar/yaml_driver input.nw
```

Cette commande crée un fichier de `input.yaml` au format Broombridge dans votre répertoire actif.

### <a name="using-nwchem-with-docker"></a>Utilisation de NWChem avec l’ancrage

Les images prédéfinies pour l’utilisation de NWChem sont disponibles sur plusieurs plateformes via le hub de l' [arrimeur](https://hub.docker.com).
Pour commencer, suivez les instructions d’installation de la station d’accueil pour votre plateforme :

- [Installer la station d’accueil pour Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/)
- [Installer l’arrimeur pour macOS](https://docs.docker.com/docker-for-mac/install/)
- [Installer Docker pour Windows 10](https://docs.docker.com/docker-for-windows/install/)

> [!TIP]
> Si vous utilisez Docker pour Windows, vous devez partager le lecteur contenant votre répertoire temporaire (il s’agit généralement du lecteur `C:\`) avec le démon Dockr. Pour plus d’informations, consultez la documentation de l' [ancrage](https://docs.docker.com/docker-for-windows/#shared-drives) .

Une fois que vous avez installé la station d’accueil, vous pouvez utiliser le module PowerShell fourni avec les exemples du kit de développement Quantum pour exécuter l’image, ou vous pouvez exécuter l’image manuellement.
Nous avons détaillé l’utilisation de PowerShell ici. Si vous souhaitez utiliser l’image de l’ancrer manuellement, consultez la [documentation fournie avec l’image](https://hub.docker.com/r/nwchemorg/nwchem-qc/).

#### <a name="running-nwchem-through-powershell-core"></a>Exécution de NWChem via PowerShell Core

Pour utiliser l’image de l’Ancrable NWChem avec le kit de développement Quantum, nous fournissons un petit module PowerShell qui gère le déplacement des fichiers vers et depuis NWChem pour vous.
Si vous n’avez pas encore installé PowerShell Core, vous pouvez le télécharger sur plusieurs plateformes à partir du [référentiel PowerShell sur GitHub](https://github.com/PowerShell/PowerShell#get-powershell).

> [!NOTE]
> PowerShell Core est également utilisé pour certains exemples pour démontrer l’interopérabilité avec les flux de travail de science des données et d’analyse commerciale.

Une fois PowerShell Core installé, importez `InvokeNWChem.psm1` pour rendre les commandes NWChem disponibles dans votre session active :

```powershell
cd Quantum/utilities/
Import-Module ./InvokeNWChem.psm1
```

Cela rendra la commande `Convert-NWChemToBroombridge` disponible dans votre session PowerShell actuelle.
Pour télécharger les images nécessaires à partir de la station d’accueil et les utiliser pour exécuter des jeux d’entrée NWChem et capturer la sortie sur Broombridge, exécutez la commande suivante :

```powershell
Convert-NWChemToBroombridge ./input.nw
```

Cette opération crée un fichier Broombridge en exécutant NWChem sur `input.nw`.
Par défaut, la sortie Broombridge aura le même nom et le même chemin d’accès que le pont d’entrée, avec l’extension `.nw` remplacée par `.yaml`.
Cela peut être substitué à l’aide du paramètre `-DestinationPath` pour `Convert-NWChemToBroombridge`.
Vous pouvez obtenir plus d’informations à l’aide des fonctionnalités d’aide intégrées de PowerShell :

```powershell
Convert-NWChemToBroombridge -?
Get-Help Convert-NWChemToBroombridge -Full
```
