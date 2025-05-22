---
lab:
  title: "Explorer l’IA générative dans le portail Azure\_AI Foundry"
---

# Explorer l’IA générative dans le portail Azure AI Foundry

L’IA générative fait référence à une catégorie de fonctionnalités au sein de l’IA qui créent du contenu. Les personnes interagissent généralement avec l’IA générative qui est intégrée aux applications de conversation. Dans cet exercice, vous essayez l’IA générative dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes. 

## Créer un projet dans le portail Azure AI Foundry

Commençons par créer un projet Azure AI Foundry.

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil d’Azure AI Foundry avec l’option de création d’un assistant sélectionné.](./media/azure-ai-foundry-home-page.png)

1. Sur la page d’accueil, sélectionnez **+Créer un assistant**.

1. Dans l’Assistant **Création d’un assistant**, entrez un nom valide pour votre assistant. 

1. Sélectionnez **Options avancées** et définissez les paramètres suivants :
    - **Ressource Azure AI Foundry** : *conservez le nom par défaut*
    - **Abonnement** : *votre abonnement Azure*
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
    - **Région** : sélectionnez l’un des emplacements suivants.
        * USA Est
        * France Centre
        * Centre de la Corée
        * Europe Ouest
        * USA Ouest

1. Vérifiez vos configurations, puis sélectionnez **Créer**. Attendez que le processus de configuration se termine.

    >**Remarque** : si vous recevez une erreur d’autorisation, sélectionnez le bouton **Corriger** pour ajouter les autorisations appropriées pour continuer.

1. Une fois votre projet créé, vous serez amené par défaut vers le terrain de jeu des assistants dans le portail Azure AI Foundry, qui devrait ressembler à l’image suivante :

    ![Capture d’écran des détails d’un projet Azure AI dans le portail Azure AI Foundry.](./media/ai-foundry-project-2.png)

1. Dans le menu de gauche de l’écran, sélectionnez **Terrains de jeu**.

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
