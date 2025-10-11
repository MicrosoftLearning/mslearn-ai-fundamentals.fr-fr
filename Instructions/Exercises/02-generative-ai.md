---
lab:
  title: "Explorer l’IA générative dans le portail Azure\_AI Foundry"
---

# Explorer l’IA générative dans le portail Azure AI Foundry

L’IA générative fait référence à une catégorie de fonctionnalités au sein de l’IA qui créent du contenu. Les personnes interagissent souvent avec l’IA générative qui a été intégrée aux applications de conversation. Dans cet exercice, vous essayez l’IA générative dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes. 

Cet exercice prend environ **20** minutes.

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil du portail Azure AI Foundry.](./media/ai-foundry-portal.png)

1. Dans la section **Explorer les modèles et les fonctionnalités**, recherchez `gpt-4o`. Ensuite, dans les résultats de la recherche, sélectionnez le modèle **gpt-4o** pour afficher ses détails.

    ![Capture d’écran de la page de détails de gpt-4o.](./media/gpt-4o-details.png)

1. Sélectionnez **Utiliser ce modèle**.

1. Dans l’Assistant **Créer un projet**, entrez un nom valide pour votre projet. Développez ensuite **Options avancées** pour spécifier les paramètres suivants pour votre projet :
    - **Ressource Azure AI Foundry** : *Entrez un nom valide pour votre ressource AI Foundry.*
    - **Abonnement** : *votre abonnement Azure*
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
    - **Région** : Sélectionnez l’une des régions recommandées par **AI Foundry**\*
    
    \**Les déploiements de modèle sont limités par des quotas régionaux. Si vous sélectionnez une région dans laquelle vous avez un quota disponible insuffisant, vous devrez peut-être sélectionner une autre région pour une nouvelle ressource ultérieurement.*

1. Sélectionnez **Créer**. Attendez que votre projet soit créé. Cette opération peut prendre quelques minutes.

    Si vous êtes invité à déployer le modèle dans une autre région, utilisez les paramètres par défaut pour le faire.

## Explorer l’IA générative dans le terrain de jeu de conversation d’Azure AI Foundry

1. Une fois le projet créé, dans le volet des tâches à gauche, sélectionnez **Terrains de jeu**. 

    >*Conseil* : le cas échéant, développez le menu pour lire son contenu en cliquant sur l’icône « Développer » en haut.

1. Dans la page Terrains de jeu d’Azure AI Foundry, sélectionnez **Essayer le terrain de jeu de conversation**. Fermez tous les volets Conseils ou Démarrage rapide qui s’ouvrent.

    Le terrain de jeu de conversation est une interface utilisateur qui vous permet d’essayer de créer une application de conversation avec différents modèles d’IA générative.

    ![Capture d’écran de la page de détails de gpt-4o.](./media/chat-playground.png)

    >*Conseil* : si le volet **Configuration** n’apparaît pas sur l’écran du terrain de jeu de conversation, agrandissez la taille de la fenêtre.  

1. Pour utiliser le terrain de jeu de conversation, vous devez l’associer à un modèle déployé. Dans le volet **Configuration** du terrain de jeu de conversation, vérifiez que le modèle **gpt-4o** que vous avez déployé précédemment est sélectionné. 

    >*Remarque* : vous devez sélectionner **Appliquer les modifications** chaque fois que vous faites des modifications dans le volet **Configuration**.

1. Dans le volet **Configuration**, notez les instructions et le contexte par défaut du modèle, qui doivent être similaires à :

    `You are an AI assistant that helps people find information.`

    Ces types d’instructions sont couramment appelés *invite du système* et sont utilisés pour fournir des conseils et des contraintes pour les réponses du modèle.

1. Passez en revue le volet *Historique des conversations*, qui contient des exemples d’invites pour vous aider à commencer, et une zone de requête pour à entrer vos propres invites. 

1. Essayons de générer une réponse à l’aide d’une invite avec un objectif spécifique. Dans la zone de conversation, entrez l’invite suivante :

    ```prompt
    I'm planning a trip to Paris in September. Can you help me?
    ```

1. Passez en revue la réponse. N’oubliez pas que la réponse spécifique que vous recevez peut varier en raison de la nature de l’IA générative.

1. Essayons une autre invite : Saisissez les informations suivantes :

    ```prompt
    Where's a good location in the city to stay?
    ```

1. Passez en revue la réponse, qui devrait fournir certains endroits pour rester à Paris. Notez que la session de conversation conserve le contexte des invites précédentes, donc il sait que « la ville » en question est Paris.

1. Itérez en fonction des invites et des réponses précédentes pour affiner le résultat. Entrez l’invite suivante :

    ```prompt
    Can you give me more information about dining options near the first location?
    ```

1. Passez en revue la réponse, qui doit fournir des options de restauration près d’un lieu indiqué dans la réponse précédente. 

1. Indiquons maintenant une source pour ancrer la réponse dans une étendue spécifique d’informations. Saisissez les informations suivantes : 

    ```prompt
    Based on the information at https://en.wikipedia.org/wiki/History_of_Paris, what were the key events in the city's history?
    ```

1. Passez en revue la réponse, qui doit fournir des informations basées sur le site web fourni. 

1. Essayons d’ajouter du contexte pour optimiser la pertinence de la réponse. Entrez l’invite suivante : 

    ```prompt
    What three places do you recommend I stay in Paris to be within walking distance to historical attractions? Explain your reasoning.
    ```

1. Passez en revue la réponse et le raisonnement de la réponse.  

1. Définissez maintenant des attentes claires pour la réponse Entrez l’invite suivante :

    ```prompt
    What are the top 10 sights to see in Paris? Answer with a numbered list in order of popularity.
    ```

1. Passez en revue la réponse, qui doit fournir une liste numérotée de sites à voir à Paris.

## Afficher le code client

1. En haut de la page Terrain de jeux de conversation, sélectionnez **Afficher le code**.
1. Passez en revue les exemples de code fournis pour plusieurs langages de programmation, kits de développement logiciel et options d’authentification.

    Ces exemples de code peuvent aider les développeurs à démarrer rapidement lors de la création d’applications clientes qui discutent avec votre modèle déployé.

1. Fermez la fenêtre d’exemple de code.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressources que vous avez créées.
1. Sélectionnez **Supprimer le groupe de ressources**, puis **entrez le nom du groupe de ressources** pour confirmer. Le groupe de ressources est ensuite supprimé.
