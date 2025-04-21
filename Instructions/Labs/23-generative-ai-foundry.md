---
lab:
  title: "Explorer l’IA générative dans le portail Azure\_AI Foundry"
---

# Explorer l’IA générative dans le portail Azure AI Foundry

L’IA générative fait référence à une catégorie de fonctionnalités au sein de l’IA qui créent du contenu. Les personnes interagissent généralement avec l’IA générative qui est intégrée aux applications de conversation. Dans cet exercice, vous essayez l’IA générative dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes. 

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
 
1. Une fois les ressources créées, vous serez redirigé vers la page *Vue d’ensemble* de votre projet. Dans le menu de gauche de l’écran, sélectionnez **Terrains de jeu**.
 
    ![Capture d’écran du menu de gauche de l’écran du projet avec Services d’IA sélectionnés.](./media/azure-ai-foundry-playgrounds.png)  

## Explorer l’IA générative dans le terrain de jeu de conversation d’Azure AI Foundry

1. Dans la page Terrains de jeu d’Azure AI Foundry, sélectionnez **Essayer le terrain de jeu de conversation**. Le terrain de jeu de conversation est une interface utilisateur qui vous permet d’essayer de créer une application de conversation avec différents modèles d’IA générative.  

1. Pour utiliser le terrain de jeu de conversation, vous devez l’associer à un modèle déployé. Dans le terrain de jeu de conversation, sélectionnez **Créer un déploiement**. Recherchez et sélectionnez **GPT-4**. 

1. Dans la fenêtre *Déployer un modèle*, conservez le nommage et la sélection par défaut, puis sélectionnez **Déployer**. Le déploiement du modèle peut prendre un moment. Vous pouvez vérifier l’état de votre déploiement en sélectionnant *Modèles et points de terminaison* dans le menu de gauche dans *Mes ressources*.
1. Dans le terrain de jeu de conversation, vous pouvez utiliser votre modèle déployé lorsqu’il apparaît dans le menu de sélection *Déploiement*. Vérifiez que le modèle que vous avez déployé est sélectionné. Il est important de sélectionner **Appliquer les modifications** après avoir apporté des modifications à la *Configuration*. 

1. Tenez compte des façons suivantes d’améliorer les réponses d’un assistant IA générative :
    - Commencez par fixer un objectif spécifique pour l’assistant
    - Itérez en fonction des invites et réponses précédentes pour affiner le résultat
    - Indiquez une source pour baser la réponse dans une étendue spécifique d’informations.
    - Ajoutez un contexte pour optimiser la pertinence et l’adéquation de la réponse
    - Définissez des attentes claires pour la réponse

1. Essayons de générer une réponse à l’aide d’une invite avec un objectif spécifique. Dans la zone de conversation, entrez l’invite suivante :

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Vérifiez la réponse. **Note** : la réponse spécifique que vous recevez peut varier en raison de la nature de l’IA générative.
 
1. Essayons une autre invite : Entrez les informations suivantes :

    ```prompt
    Where's a good location in Paris to stay? 
    ```

1. Passez en revue la réponse, qui devrait fournir certains endroits pour rester à Paris.

1. Itérez en fonction des invites et des réponses précédentes pour affiner le résultat. Entrez l’invite suivante :
    
    ```prompt
    Can you give me more information about dining options near the first location?
    ``` 

1. Passez en revue la réponse, qui doit fournir des options de restauration près d’un lieu indiqué dans la réponse précédente. 

1. Indiquons maintenant une source pour ancrer la réponse dans une étendue spécifique d’informations. Entrez les informations suivantes : 
    
    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Passez en revue la réponse, qui doit fournir des informations basées sur le site web fourni. 

1. Essayons d’ajouter du contexte pour optimiser la pertinence de la réponse. Entrez l’invite suivante : 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Passez en revue la réponse et le raisonnement de la réponse.  

1. Définissez maintenant des attentes claires pour la réponse Entrez l’invite suivante :
    
    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Passez en revue la réponse, qui doit fournir une liste numérotée de sites à voir à Paris.

1. Lorsque vous avez terminé, vous pouvez fermer la fenêtre du navigateur.