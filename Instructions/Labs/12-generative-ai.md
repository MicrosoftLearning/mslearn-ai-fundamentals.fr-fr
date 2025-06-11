---
lab:
  title: "Explorer l’IA générative dans le portail Azure\_AI Foundry"
---

# Explorer l’IA générative dans le portail Azure AI Foundry

L’IA générative fait référence à une catégorie de fonctionnalités au sein de l’IA qui créent du contenu. Les personnes interagissent généralement avec l’IA générative qui est intégrée aux applications de conversation. Dans cet exercice, vous essayez l’IA générative dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes. 

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts lors de votre première connexion. 

1. Dans le navigateur, accédez à `https://ai.azure.com/managementCenter/allResources` et sélectionnez **Créer**. Choisissez ensuite l’option permettant de créer une *ressource Azure AI Foundry*.

1. Dans l’Assistant *Créer un projet*, entrez un nom valide pour votre projet.

1. Développez les *options avancées* pour définir les paramètres suivants de votre projet :
    - **Abonnement** : votre abonnement Azure.
    - **Groupe de ressources** : créez ou sélectionnez un groupe de ressources.
    - **Région** : sélectionnez l’un des emplacements suivants.
        * USA Est
        * France Centre
        * Centre de la Corée
        * Europe Ouest
        * USA Ouest

    Attendez que votre projet et votre hub soient créés.

1. Lorsque le projet est créé, vous accédez à une page *Vue d’ensemble* des détails du projet.

1. Dans le menu de gauche de l’écran, sélectionnez **Terrains de jeu**.

## Explorer l’IA générative dans le terrain de jeu de conversation d’Azure AI Foundry

1. Dans la page Terrains de jeu d’Azure AI Foundry, sélectionnez **Essayer le terrain de jeu de conversation**. Le terrain de jeu de conversation est une interface utilisateur qui vous permet d’essayer de créer une application de conversation avec différents modèles d’IA générative.  

1. Pour utiliser le terrain de jeu de conversation, vous devez l’associer à un modèle déployé. Dans le terrain de jeu de conversation, vous devez avoir sélectionné **gpt-4o**. Si vous ne voyez aucun déploiement, vous devez sélectionner **+ Créer un déploiement**, rechercher **gpt-4o**. Sélectionnez ensuite **Confirmer**, puis **Déployer**.

1. Dans le terrain de jeu de conversation, vous pouvez utiliser votre modèle déployé lorsqu’il apparaît dans le menu de sélection *Déploiement*. Il est important de sélectionner **Appliquer les modifications** après avoir apporté des modifications à la *Configuration*. 

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

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressources que vous avez créées.

1. Sélectionnez les ressources, puis **Supprimer**, et **Oui** pour confirmer. Les ressources sont alors supprimées.
