---
lab:
  title: "Extraire des données de documents dans le portail Azure\_AI\_Foundry"
---

# Extraire des données de documents dans le portail Azure AI Foundry

Le service **Azure AI Intelligence documentaire** vous permet d’analyser et d’extraire des informations à partir de formulaires et de documents, puis d’identifier les noms de champs et les données. 

Comment Intelligence documentaire se base-t-il sur la reconnaissance optique de caractères (OCR) ? Bien que l’OCR puisse lire des documents imprimés ou manuscrits, elle extrait du texte dans un format non structuré qui est difficile à stocker dans une base de données ou à analyser. L’intelligence documentaire donne un sens aux données non structurées en capturant la structure du texte, comme les champs de données et les informations contenues dans des tables. 

Dans cet exercice, vous allez utiliser les modèles prédéfinis d’Azure AI Intelligence documentaire dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, afin de reconnaître les données d’un reçu. 

## Créer un projet dans le portail Azure AI Foundry

1. Dans un onglet de navigateur, accédez à [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. Connectez-vous avec votre compte. 

1. Sur la page d’accueil du portail Azure AI Foundry, sélectionnez **Créer un projet**. Dans Azure AI Foundry, les projets sont des conteneurs qui aident à organiser votre travail.  

    ![Capture d’écran de la page d’accueil d’Azure AI Foundry avec l’option de création d’un projet sélectionné.](./media/azure-ai-foundry-home-page.png)

1. Dans le volet *Créer un projet*, vous verrez un nom de projet généré, que vous pouvez conserver en l’état. Selon que vous avez créé un hub par le passé, vous verrez une liste de *nouvelles* ressources Azure à créer ou une liste déroulante de hubs existants. Si vous voyez la liste déroulante des hubs existants, sélectionnez *Créer un hub*, créez un nom unique pour votre hub, puis sélectionnez *Suivant*.  
 
    ![Capture d’écran du volet Créer un projet avec des noms générés automatiquement pour le hub et le projet.](./media/azure-ai-foundry-create-project.png)

> **Important** : vous aurez besoin d’une ressource de services Azure AI configurée dans un emplacement spécifique pour effectuer le reste du labo.

1. Dans le même volet *Créer un projet*, sélectionnez **Personnaliser** et sélectionnez l’un des **emplacements** suivants : USA Est, France Centre, Corée Centre, Europe Ouest ou USA Ouest pour terminer le reste du labo. Sélectionnez ensuite **Créer**. 

1. Notez les ressources créées : 
- Azure AI services
- Azure AI Hub
- Projet Azure AI
- Compte de stockage
- Key vault
- Resource group  
 
1. Une fois les ressources créées, vous serez redirigé vers la page *Vue d’ensemble* de votre projet. Dans le menu de gauche de l’écran, sélectionnez **Services d’IA**.
 
    ![Capture d’écran du menu de gauche de l’écran du projet avec Services d’IA sélectionnés.](./media/azure-ai-foundry-ai-services.png)  

1. Dans la page *Services d’IA*, sélectionnez la vignette *Vision + Document* pour essayer les fonctionnalités Azure AI Intelligence documentaire.

    ![Capture d’écran de la vignette Vision et Document sélectionnée dans la page Services d’IA.](./media/vision-document-tile.png)

## Analyser un reçu avec Azure AI Intelligence documentaire dans Azure AI Foundry 

Vous êtes maintenant prêt à analyser un reçu pour la société de vente au détail fictive Northwind Traders.

1. Dans la page *Vision + Document*, faites défiler vers le bas et sélectionnez **Document**. Dans *Modèles prédéfinis pour des documents spécifiques*, sélectionnez la vignette **Reçus**.

1. Dans la liste déroulante, dans *Essayer*, notez que votre ressource Azure AI Services est sélectionnée. Laissez en l’état.

1. Sur votre ordinateur, utilisez [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) pour ouvrir un exemple d’image d’un reçu. Enregistrez-le dans votre dossier Téléchargements, ou sur votre Bureau. 
 
1. Dans Azure AI Foundry, sur la page *Reçus*, sélectionnez **Parcourir les fichiers** et accédez au dossier où vous avez enregistré l’image. Sélectionnez l’image du reçu, puis **Ouvrir**. L’image apparaît sur le côté gauche de l’écran.

    ![Capture d’écran d’un reçu de Northwind.](media/document-intelligence/receipt.jpg)

1. Sur la droite, sélectionnez **Exécuter l’analyse**.

1. Une fois l’analyse exécutée, les résultats sont retournés. Notez que le service a reconnu des champs de données spécifiques tels que le nom du prestataire, l’adresse, le numéro de téléphone et la date et l’heure de la transaction, ainsi que les éléments de ligne, les sous-totaux, les taxes et les montants totaux. À côté de chaque champ figure un pourcentage de probabilité que le champ soit correct.

    ![Capture d’écran du résultat de l’analyse des reçus dans le portail Azure AI Foundry, montrant des zones englobantes autour des champs de données et du texte dans ces champs extraits.](media/receipt-lab-result.png)

Dans cet exercice, vous avez utilisé le modèle de reçus prédéfinis d’Azure AI Intelligence documentaire dans le portail Azure AI Foundry. À partir des résultats retournés, vous avez vu comment Intelligence documentaire a pu identifier des champs spécifiques, ce qui permet de traiter plus facilement les données des documents quotidiens. Avant de fermer la démonstration, pourquoi ne pas essayer certains exemples de reçus, y compris ceux dans différentes langues ?

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Microsoft Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Cet exercice n’a montré que certaines des fonctionnalités du service AI Intelligence documentaire. Pour en savoir plus sur ce que vous pouvez faire avec ce service, consultez la page [Intelligence documentaire](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
