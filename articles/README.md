# <a name="articles"></a>Articles

Dans ce répertoire, vous trouverez les Articles de la documentation du kit de développement quantique. Ce répertoire contient :

- **Répertoires des articles**: contiennent les Articles de chaque section de la documentation. Dans ces répertoires, vous pouvez trouver le contenu suivant :
  
  - Chaque répertoire contient un `toc.yml` fichier pour afficher le contenu du répertoire dans la table des matières principale.
  - Articles de démarque contenant la documentation. Ces articles doivent suivre les instructions du [Guide du contributeur Microsoft docs](https://docs.microsoft.com/en-us/contribute/).
  - Sous-répertoires d’articles. Ces sous-répertoires doivent également contenir leur propre `toc.yml` fichier.

> :p encil : bien qu’il soit possible de faire référence aux `*.md` fichiers directement dans le `TOC.yml` fichier parent, afin de conserver les éléments classés, nous ne les référencez qu’à partir `toc.yml` de leur répertoire actif.

- ** `TOC.yml` Fichier de table des matières (TOC) principal**: dans ce fichier, les sections de la table des matières du site Web sont répertoriées avec la référence au `toc.yml` fichier principal du répertoire de chaque section.
- **`index.yml`** YAML avec la configuration de la page d’accueil de la documentation.
- **`\media`**: Un répertoire pour stocker toutes les images utilisées dans la documentation. Il contient un `\media\src` sous-répertoire pour stocker les fichiers sources des images.
- **Fichiers de licence**: fichiers contenant des licences autorisées
- **Fichiers techniques**: fichiers contenant des macros et des métadonnées.

## <a name="guidelines"></a>Recommandations

Certaines instructions générales sur l’organisation de ce répertoire pour les contributeurs :

- Chaque répertoire ou sous-répertoire doit contenir son propre `toc.yml` fichier dans lequel sont désignés les Articles de même niveau ou les `toc.yml` fichiers de ses répertoires enfants.
- L’Organisation des annuaires du référentiel doit être aussi proche que possible de l’organisation de la table des matières du site Web de la documentation.
- Toutes les images doivent être stockées dans `articles\media` le dossier Articles et non dans celui-ci.
- Les titres des articles, les noms figurant dans la table des matières et l' *UID* des métadonnées doivent être aussi proches que possible parmi ceux-ci et représentent clairement l’en-tête H1 du document de démarque.

## <a name="adding-images"></a>Ajouter des images

Pour que les images soient correctement rendues en mode sombre, vous devez éviter les transparences.
- Pour les `*.jpg` fichiers, vous n’avez rien à faire, car le format de fichier ne prend pas en charge les éléments transparents.
- Pour les `*.png` fichiers, vous devez ajouter un arrière-plan blanc ou modifier la valeur du canal alpha sur 100. Le moyen le plus simple pour effectuer cette opération dans Windows consiste à ouvrir le fichier dans Paint et à enregistrer, en remplaçant le fichier d’origine.
- Pour `*.svg` les fichiers, vous devez ajouter un rectangle blanc dans la couche la plus basse. Pour ce faire, vous pouvez utiliser Inkscape :
  - Ouvrez le fichier `*.svg` .
  - Sélectionnez l’outil générateur carré et dessinez un rectangle blanc en plus de la figure d’origine.
  - Sélectionnez l’outil « sélectionner et transformer des objets » en cliquant sur la flèche foncée ou en appuyant sur F1.
  - Lorsque le rectangle est sélectionné, cliquez dans l’élément de barre d’outils « réduire la sélection au bas (fin) ».
  - Ajustez le rectangle avec la souris ou les touches de direction.
