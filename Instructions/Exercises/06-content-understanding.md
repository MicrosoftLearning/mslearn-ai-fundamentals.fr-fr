---
lab:
  title: "Extraire des données avec Compréhension de contenu dans le portail Azure\_AI\_Foundry"
---

# Extraire des données avec Compréhension de contenu dans le portail Azure AI Foundry

Compréhension de contenu Azure AI fournit une analyse multimodale des documents, des fichiers audio, des vidéos et des images pour extraire des informations.

Dans cet exercice, vous allez utiliser Compréhension de contenu Azure AI dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, pour extraire des informations à partir de factures. 

Cet exercice dure environ **25** minutes.

## Créer un projet Azure AI Foundry pour la compréhension du contenu

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil du portail Azure AI Foundry.](./media/ai-foundry-portal.png)

1. Faites défiler vers le bas de la page, puis sélectionnez la vignette **Explorer Azure AI Services**.

    ![Capture d’écran de la vignette Explorer Azure AI Services.](./media/ai-services.png)

1. Dans la page Azure AI Services, sélectionnez **Essayer Compréhension de contenu**.

    ![Capture d’écran du bouton Essayer Compréhension de contenu.](./media/try-content-understanding.png)

1. Dans la page Compréhension de contenu, sélectionnez **Créer un projet à démarrer**. Ensuite, dans la boîte de dialogue **Créer un projet**, sélectionnez le type de ressource recommandé (**ressource Azure AI Foundry**) :

    ![Capture d’écran des résultats de l’analyse.](./media/resource-type.png)

1. Dans la page **Suivant**, entrez un nom valide pour votre projet. Sélectionnez ensuite **Options avancées** et spécifiez les paramètres suivants :
    - **Ressource Azure AI Foundry** : *un nom valide pour votre ressource Azure AI Foundry.*
    - **Abonnement** : *votre abonnement Azure*
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
    - **Région** : sélectionnez l’un des emplacements suivants\* :
        * USA Ouest
        * Suède Centre
        * Australie Est

    \**Au moment de l’écriture, Compréhension de contenu est pris en charge dans ces régions.*

    ![Capture d’écran des paramètres du projet.](./media/content-project-settings.png)

1. Sélectionnez **Créer**. Attendez que le processus de configuration se termine. Cette opération peut prendre quelques minutes.

## Extraire des informations d’une facture

1. Téléchargez [contoso-invoice-1.pdf](https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf) à partir de `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/refs/heads/main/data/contoso-invoice-1.pdf`. 

1. Dans la page Compréhension de contenu, sélectionnez l’onglet **Essayer**, puis sélectionnez la vignette **Extraction des données d’une facture**.

    ![Capture d’écran de la page Compréhension de contenu « Essayer ».](./media/content-understanding-invoice.png)

    Un exemple de facture est fourni.

1. Sélectionnez l’exemple de facture et utilisez le bouton **Exécuter l’analyse** pour extraire des informations de celui-ci. Une fois l’analyse terminée, affichez les résultats.

    ![Capture d’écran des résultats de l’analyse de l’exemple de facture.](./media/sample-invoice-analysis.png)

1. Utilisez le lien **Parcourir les fichiers** pour charger le document **contoso-invoice-1.pdf** que vous avez téléchargé précédemment, puis exécutez l’analyse sur ce fichier.

    ![Capture d’écran des résultats de l’analyse de la facture Contoso.](./media/contoso-invoice-analysis.png)

    Notez que l’analyseur Compréhension de contenu est en mesure d’extraire des informations de cette facture, même si son format diffère de celui de l’exemple.

1. Dans le volet de droite, où les champs extraits sont affichés, affichez l’onglet **Résultat** pour afficher la réponse JSON qui serait envoyée à une application cliente. Un développeur écrirait du code pour traiter cette réponse et faire quelque chose avec les champs extraits.

    ![Capture d’écran des résultats de l’analyse de la facture Contoso.](./media/invoice-analysis-json.png)

## Nettoyage

Si vous avez terminé votre travail avec le service Compréhension de contenu, vous devez supprimer les ressources créées dans cet exercice pour éviter des coûts Azure inutiles.

- Dans le portail Azure, supprimez le groupe de ressources que vous avez créé pour cet exercice.
