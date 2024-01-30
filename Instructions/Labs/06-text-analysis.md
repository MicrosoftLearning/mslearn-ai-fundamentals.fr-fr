---
lab:
  title: Analyser du texte avec Language Studio
---

# Analyser du texte avec Language Studio

Dans cet exercice, vous explorerez les capacités d'Azure AI Language en analysant quelques exemples de commentaires d'hôtels. Vous utiliserez Language Studio pour savoir si les avis sont majoritairement positifs ou négatifs.

Le traitement du langage naturel (NLP) est une branche de l’IA qui traite du langage écrit et parlé. Vous pouvez utiliser le NLP pour créer des solutions qui extraient le sens sémantique du texte ou de la parole, ou qui formulent des réponses significatives en langage naturel.

Par exemple, supposons que l’agence de voyage fictive Margie’s Travel encourage ses clients à soumettre des avis sur leurs séjours à l’hôtel. Vous pourriez utiliser le service Language pour identifier des expressions clés, discriminer les avis positifs et négatifs ou analyser le texte des avis pour y détecter des mentions d’entités connues telles que des emplacements ou des personnes.

Azure AI Language Service comprend des fonctionnalités d’analyse de texte et de NLP. Il s'agit notamment de l'identification des phrases clés dans les textes et de la classification des textes sur la base du sentiment.

## Créer une ressource *Langage*

Vous pouvez utiliser de nombreuses fonctionnalités Azure AI Language avec une ressource **Langage** ou **Azure AI services**. Dans certains cas, seule une ressource linguistique peut être utilisée. Pour l’exercice ci-dessous, nous allons utiliser une ressource **Langage**. Si ce n’est déjà fait, créez une ressource **Langage** dans votre abonnement Azure.

1. Dans un nouvel onglet de navigateur, ouvrez le Portail Azure à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et connectez-vous avec le compte Microsoft associé à votre abonnement Azure.

1. Cliquez sur le bouton  **&#65291;Créer une ressource** et recherchez *Language service*. Sélectionnez **créer** un plan du **service Language**. Vous serez redirigé vers une page pour **sélectionner des fonctionnalités supplémentaires**. Conservez la sélection par défaut, puis cliquez sur **Continuer pour créer votre ressource**. 

1. Dans la page **Créer un langage**, configurez-la avec les paramètres suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
    - **Région** : USA Est.
    - **Nom** : *entrez un nom unique.*
    - **Niveau tarifaire** : *Gratuit F0 ou S si gratuit F0 n’est pas disponible*
    - **En cochant cette case, je reconnais avoir lu et compris toutes les conditions ci-dessous** : *Sélectionné*.

1. Sélectionnez **Vérifier + créer**, puis **Créer** et attendez la fin du déploiement.

## Configurez votre ressource dans Azure AI Language Studio

1. Dans un autre onglet de navigateur, ouvrez **Language Studio** à l’adresse [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true) et connectez-vous.

1. Lorsque vous êtes invité à **sélectionner une ressource Azure**, effectuez les configurations suivantes :
    - **Répertoire Azure** : *Répertoire par défaut, répertoire que vous utilisez*
    - **Abonnement Azure** : *Sélectionnez l’abonnement que vous utilisez*
    - **Type de ressource** : Language.
    - **Nom de la ressource** : *sélectionnez la ressource de service de langage que vous venez de créer*

Ensuite, sélectionnez **Terminé**.

> **Important** : Depuis juillet 2023, les services Azure AI englobent l'ensemble de ce qui était auparavant connu sous le nom de Cognitive Services et Azure Applied AI Services. Certaines interfaces utilisateur mettent toujours à jour leur référence de `Cognitive Services` à partir de `Azure AI services`. Les deux noms font référence au même type de ressource.

> **Remarque** : Si vous n’êtes ***pas*** invité à choisir une ressource Language, cela peut être dû au fait que vous disposez de plusieurs ressources Language dans votre abonnement. Dans ce cas :
> 1. Dans la barre en haut de la page, sélectionnez **Paramètres (&#9881;)**. 
> 1. Dans la page **Paramètres**, affichez l’onglet **Ressources**.
> 1. Sélectionnez la ressource que vous venez de créer, puis sélectionnez **Changer de ressource**. Vérifiez que l’identité managée est **activée**.
> ![Activer la ressource Langue.](media/analyze-text-language-service/language-resource-enabled.png)
> 1. En haut de la page, sélectionnez **Language Studio** pour revenir à la page d’accueil de Language Studio.

## Analyser les révisions dans Language Studio

1. Dans un navigateur web, accédez à **Language Studio** à l’adresse [https://language.cognitive.azure.com](https://language.cognitive.azure.com?azure-portal=true).

1. Dans la page d’accueil de **Language Studio**, sélectionnez l’onglet **Classifier le texte**, puis sélectionnez la vignette **Analyser les sentiments et les opinions personnelles**.

1. Sous *Sélectionner la langue du texte*, sélectionnez **Anglais**.

1. Sous *Sélectionner votre ressource Azure*, sélectionnez votre ressource.

1. Sous *Entrer votre propre texte, chargez un fichier ou utilisez l’un de nos exemples de textes*, copiez et collez la révision suivante :

    ```
    Tired hotel with poor service
    The Royal Hotel, London, United Kingdom
    5/6/2018
    This is an old hotel (has been around since 1950's) and the room furnishings are average - becoming a bit old now and require changing. The internet didn't work and had to come to one of their office rooms to check in for my flight home. The website says it's close to the British Museum, but it's too far to walk.
    ```

1. Cochez la case pour confirmer que la démonstration entraîne l’utilisation et peut entraîner des coûts, puis sélectionnez **Exécuter**.

1. Passez en revue la sortie. Notez que le *document* est analysé pour les sentiments, ainsi que chaque *phrase*. Sélectionnez **phrase 1** pour afficher l’analyse des sentiments pour cette phrase. 

Notez qu’il existe un sentiment global suivi de scores en regard de trois catégories, d’un *score positif*, d’un *score neutre*, d’un *score négatif*. Dans chacune des catégories, un score compris entre 0 et 1 est fourni. Ces scores de confiance indiquent la probabilité que le texte fourni présente un sentiment particulier. 

Sélectionnez à nouveau **phrase 1** pour fermer.

1. Faites défiler vers le haut pour sélectionner **Effacer la zone de texte**, puis copiez et collez la révision suivante :

    ```
    Good Hotel and staff
    The Royal Hotel, London, UK
    3/2/2018
    Clean rooms, good service, great location near Buckingham Palace and Westminster Abbey, and so on. We thoroughly enjoyed our stay. The courtyard is very peaceful and we went to a restaurant which is part of the same group and is Indian ( West coast so plenty of fish) with a Michelin Star. We had the taster menu which was fabulous. The rooms were very well appointed with a kitchen, lounge, bedroom and enormous bathroom. Thoroughly recommended.
    ```
    
    
1. Sélectionnez **Exécuter**. Examinez les résultats et passez en revue le niveau de confiance.

1. Sélectionnez à nouveau **Effacer la zone de texte**, puis copiez et collez la révision suivante :

    >Very noisy and rooms are tiny The Lombard Hotel, San Francisco, USA 9/5/2018 Hotel is located on Lombard street which is a very busy SIX lane street directly off the Golden Gate Bridge. Traffic from early morning until late at night especially on weekends. Noise would not be so bad if rooms were better insulated but they are not. Had to put cotton balls in my ears to be able to sleep--was too tired to enjoy the city the next day. Rooms are TINY. I picked the room because it had two queen size beds--but the room barely had space to fit them. With family of four in the room it was tight. With all that said, rooms are clean and they've made an effort to update them. The hotel is in Marina district with lots of good places to eat, within walking distance to Presidio. May be good hotel for young stay-up-late adults on a budget

1. Sélectionnez **Exécuter** et passez en revue le sentiment avec le niveau de confiance. Examinez le texte et comparez-le à l’analyse des sentiments renvoyée par le service.

Dans cet exercice, vous avez utilisé Language Studio pour créer une nouvelle ressource linguistique ou utiliser une ressource linguistique existante. Vous avez activé la ressource dans Paramètres avant d’essayer le service d’exploration de sentiments et d’avis. Vous avez ensuite testé le service avec trois morceaux de texte.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **Portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page sur le service Language](https://learn.microsoft.com/azure/ai-services/language-service/overview).
