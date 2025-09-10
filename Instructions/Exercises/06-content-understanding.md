---
lab:
  title: "Extraire des données avec Compréhension de contenu dans le portail Azure\_AI\_Foundry"
---

# Extraire des données avec Compréhension de contenu dans le portail Azure AI Foundry

**Compréhension de contenu Azure AI (préversion)** utilise l’IA générative pour traiter divers types de contenu (documents, images, vidéos et audio) et les convertir dans un format de sortie défini par l’utilisateur.

Dans cet exercice, vous allez utiliser Compréhension de contenu Azure AI dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, pour extraire des données à partir de factures. 

Cet exercice dure environ **25** minutes.

## Créer un projet Azure AI Foundry et une tâche de compréhension de contenu

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil d’Azure AI Foundry avec l’option de création d’un assistant sélectionné.](./media/azure-ai-foundry-home-page.png)

1. Dans une nouvelle fenêtre de navigateur, ouvrez la [page d’exploration des services Azure AI](https://ai.azure.com/explore/aiservices).

1. Dans la page *Services IA*, sélectionnez la vignette *Essayer la compréhension de contenu*.

1. Sélectionnez **Sélectionnez ou créez un projet pour démarrer**. 

1. Sélectionnez **+ Créer un projet**.

1. Dans l’Assistant, entrez un nom valide pour votre projet. 

1. Sélectionnez **Options avancées** et définissez les paramètres suivants :
    - **Ressource Azure AI Foundry** : *conservez le nom par défaut*
    - **Abonnement** : *votre abonnement Azure*
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
    - **Région** : sélectionnez l’un des emplacements suivants.
        * USA Ouest
        * Suède Centre
        * Australie Est

1. Sélectionnez **Créer**. Attendez que le processus de configuration se termine. Cette opération peut prendre quelques minutes.

    >**Remarque** : si vous recevez une erreur d’autorisation, sélectionnez le bouton **Corriger** pour ajouter les autorisations appropriées pour continuer.

1. Une fois votre projet créé, vous serez amené par défaut à la fenêtre de création de tâche de compréhension de contenu. Utilisez les paramètres suivants pour créer une tâche de compréhension de contenu :
    - **Nom de la tâche** : `contoso-invoice`
    - **Description** : `An invoice analysis task`
    - *Sélectionner l’analyse de contenu d’un seul fichier*
    - **Paramètres avancés** : *conservez la valeur par défaut*.

1. Sélectionnez **Créer**, puis attendez la création de votre tâche. 

1. Sélectionnez votre tâche **contoso-invoice**. 

## Analyser une facture avec Compréhension de contenu Azure AI dans Azure AI Foundry 

Supposons que vous souhaitiez extraire des données à partir de nombreuses factures et les stocker dans une base de données. Vous pouvez utiliser Compréhension de contenu Azure AI pour analyser une facture et créer votre propre analyseur capable d’analyser d’autres factures similaires. Commençons par définir votre schéma.

#### Définir votre schéma 

1. Sur la page *Définir le schéma*, vous pouvez ajouter des fichiers de test. Téléchargez [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) à partir de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. le fichier sur la page **définir le schéma**. Sélectionnez le modèle **Extraction des données de facturation**. Le modèle d’extraction des données de facture contient des champs de données pré-sélectionnés que l’analyseur tentera de détecter. 

    ![Capture d’écran de la page de définition du schéma dans l’outil Compréhension de contenu.](./media/content-understanding/define-schema.png)

1. Sélectionnez **Créer**. Vous avez maintenant la possibilité de modifier le schéma en ajoutant ou en supprimant des champs. Une fois la révision des champs terminée, sélectionnez **Enregistrer**.

    ![Capture d’écran de la page Définir le schéma après avoir sélectionné Créer.](./media/content-understanding/define-schema-2.png)

1. Attendez que l’analyse se termine. Cette opération peut prendre un certain temps.

#### Tester l’analyseur 

1. Une fois l’analyse terminée, vous pourrez consulter les résultats de l’analyseur dans la page *Tester l’analyseur*. Passez en revue l’onglet *Champs* (*Remarque* : vous devrez peut-être développer la fenêtre pour afficher les résultats complets). Ces données correspondent-elles à ce que vous voyez sur la facture ? 
    ![Capture d’écran de la page de test de l’analyseur avec l’onglet Champs mis en évidence.](./media/content-understanding/test-analyzer-fields.png)

1. Notez le *score de confiance* affiché à côté de chaque champ. Le score de confiance indique le degré de certitude du modèle quant à l’exactitude du résultat. Plus le score est proche de 100 %, plus la confiance dans la prédiction est élevée.

1. Examinez l’onglet *Résultat*. Les mêmes informations affichées dans l’onglet Champs y sont présentées au format JSON. Le JSON montre à quoi ressemblent les données lorsqu’elles sont envoyées à une application cliente ou reçues par celle-ci. 

    ![Capture d’écran de la page de test de l’analyseur avec l’onglet Résultats mis en évidence.](./media/content-understanding/test-analyzer-result.png)

1. Le service Compréhension de contenu doit avoir correctement identifié le texte correspondant aux champs du schéma. Si ce n’était pas le cas, vous pouvez utiliser la page *Étiqueter les données* pour charger un autre exemple de formulaire et identifier explicitement le texte correct pour chaque champ. Lorsque la capacité de l’analyseur à détecter les données de la facture vous satisfait, sélectionnez l’onglet **Liste des analyseurs**. 

#### Générer votre analyseur 

Maintenant que vous avez entraîné un modèle à extraire les champs à partir de votre facture exemple, vous pouvez générer un analyseur à utiliser avec des formulaires similaires. En générant un analyseur, vous pouvez déployer le modèle et l’utiliser pour automatiser d’autres tâches liées aux factures.

1. Dans l’onglet *Liste des analyseurs*, sélectionnez** + Analyseur de build**. Saisissez les informations suivantes : 
    - **Nom :** `invoice-analyzer`
    - **Description** : `An invoice analyzer`

    ![Capture d’écran de la page de génération d’un analyseur.](./media/content-understanding/build-analyzer.png)

1. Sélectionnez **Générer**. Attendez que l’analyseur soit prêt (utilisez le bouton Actualiser pour vérifier). Votre analyseur utilise un modèle prédictif fondé sur le schéma que vous avez défini et testé dans les étapes précédentes. 
1. Passons maintenant au test de l’analyseur que vous venez de générer. Téléchargez une facture différente de Contoso : [contoso-invoice-2.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf) à partir de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-2.pdf`.
1. Revenez à la page *Liste des analyseurs* et sélectionnez le lien analyseur de factures. Les champs définis dans le schéma de l’analyseur s’affichent.
1. Dans la page de l’analyseur invoice-analyzer, sélectionnez *Tester*.
1. Utilisez le bouton **+ Importer des fichiers de test** pour charger *contoso-receipt-2.pdf*. Sélectionnez **Exécuter l’analyse** pour extraire les données des champs à partir du formulaire de test. Passez en revue les résultats du test.

    ![Capture d’écran des résultats de l’analyse pour l’analyseur que vous avez généré.](./media/content-understanding/build-analyzer-2.png)

1. Sélectionnez l’onglet *Exemple de code*. Repérez le *point de terminaison* dans le code. Dans la phase du processus *Générer un analyseur*, vous avez déployé votre modèle de compréhension de contenu sur un point de terminaison. Ce point de terminaison peut être utilisé dans un code semblable à l’exemple affiché, afin d’intégrer le modèle dans un processus réutilisable au sein d’une application.  

    ![Capture d’écran de l’exemple de code pour l’analyseur que vous avez généré.](./media/content-understanding/code-example.png)

## Nettoyage

Si vous avez terminé votre travail avec le service Compréhension de contenu, vous devez supprimer les ressources créées dans cet exercice pour éviter des coûts Azure inutiles.

- Dans le portail Azure AI Foundry, accédez au projet contoso-receipt et supprimez-le.
- Dans le portail Azure, supprimez le groupe de ressources que vous avez créé pour cet exercice.
