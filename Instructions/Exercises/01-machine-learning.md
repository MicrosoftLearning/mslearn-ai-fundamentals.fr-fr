---
lab:
  title: Explorer le Machine Learning automatisé
---

# Explorer le Machine Learning automatisé

Dans cet exercice, vous allez utiliser le Machine Learning automatisé pour entraîner et évaluer un modèle Machine Learning. Vous allez ensuite déployer et tester le modèle entraîné.

> **Remarque** : Cet exercice est conçu pour vous guider à travers les étapes d’apprentissage et de test d’un modèle à l’aide d’***Azure Machine Learning***. Si vous disposez d’un abonnement Azure avec des autorisations suffisantes, vous pouvez approvisionner un espace de travail Azure Machine Learning et l’utiliser pour l’exercice. Toutefois, Azure Machine Learning est conçu pour les solutions d’apprentissage automatique à l’échelle de l’entreprise, impliquant d’importants volumes de données et des calculs dans le cloud. Certaines opérations dans Azure Machine Learning nécessitent l’approvisionnement de ressources de calcul, ce qui peut prendre beaucoup de temps. Si vous n’avez pas accès à Azure ou si vous disposez de peu de temps pour réaliser l’exercice, une application***ML Lab*** basée sur un navigateur et incluant les fonctionnalités principales d’Azure ML utilisées dans cet exercice est également disponible. Vous pouvez l’utiliser pour entraîner et tester de véritables modèles d’apprentissage automatique, comme vous le feriez avec Azure ML. Bien que l’interface utilisateur de ML Lab ne soit pas*identique* à celle d’Azure Machine Learning, elle est suffisamment similaire pour rendre la transition vers Azure Machine Learning intuitive. Notez que l’application ML Lab s’exécute dans le navigateur, donc rafraîchir la page à tout moment redémarrera l’application !

Cet exercice prend environ**35** minutes (moins si vous utilisez l’application ML Lab basée sur un navigateur).

## Créer un espace de travail

Un espace de travail permet de regrouper toutes vos ressources de Machine learning, ce qui facilite la gestion des données, du code, des modèles et des autres ressources en un seul endroit.

1. Ouvrez le portail de l’environnement que vous souhaitez utiliser dans ce labo et connectez-vous si vous y êtes invité :
    - [Azure Machine Learning Studio](https://ml.azure.com){:target="_blank"} basé sur Azure à`https://ml.azure.com`
    - [ML Lab](https://aka.ms/ml-lab){:target="_blank"} basé sur un navigateur à`https://aka.ms/ml-lab`

    > **Conseil** : Si Azure Machine Learning Studio s’ouvre dans un espace de travail existant, accédez à la page**Tous les espaces de travail**.

1. Créez un nouvel espace de travail avec un nom approprié.

    Si vous utilisez Azure Machine Learning, vous n’avez pas besoin d’un*Hub* pour cet exercice. Choisissez les paramètres avancés appropriés en fonction des contraintes de stratégie de votre abonnement Azure.

1. Une fois l’espace de travail créé, sélectionnez-le pour afficher sa page**Accueil**.

    Notez que l’espace de travail comporte plusieurs pages, qui s’affichent dans le volet de navigation à gauche. Vous pouvez développer et réduire ce volet à l’aide du menu **&#9776;** en haut.

## Télécharger des données

Dans cet exercice, vous allez utiliser un jeu de données sur les ventes de glaces pour entraîner un modèle qui prédit la demande de glaces pour un jour donné, en fonction des caractéristiques saisonnières et météorologiques.

1. Dans un nouvel onglet du navigateur, téléchargez**[ml-data.zip](https://aka.ms/mslearn-ml-data)** à partir de`https://aka.ms/mslearn-ml-data` sur votre ordinateur local.
1. Extrayez l’archive**ml-data.zip** téléchargée pour voir les fichiers qu’elle contient. Notez que l’un de ces fichiers est**ice-cream.csv**, qui contient les données de ventes de glaces nécessaires à cet exercice.

## Utiliser le Machine Learning automatisé pour entraîner un modèle

Le Machine Learning automatisé vous permet d’essayer plusieurs algorithmes et paramètres, afin d’entraîner plusieurs modèles et identifier celui qui convient le mieux à vos données.

1. Dans le portail, ouvrez la page**ML automatisé** (sous**Création**).

1. Créez un travail de ML automatisé avec les paramètres suivants, en utilisant**Suivant** pour progresser dans l’interface utilisateur :

    > **Conseil** : Si aucune information explicite n’est fournie pour un paramètre dans les étapes ci-dessous, utilisez la valeur par défaut.

    **Paramètres de base** :

    - Attribuez un**nom de tâche** unique à votre tâche de Machine Learning automatisé

   **Type de tâches et données** :

    - Définissez le type de tâche sur**Régression**.
    - Créez une nouvelle ressource de données***tabulaire*** nommée**ice-cream**
        - Téléchargez le fichier local**ice-cream.csv** dans le stockage par défaut de l’espace de travail.
        - Incluez<u>uniquement</u> les colonnes suivantes (*Date* est unique pour chaque ligne et apporte à elle seule une fonctionnalité prédictive) :
            - **DayOfWeek**
            - **Month**
            - **Température**
            - **Rainfall**
            - **IceCreamsSold**
        - Créez la ressource de données.
    - Assurez-vous que la ressource de données**ice-cream** nouvellement créée est sélectionnée avant de passer à l’étape suivante

    > **Remarque** : Si vous utilisez un abonnement Azure dont vous n’êtes pas l’administrateur, l’accès au stockage via une clé peut avoir été désactivé par la stratégie. Dans ce cas, vous devrez collaborer avec votre administrateur pour autoriser l’accès via une clé ou reconfigurer votre espace de travail Azure Machine Learning afin d’utiliser l’authentification Entra ID pour accéder au stockage. Si ce n’est pas possible, utilisez l’application***ML Lab*** basée sur un navigateur pour cet exercice.

    **Paramètres de la tâche** :

    - Définissez la**colonne cible** (l’étiquette que nous voulons que le modèle prédise) sur**IceCreamsSold**.
    - Définissez les**paramètres de configuration supplémentaires** :
        - Définissez la**métrique principale** sur la métrique que vous souhaitez utiliser pour évaluer les performances du modèle. Dans cet exercice, utilisez le score*R<sup>2</sup>*.
        - Sélectionnez les algorithmes de modèle que vous souhaitez essayer (ou laissez-les tous sélectionnés)
    - Définissez les**paramètres de caractérisation** :
        - Utilisez ces paramètres pour personnaliser la caractérisation (la manière dont les caractéristiques des données sont préparées pour l’entraînement du modèle)
    - Définissez les**limites** :
        - Appliquez des limites pour interrompre prématurément la tâche d’entraînement en fonction de critères spécifiques. Dans cet exercice, définissez les limites suivantes :
            - **Seuil de score de métrique** : 0,9
            - **Délai d’expiration de l’expérience (minutes)**  : 15
        
        > **Remarque** : il est important de définir ces limites lorsque vous utilisez Azure Machine Learning, car l’exécution de tâches d’entraînement pour chaque combinaison possible d’algorithmes et de caractérisation pourrait prendre plusieurs heures !

    **Capacité de calcul :**

    - Utilisez le calcul**serverless**

    **Révision**

    - Passez en revue les paramètres et vérifiez-les attentivement. Soumettez ensuite la tâche d’entraînement. Il démarre automatiquement.

1. Attendez que le travail se termine.

    > **Conseil** : Si vous utilisez Azure Machine Learning, cela peut prendre un certain temps. C’est peut-être le moment idéal pour faire une pause café !

## Examiner le meilleur modèle

Une fois le travail de Machine Learning automatisé terminé, vous pouvez évaluer le meilleur modèle qu’il a entraîné.

1. Dans l’onglet**Vue d’ensemble** de la page des détails de la tâche, affichez les informations relatives à la tâche et notez le résumé du meilleur modèle.
  
1. Sélectionnez le**Nom de l’algorithme** correspondant au meilleur modèle pour afficher ses détails. Ensuite, dans la page des détails de la tâche enfant, affichez les onglets suivants :
    - **Vue d’ensemble** : Détails généraux de la tâche enfant.
    - **Modèle** : Informations sur le modèle entraîné.
    - **Métriques** : métriques d’évaluation et visualisations pour le modèle basées sur les données de test utilisées pendant le processus d’entraînement.
    - **Sorties et journaux** : Informations consignées pendant le processus d’entraînement.

## Déployer et tester le modèle

1. Dans l’onglet**Modèle** du meilleur modèle entraîné par votre tâche de Machine Learning automatisé, sélectionnez**Déployer** pour déployer le modèle sur un point de terminaison en temps réel.

    Sélectionnez les options**Instances** et**Machine virtuelle** appropriées pour le calcul sur lequel le point de terminaison déployé sera exécuté ( qui peut dépendre du quota disponible dans votre abonnement Azure), puis attribuez des noms**point de terminaison** et**déploiement** appropriés.

1. Attendez la notification indiquant que le déploiement est terminé.

    > **Conseil** : Dans Azure Machine Learning Studio, le déploiement du point de terminaison peut prendre 5 à 10 minutes.

## Tester le service déployé

Vous pouvez maintenant tester votre service déployé.

1. Dans le menu de navigation, sélectionnez la page**Points de terminaison** et ouvrez le point de terminaison en temps réel que vous avez créé.

1. Dans la page du point de terminaison, affichez l’onglet**Test**.

1. Dans le volet**Entrer des données pour tester le point de terminaison**, remplacez le modèle JSON par les données de l’entrée suivante :

    ```json
   {
     "input_data": {
        "columns": [
            "DayOfWeek",
            "Month",
            "Temperature",
            "Rainfall"
        ],
        "index": [0],
        "data": [["Wednesday","June",70.5,0.05]]
     }
   }
    ```

1. Cliquez sur le bouton**Test**.

1. Consultez les résultats des tests qui comprennent un nombre prévu de locations en fonction des fonctionnalités d’entrée – semblables à ceci :

    ```JSON
   [
       120.16208168753236
   ]
    ```

    Le volet Tester a récupéré les données d’entrée et a utilisé le modèle sur lequel vous avez effectué l'apprentissage pour retourner le nombre prévu de locations.

## Affichez le code pour consommer le modèle

Maintenant que vous disposez d’un modèle prédictif, les développeurs peuvent générer des applications qui le consomment.

1. Sur la page du point de terminaison en temps réel, affichez l’onglet**Consommer**.
1. Passez en revue l’exemple de code pour consommer votre modèle.

## Si le temps vous le permet

Si vous souhaitez approfondir vos connaissances en matière de Machine Learning automatisé, essayez d’entraîner un modèle de**classification** basé sur le fichier**penguins.csv** inclus dans l’archive**ml-data.zip** que vous avez téléchargée précédemment. Utilisez toutes les colonnes de ce jeu de données.

Après avoir entraîné et déployé un modèle de classification, vous pouvez le tester dans le point de terminaison avec le JSON suivant :

```json
{
    "input_data": {
    "columns": [
        "CulmenLength",
        "CulmenDepth",
        "FlipperLength",
        "BodyMass"
    ],
    "index": [0],
    "data": [[45.2,13.8,215,4750]]
    }
}
```

## Nettoyage

Si vous avez utilisé Azure Machine Learning pour réaliser cet exercice, vous devez supprimer les ressources que vous avez créées afin d’éviter toute utilisation inutile d’Azure.

1. Dans[Azure Machine Learning studio](https://ml.azure.com), sous l’onglet**Points de terminaison**, sélectionnez le point de terminaison que vous avez déployé. Sélectionnez ensuite**Supprimer**, puis confirmez la suppression du point de terminaison.

    La suppression du calcul évite une facturation à votre abonnement des ressources de calcul. Une petite quantité de stockage de données vous est cependant facturée tant que l’espace de travail Azure Machine Learning existe dans votre abonnement. Si vous avez terminé l’exploration d’Azure Machine Learning, vous pouvez supprimer l’espace de travail Azure Machine Learning et les ressources associées.

Pour supprimer votre espace de travail, procédez comme suit :

1. Dans le[portail Azure](https://portal.azure.com), dans la page**Groupes de ressources**, ouvrez le groupe de ressources que vous avez spécifié lors de la création de votre espace de travail Azure Machine Learning.
2. Cliquez sur**Supprimer le groupe de ressources**, tapez le nom du groupe de ressources pour confirmer que vous souhaitez le supprimer, puis sélectionnez**Supprimer**.
