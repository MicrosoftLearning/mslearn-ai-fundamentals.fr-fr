---
lab:
  title: "Analyser du texte dans le portail Azure\_AI\_Foundry"
---

# Analyser du texte dans le portail Azure AI Foundry

Le traitement du langage naturel (NLP) est une branche de l’IA qui traite du langage écrit et parlé. Vous pouvez utiliser le NLP pour créer des solutions qui extraient le sens sémantique du texte ou de la parole, ou qui formulent des réponses significatives en langage naturel.

Le service Azure AI Language inclut l’analyse de texte, avec des fonctionnalités telles que la reconnaissance d’entité, l’extraction de phrases clés, le résumé et l’analyse des sentiments. Par exemple, supposons que l’agence de voyage fictive Margie’s Travel encourage ses clients à soumettre des avis sur leurs séjours à l’hôtel. Vous pouvez utiliser le service de language pour extraire des entités nommées, identifier des phrases clés, résumer du texte, etc.

Dans cet exercice, vous allez utiliser Azure AI Language dans le portail Azure AI Foundry, plateforme de Microsoft pour la création d’applications intelligentes, afin d’analyser les avis des hôtels. 

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

1. Dans la page *Terrains de jeu*, sélectionnez la vignette **Terrain de jeu de langue** pour essayer certaines fonctionnalités Azure AI Language.

## Extraire des entités nommées avec Azure AI Language dans le portail Azure AI Foundry

Les *entités nommées* sont des mots qui décrivent des personnes, des lieux et des objets avec des noms appropriés. Utilisons la fonctionnalité d’extraction d’entité nommée d’Azure AI Language pour identifier les types d’informations dans une révision.

1. Dans le terrain de jeu de langue, sélectionnez **Extraire des informations**. Sélectionnez ensuite la vignette **Extraire les entités nommées**. 

1. Dans *Exemple*, copiez et collez la révision suivante :

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie. Notez dans la section *Détails* comment les entités extraites sont fournies avec des informations supplémentaires telles que le type et les scores de confiance. Le score de confiance représente la probabilité que le type identifié appartient réellement à cette catégorie.

## Extraire des phrases clés avec Azure AI Language dans le portail Azure AI Foundry

Les *expressions clés* sont les éléments d’information les plus importants dans le texte. Utilisons la fonctionnalité d’extraction de phrases clés d’Azure AI Language pour extraire des informations importantes d’une révision.

1. Dans le terrain de jeu de langue, sélectionnez **Extraire des informations**. Sélectionnez ensuite la vignette **Extraire les phrases clés**. 

1. Dans *Exemple*, copiez et collez la révision suivante :

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie. Notez les différentes phrases extraites dans la section *Détails*. Ces phrases doivent contribuer le plus à la signification du texte.

## Résumer le texte avec Azure AI Language dans le portail Azure AI Foundry
 
1. Examinons les fonctionnalités de résumé d’Azure AI Language. Dans le terrain de jeu de langue, sélectionnez *Résumer les informations*, puis sélectionnez la vignette **Résumer le texte**.

1. Dans *Exemple*, copiez et collez la révision suivante :
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie. Notez que le *résumé extractif* dans *Détails* fournit des scores de classement pour les phrases les plus saillantes.   

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressources que vous avez créées.

1. Sélectionnez les ressources, puis **Supprimer**, et **Oui** pour confirmer. Les ressources sont alors supprimées.

## En savoir plus

Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page sur le service Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
