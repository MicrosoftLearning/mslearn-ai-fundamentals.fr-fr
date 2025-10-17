---
lab:
  title: Explorer le Machine Learning automatisé dans Azure Machine Learning
---

# Explorer le Machine Learning automatisé dans Azure Machine Learning

Dans cet exercice, vous allez utiliser la fonctionnalité Machine Learning automatisé dans Azure Machine Learning pour entraîner et évaluer un modèle Machine Learning. Vous allez ensuite déployer et tester le modèle entraîné.

Cet exercice devrait prendre environ **35** minutes.

## Création d’un espace de travail Microsoft Azure Machine Learning

Pour utiliser Azure Machine Learning, vous devez approvisionner un espace de travail Azure Machine Learning dans votre abonnement Azure. Vous allez ensuite pouvoir utiliser Azure Machine Learning studio pour utiliser les ressources de votre espace de travail.

> **Conseil** : Si vous disposez déjà d’un espace de travail Azure Machine Learning, vous pouvez l’utiliser et passer à la tâche suivante.

1. Connectez-vous au [Portail Azure](https://portal.azure.com) à `https://portal.azure.com` en utilisant vos informations d’identification Microsoft.

1. Sélectionnez **+ Créer une ressource**, recherchez *Machine Learning* et créez une ressource **Azure Machine Learning** avec les paramètres suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*.
    - **Nom** : *Entrez un nom unique pour votre espace de travail*.
    - **Région** : USA Est.
    - **Compte de stockage** : *notez le nouveau compte de stockage par défaut à créer pour votre espace de travail*.
    - **Coffre de clés** : *notez le nouveau coffre de clés par défaut, qui va être créé pour votre espace de travail*.
    - **Application Insights** : *notez la nouvelle ressource Application Insights par défaut, qui va être créée pour votre espace de travail*.
    - **Registre de conteneurs** : aucun (*un registre est créé automatiquement la première fois que vous déployez un modèle sur un conteneur*).

1. Sélectionnez **Vérifier + créer**, puis sélectionnez **Créer**. Attendez que votre espace de travail soit créé (cela peut prendre quelques minutes), puis accédez à la ressource déployée.

#### Lancer Studio 

1. Dans la ressource de votre espace de travail Azure Machine Learning, sélectionnez **Lancer Studio** (ou ouvrez un nouvel onglet de navigateur et accédez à [https://ml.azure.com](https://ml.azure.com), puis connectez-vous à Azure Machine Learning Studio à l’aide de votre compte Microsoft). Fermez tous les messages affichés.

1. Dans Azure Machine Learning Studio, vous devez voir l’espace de travail qui vient d’être créé. Si ce n’est pas le cas, sélectionnez **Tous les espaces de travail** dans le menu de gauche, puis l’espace de travail créé.

## Utiliser le Machine Learning automatisé pour entraîner un modèle

Le Machine Learning automatisé vous permet d’essayer plusieurs algorithmes et paramètres, afin d’entraîner plusieurs modèles et identifier celui qui convient le mieux à vos données. Dans cet exercice, vous allez utiliser un jeu de données de détails historiques sur la location de vélos pour entraîner un modèle qui prédit le nombre de locations de vélos auquel s’attendre pour une journée donnée, en fonction des caractéristiques saisonnières et météorologiques.

> **Citation** : *Les données utilisées dans cet exercice sont dérivées de [Capital Bikeshare](https://www.capitalbikeshare.com/system-data) et utilisées conformément au [contrat de licence](https://www.capitalbikeshare.com/data-license-agreement) des données publiées.*

1. Dans [Azure Machine Learning studio](https://ml.azure.com?azure-portal=true), consultez la page **ML automatisé** (sous **Création**).

1. Créez un travail de ML automatisé avec les paramètres suivants, en utilisant **Suivant** pour progresser dans l’interface utilisateur :

    **Paramètres de base** :

    - **Nom du travail** : le champ Nom du travail doit déjà être prérempli avec un nom unique. Gardez-le tel quel.
    - **Nom de la nouvelle expérience** : `mslearn-bike-rental`
    - **Description** : `Automated machine learning for bike rental prediction`
    - **Balises** : *aucune*

   **Type de tâches et données** :
    
    >**REMARQUE** : Certains abonnements disposent d’autorisations qui ne permettent pas l’ajout de *bike-data* à *workspaceblobstore*. Si vous rencontrez ce problème, vous devez basculer vers un autre abonnement.

    - **Sélectionner le type de tâche** : Régression
    - **Sélectionner des données** :
        - Créez une ressource de données avec les paramètres suivants :
            - **Type de données** :
                - **Nom :** `bike-rentals`
                - **Description** : `Historic bike rental data`
                - **Type** : Table (mltable)
            - **Source des données** :
                - Sélectionnez **À partir de fichiers locaux**
            - **Type de stockage de destination** :
                - **Datastore type** (Type de magasin de données) : Stockage Blob Azure
                - **Nom** : workspaceblobstore
            - **Sélection MLTable** :
                - *Téléchargez et décompressez le [dossier bike-data](https://aka.ms/bike-rentals) à partir de `https://aka.ms/bike-rentals`.*
                - **Charger le dossier** : *Téléchargez le dossier **bike-data** extrait, qui contient les fichiers de données et de définition de table dont vous avez besoin pour votre jeu de données d’entraînement.*
                - **Remarque** : *si un message vous invite à ignorer la validation des données pour continuer, sélectionnez l’option permettant d’ignorer la validation des données.*
        - Sélectionnez la ressource de données **bike-rentals** nouvellement créée et continuez à définir la tâche ML automatisé à la page suivante (**Paramètres de la tâche**).

    **Paramètres de la tâche** :

    - **Type de tâche** : Régression
    - **Jeu de données** : bike-rentals
    - **Colonne cible** : rentals (entier)
    - **Paramètres de configuration supplémentaires** :
        - **Métrique principale** : NormalizedRootMeanSquaredError
        - **Expliquer le meilleur modèle** : *<u>Non</u>sélectionné*
        - **Activer l’empilement d’ensembles** : *<u>Non</u>sélectionné*
        - **Utiliser tous les modèles pris en charge** : <u>Un</u>sélectionné. *Vous allez restreindre le travail pour essayer uniquement quelques algorithmes spécifiques.*
        - **Modèles autorisés** : *Sélectionnez uniquement **RandomForest** et **LightGBM**. Normalement, vous pouvez en essayer autant que possible, mais chaque modèle ajouté augmente le temps nécessaire à l’exécution du travail.*
    - **Limites** : *Développer cette section*
        - **Nombre maximal d’essais** : `3`
        - **Nombre maximal d’essais simultanés** : `3`
        - **Nombre maximal de nœuds** : `3`
        - **Seuil de score de métrique** : `0.085` (*si un modèle atteint ainsi un score de métrique d’erreur quadratique moyenne normalisée égal ou inférieur à 0,085, le travail s’achève*)
        - **Délai d’expiration de l’expérience** : `15`
        - **Délai d’expiration de l’itération** : `15`
        - **Activer la résiliation anticipée** : *Sélectionné*
    - **Validation et test** :
        - **Type de validation** : fractionnement de validation d’entraînement
        - **Pourcentage de données de validation** : 10
        - **Jeu de données de test** : Aucun

    **Capacité de calcul :**

    - **Sélectionner le type de calcul** : Serverless
    - **Type de machine virtuelle** : Processeur
    - **Niveau de machine virtuelle** : dédié
    - **Taille de machine virtuelle** : Standard_DS3_V2\*
    - **Nombre d’instances** : 1

    \* *Si votre abonnement limite les tailles de machine virtuelle disponibles, choisissez une taille disponible.*

1. Soumettre la tâche d’apprentissage. Il démarre automatiquement.

1. Attendez que le travail se termine. Cela risque de prendre un certain temps, c’est peut-être le moment de faire une pause café !

## Examiner le meilleur modèle

Une fois le travail de Machine Learning automatisé terminé, vous pouvez évaluer le meilleur modèle qu’il a entraîné.

1. Sous l’onglet **Vue d’ensemble** du travail de machine learning automatisé, notez le meilleur récapitulatif du modèle.
    ![Capture d’écran du meilleur récapitulatif de modèle du travail de machine learning automatisé avec un encadré autour du nom de l’algorithme.](./media/use-automated-machine-learning/complete-run.png)
  
1. Sélectionnez le texte sous **Nom de l’algorithme** correspondant au meilleur modèle pour voir ses détails.

1. Sélectionnez l’onglet **Métriques** et sélectionnez les graphiques de **résiduels** et de comparaison **valeurs prédites-valeurs réelles** s’ils ne sont pas déjà sélectionnés.

    Regardez les graphiques qui montrent les performances du modèle. Le graphique des **résidus** montre les *résidus* (les différences entre les valeurs prédites et réelles) sous forme d’histogramme. Le graphique **predicted_true** compare les valeurs prédites aux vraies valeurs.

## Déployer et tester le modèle

1. Sous l’onglet **Modèle** du meilleur modèle entraîné par votre travail de Machine Learning automatisé, sélectionnez **Déployer**, puis utilisez l’option **Point de terminaison en temps réel** pour déployer le modèle avec les paramètres suivants :
    - **Machine virtuelle** : Standard_DS3_v2
    - **Nombre d’instances** : 3
    - **Point de terminaison** : Nouvelle
    - **Nom du point de terminaison** : *Laissez la valeur par défaut ou assurez-vous qu’elle est globalement unique*
    - **Nom du déploiement** : *Conserver la valeur par défaut*
    - **Collecte des données d’inférence** : *Disabled*
    - **Empaqueter le modèle** : *Disabled*

    > **Remarque** : si vous recevez un message indiquant qu’il n’y a pas suffisamment de quota pour sélectionner la machine virtuelle *Standard_DS3_v2*, sélectionnez-en une autre.

1. Attendez que le déploiement commence. Cette opération peut prendre quelques secondes. Le **statut de déploiement** du point de terminaison sera indiqué dans la partie principale de la page comme *En cours d’exécution*.
1. Attendez que l’**état du déploiement** passe à *Réussi*. Cette opération peut prendre 5 à 10 minutes.

## Tester le service déployé

Vous pouvez maintenant tester votre service déployé.

1. Dans Azure Machine Learning studio, dans le menu de gauche, sélectionnez **Points de terminaison** et ouvrez le point de terminaison en temps réel que vous avez créé.

1. Sur la page du point de terminaison en temps réel, affichez l’onglet **Test**.

1. Dans le volet **Entrer des données pour tester le point de terminaison**, remplacez le modèle JSON par les données de l’entrée suivante :

    ```json
      {
     "input_data": {
       "columns": [
         "day",
         "mnth",
         "year",
         "season",
         "holiday",
         "weekday",
         "workingday",
         "weathersit",
         "temp",
         "atemp",
         "hum",
         "windspeed"
       ],
       "index": [0],
       "data": [[1,1,2022,2,0,1,1,2,0.3,0.3,0.3,0.3]]
     }
    }

    ```

1. Cliquez sur le bouton **Test**.

1. Consultez les résultats des tests qui comprennent un nombre prévu de locations en fonction des fonctionnalités d’entrée – semblables à ceci :

    ```JSON
    [
      352.3564674945718
    ]
    ```

    Le volet Tester a récupéré les données d’entrée et a utilisé le modèle sur lequel vous avez effectué l'apprentissage pour retourner le nombre prévu de locations.

## Afficher le code pour utiliser le service

Maintenant que vous disposez d’un point de terminaison de service prédictif, les développeurs peuvent générer des applications qui le consomment.

1. Sur la page du point de terminaison en temps réel, affichez l’onglet **Consommer**.
1. Passez en revue l’exemple de code permettant de consommer votre point de terminaison, qui est fourni pour plusieurs langages de programmation.

Passons en revue les opérations que vous avez effectuées. Vous avez utilisé un jeu de données de données historiques sur la location de bicyclettes pour effectuer l’apprentissage d’un modèle. Le modèle prédit le nombre de locations de bicyclettes attendues pour un jour donné, en fonction des *caractéristiques* saisonnières et météorologiques. Enfin, vous avez testé le modèle et passé en revue le code qu’un développeur peut utiliser pour générer une application permettant de le consommer.

## Nettoyage

Le service web que vous avez créé est hébergé dans une *instance de conteneur Azure*. Si vous n’envisagez pas d’effectuer d’autres expériences avec celui-ci, vous devez supprimer le point de terminaison afin d’éviter une utilisation d’Azure non nécessaire.

1. Dans [Azure Machine Learning studio](https://ml.azure.com), sous l’onglet **Points de terminaison**, sélectionnez le point de terminaison que vous avez déployé. Sélectionnez ensuite **Supprimer**, puis confirmez la suppression du point de terminaison.

    La suppression du calcul évite une facturation à votre abonnement des ressources de calcul. Une petite quantité de stockage de données vous est cependant facturée tant que l’espace de travail Azure Machine Learning existe dans votre abonnement. Si vous avez terminé l’exploration d’Azure Machine Learning, vous pouvez supprimer l’espace de travail Azure Machine Learning et les ressources associées.

Pour supprimer votre espace de travail, procédez comme suit :

1. Dans le [portail Azure](https://portal.azure.com), dans la page **Groupes de ressources**, ouvrez le groupe de ressources que vous avez spécifié lors de la création de votre espace de travail Azure Machine Learning.
2. Cliquez sur **Supprimer le groupe de ressources**, tapez le nom du groupe de ressources pour confirmer que vous souhaitez le supprimer, puis sélectionnez **Supprimer**.
