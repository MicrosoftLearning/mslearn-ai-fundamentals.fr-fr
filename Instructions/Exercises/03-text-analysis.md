---
lab:
  title: "Analyser du texte dans le portail Azure\_AI\_Foundry"
---

# Analyser du texte dans le portail Azure AI Foundry

Azure AI Language inclut Analyse de texte, avec des fonctionnalités telles que la reconnaissance d’entité, l’extraction de phrases clés, la synthèse et l’analyse des sentiments. Par exemple, supposons que l’agence de voyage fictive Margie’s Travel encourage ses clients à soumettre des avis sur leurs séjours à l’hôtel. Vous pouvez utiliser le service de language pour extraire des entités nommées, identifier des phrases clés, résumer du texte, etc.

Dans cet exercice, vous allez utiliser Azure AI Language dans le portail Azure AI Foundry, plateforme de Microsoft pour la création d’applications intelligentes, afin d’analyser les avis des hôtels. 

Cet exercice prend environ **20** minutes.

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil du portail Azure AI Foundry.](./media/ai-foundry-portal.png)

1. Faites défiler vers le bas de la page, puis sélectionnez la vignette **Explorer Azure AI Services**.

    ![Capture d’écran de la vignette Explorer Azure AI Services.](./media/ai-services.png)

1. Dans la page Azure AI Services, sélectionnez la vignette **Language + Traducteur**.

    ![Capture d’écran de la vignette Language + Traducteur.](./media/language-tile.png)

1. Dans la page **Language + Traducteur**, sélectionnez **Essayer le terrain de jeu Language**. Ensuite, lorsque vous y êtes invité, créez un projet avec les paramètres suivants :
    - **Nom du projet** : *entrez un nom valide pour votre projet.*
    - **Paramètres avancés** :
        - **Abonnement** : *votre abonnement Azure*
        - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
        - **Région** : *sélectionnez n’importe quelle région **AI Foundry** recommandée*
        - **AI Foundry ou Azure OpenAI** *Créer une ressource Azure AI Foundry avec un nom valide*

1. Sélectionnez **Créer**. Attendez que votre projet soit créé. Cette opération peut prendre quelques minutes.

1. Lorsque le projet est créé, vous serez redirigé vers un terrain de jeu **Language** (si ce n’est pas le cas, dans le volet des tâches à gauche, sélectionnez **Terrains de jeu** et ouvrez le terrain de jeu Language à partir de là.)

    Le terrain de jeu du langage est une interface utilisateur qui vous permet d’essayer certaines fonctionnalités du langage Azure AI.  

## Utiliser Azure AI Language pour analyser du texte

Azure AI Language offre un large éventail de fonctionnalités d’analyse de texte.

### Extraire des entités nommées avec Azure AI Language dans le portail Azure AI Foundry

Les *entités nommées* sont des mots qui décrivent des personnes, des lieux et des objets avec des noms appropriés. Utilisons la fonctionnalité d’extraction d’entité nommée d’Azure AI Language pour identifier les types d’informations dans une révision.

1. Dans le terrain de jeu de langue, sélectionnez **Extraire des informations**. Sélectionnez ensuite la vignette **Extraire les entités nommées**. 

1. Sous *Exemple*, entrez l’avis suivant :

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Extraire des entités nommées dans le terrain de jeu Language.](./media/entity-extraction.png)

    Notez dans la section *Détails* comment les entités extraites sont fournies avec des informations supplémentaires telles que le type et les scores de confiance. Le score de confiance représente la probabilité que le type identifié appartient réellement à cette catégorie.

### Extraire des phrases clés avec Azure AI Language dans le portail Azure AI Foundry

Les *expressions clés* sont les éléments d’information les plus importants dans le texte. Utilisons la fonctionnalité d’extraction de phrases clés d’Azure AI Language pour extraire des informations importantes d’une révision.

1. Dans le terrain de jeu de langue, sélectionnez **Extraire des informations**. Sélectionnez ensuite la vignette **Extraire les phrases clés**. 

1. Sous *Exemple*, entrez l’avis suivant :

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Extraire des phrases clés dans le terrain de jeu Language.](./media/key-phrases.png)

    Notez les différentes phrases extraites dans la section *Détails*. Ces phrases doivent contribuer le plus à la signification du texte.

### Résumer le texte avec Azure AI Language dans le portail Azure AI Foundry
 
Examinons les fonctionnalités de résumé d’Azure AI Language.

1. Dans le terrain de jeu de langue, sélectionnez **Résumer les informations**, puis sélectionnez la vignette **Résumer le texte**.

1. Sous *Exemple*, entrez l’avis suivant :
    
    ```
    Very noisy and rooms are tiny
    The Lombard Hotel, San Francisco, USA
    9/5/2018
    Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Synthèse de texte dans le terrain de jeu Language.](./media/summarize-text.png)

    Notez que le *résumé extractif* dans *Détails* fournit des scores de classement pour les phrases les plus saillantes.

### Analyser les sentiments dans le texte

L’analyse des sentiments est une tâche courante lors de l’analyse de texte comme les avis d’hôtel.

1. Dans le terrain de jeu Language, sélectionnez **Classifier le texte**. Sélectionnez ensuite la vignette **Analyser les sentiments**.

1. Sous *Exemple*, entrez l’avis suivant :
    
    ```
    Disappointing Stay at The City Hotel
    The City Hotel, London
    9/5/2018
    My experience at The City Hotel in London was far from pleasant. The constant noise from nearby train tracks made it nearly impossible to sleep, with vibrations felt throughout the building. The rooms were outdated, dusty, and poorly maintained—dripping faucets, squeaky beds, and broken fixtures were just the beginning. Sound insulation was nonexistent, so every conversation from neighboring rooms was clearly audible. While the location near public transport was convenient and the staff were friendly, these positives couldn't make up for the overall discomfort and lack of value. I wouldn’t recommend this hotel to anyone seeking a restful or enjoyable stay.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Analyse des sentiments dans le terrain de jeu Language.](./media/sentiment-analysis.png)

    Notez que l’analyse produit un score de sentiment global et des scores individuels pour chaque phrase.

## Détecter la langue et traduire du texte

Azure AI Language vous permet de détecter la langue dans laquelle le texte est écrit. En outre, Azure AI Traducteur vous permet de traduire facilement du texte d’une langue à une autre.

### Détecter la langue

Commençons par détecter la langue dans laquelle un avis est écrit.

1. Dans le volet **Classifier le texte**, sélectionnez la vignette **Détecter la langue**.

1. Sous *Exemple*, entrez l’avis suivant :
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Sélectionnez **Exécuter**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Détecter la langue dans le terrain de jeu Language.](./media/detect-language.png)

    Notez que la langue détectée est le français. 

### Traduire le texte

Nous allons maintenant traduire l’avis du française à l’anglais.

1. En haut de la page, utilisez le lien **&larr;** (précédent) en regard du titre de la page **Terrain de jeu Language** pour afficher les terrains de jeux disponibles.
1. Dans la liste des terrains de jeux, ouvrez le **Terrain de jeu Traducteur**.
1. Dans le terrain de jeu Traducteur, sélectionnez **Traduction de texte**.
1. Dans le volet **Configurer**, sélectionnez les options de langue suivantes :
    - **Traduire depuis** : Français
    - **Traduire en** : Anglais
1. Sous *Exemple*, entrez l’avis en français :
    
    ```
    Un séjour mémorable à l’Hôtel d’Ville
    l’Hôtel d’Ville, Paris
    9/5/2018
    J’ai passé un excellent séjour à l’Hôtel d’Ville à Paris. L’emplacement est idéal, en plein cœur de la ville, ce qui permet de découvrir facilement les principaux sites touristiques. Le personnel était chaleureux, professionnel et toujours prêt à aider. La chambre était propre, confortable et bien équipée, avec une vue charmante sur les rues parisiennes. Le petit-déjeuner était varié et délicieux, parfait pour commencer la journée. Je recommande vivement cet hôtel à tous ceux qui recherchent une expérience parisienne authentique et agréable.
    ```

1. Sélectionnez **Traduire**. Passez en revue la sortie.

    ![Capture d’écran de l’interface Traduction de texte dans le terrain de jeu Traducteur.](./media/text-translation.png)

    Notez que l’avis en français est traduit en anglais.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressources que vous avez créées.
1. Sélectionnez **Supprimer le groupe de ressources**, puis **entrez le nom du groupe de ressources** pour confirmer. Le groupe de ressources est ensuite supprimé.

## En savoir plus

Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page sur le service Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
