---
lab:
  title: Utiliser les réponses aux questions avec Language Studio
---

# Utiliser le modèle Réponses aux questions avec Language Studio

Dans cet exercice, vous allez utiliser Language Studio pour créer et former une base de connaissances de questions et réponses qui seront utilisées par un bot de services clients. Le contenu de la base de connaissances proviendra d’une page FAQ existante du site web de Margie’s Travel, une agence de voyage fictive. Vous allez ensuite utiliser Language Studio pour voir comment la base de connaissances fonctionnera lorsqu’elle sera utilisée par les clients.

Lors de l’implémentation d’un bot, la première étape consiste à créer une base de connaissances de paires question/réponse. Celle-ci est utilisée avec des fonctionnalités intégrées de traitement du langage naturel afin que le bot puisse interpréter les questions et trouver la réponse la plus appropriée pour l’utilisateur.

Azure AI Language inclut des fonctionnalités de *réponse aux questions*, que vous utiliserez pour créer une base de connaissances. Les bases de connaissances peuvent être créées en entrant manuellement des paires question/réponse, ou à partir d’un document ou d’une page web existants. Margie’s Travel souhaite utiliser son document FAQ existant.

La fonctionnalité de réponses aux questions de Language Service vous permet de créer rapidement une base de connaissances, soit en entrant des paires question/réponse, soit à partir d’un document ou d’une page web existants. Il peut ensuite utiliser des fonctionnalités de traitement en langage naturel intégrées pour interpréter les questions et rechercher des réponses appropriées.

## Créer une ressource *Langage*

Pour utiliser la réponse aux questions, vous avez besoin d’une ressource **Language**.

1. Dans un nouvel onglet de navigateur, ouvrez le portail Microsoft Azure à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et connectez-vous avec le compte Microsoft associé à votre abonnement Azure.

1. Cliquez sur le bouton **&#65291;Créer une ressource** et recherchez le *service Language*. Sélectionnez **créer** un plan du **service Language**. Vous serez redirigé vers une page pour **sélectionner des fonctionnalités supplémentaires**. Utilisez les paramètres suivants :
    - **Sélectionner des fonctionnalités supplémentaires** :
        - **Fonctionnalités par défaut** : *conservez les fonctionnalités par défaut*.
        - **Fonctionnalités personnalisées** : *sélectionnez les réponses aux questions personnalisées*.
     - Sélectionnez **Continuer à créer votre ressource**
    ![Création d’une ressource du service Language avec activation des réponses aux questions personnalisées.](media/create-a-bot/create-language-service-resource.png)

1. Dans la page **Créer une ressource Language**, spécifiez les paramètres suivants :
    - **Détails du projet**
        - **Abonnement** : *votre abonnement Azure*.
        - **Groupe de ressources** : *sélectionnez un groupe de ressources ou créez-en un nouveau*.
    - **Détails de l’instance**
        - **Région** : *sélectionnez une région. Si vous êtes dans l’est des États-Unis, utilisez « USA Est 2 »*.      
        - **Nom** : *nom unique de votre ressource Language*.
        - **Niveau tarifaire** : S (1 000 appels par minute)
    - **Réponses à des questions personnalisées**
        - **Région de recherche Azure** : *n’importe quelle localisation disponible*.
        - **Niveau tarifaire Recherche Azure** : Gratuit F (3 index) : (*Si ce niveau n’est pas disponible, sélectionnez Basique*)
    - **Avis sur l’IA responsable**
        - **En cochant cette case, je certifie que j’ai vérifié et reconnu les termes dans l’avis sur l’IA responsable** : *sélectionné*.

1. Sélectionnez **Vérifier et créer**, puis sélectionnez **Créer**. Attendez la fin du déploiement de Language Service qui prendra en charge votre base de connaissances de réponses aux questions personnalisées.

    > **Remarque** Si vous avez déjà provisionné une ressource **Recherche cognitive Azure** de niveau gratuit, votre quota ne vous permettra peut-être pas d’en créer une autre. Dans ce cas, sélectionnez un autre niveau que **Gratuit F**.

## Création d'un projet

1. Sous un nouvel onglet de navigateur, ouvrez le portail Language Studio sur [https://language.azure.com](https://language.azure.com?azure-portal=true) et connectez-vous avec le compte Microsoft associé à votre abonnement Azure.
1. Si vous êtes invité à choisir une ressource de langue, sélectionnez les paramètres suivants :
    - **Annuaire Azure** : *L’annuaire Azure contenant votre abonnement*.
    - **Abonnement Azure** : *Votre abonnement Azure*.
    - **Ressource Language** : *La ressource Language que vous avez créée précédemment*.

    Si vous n’êtes ***pas*** invité à choisir une ressource de langue, c’est peut-être parce que vous avez plusieurs ressources de langue dans votre abonnement, auquel cas :
    1. Dans la barre située en haut si la page, sélectionnez **Paramètres (&#9881;)**.      
    1. Dans la page **Paramètres**, affichez l’onglet **Ressources**.
    1. Sélectionnez la ressource de langage que vous venez de créer, puis cliquez sur **Changer de ressource**.
    1. En haut de la page, sélectionnez **Language Studio** pour revenir à la page d’accueil de Language Studio.

1. En haut du portail Language Studio, dans le menu **Créer**, sélectionnez **Réponses aux questions personnalisées**.

    ![Réponses à des questions personnalisées](media/create-a-bot/create-custom-question-answering.png)

1. Dans la page **Choisissez le paramètre de langue pour la ressource *votre ressource***, sélectionnez **Je souhaite sélectionner la langue quand je crée un projet dans cette ressource**, puis cliquez sur **Suivant**.
  ![Je veux sélectionner la langue](media/create-a-bot/create-project.png)

1. Dans la page **Entrer les informations de base**, entrez les détails suivants et cliquez sur **Suivant** :
    - **Ressource de langue** : *Choisissez votre ressource de langue*.  
    - **Ressource de recherche Azure** : *Choisissez votre ressource de recherche Azure*.
    - **Nom :** `MargiesTravel`
    - **Description** : `A simple knowledge base`
    - **Langue source** : Anglais
    - **Réponse par défaut quand aucune réponse n’est retournée** : `No answer found`
1. Sur la page **Vérifier et terminer**, sélectionnez **Créer un projet**.
1. Vous êtes alors dirigé vers la page **Gérer les sources**. Sélectionnez **&#65291;Ajouter une source** et sélectionnez **URL**.
1. Dans la zone **Ajouter des URL**, sélectionnez **+ Ajouter une URL**. Tapez ce qui suit, puis sélectionnez **Tout ajouter** :
    - **Nom de l’URL** : `MargiesKB`
    - **URL** : `https://raw.githubusercontent.com/MicrosoftLearning/mslearn-ai-fundamentals/main/data/natural-language/margies_faq.docx`
    - **Classifier la structure des fichiers** : *détection automatique*
1. Sélectionnez **Ajouter tout.**  

 ![Ajouter une URL](media/create-a-bot/add-url.png)

## Modifier la base de connaissances

Votre base de connaissances est basée sur les détails du document FAQ et sur certaines réponses prédéfinies. Vous pouvez ajouter des paires question-réponse personnalisées pour compléter ces informations.

1. Développez le volet de gauche et sélectionnez **Modifier la base de connaissances**. Sélectionnez ensuite **+** pour ajouter une nouvelle paire question/réponse.
1. Dans la boîte de dialogue **Ajouter une nouvelle paire question/réponse**, dans **Question** entrez `Hello`, et dans **Réponse** entrez `Hi`, puis sélectionnez **Terminer**.
1. Développez **Questions alternatives**, puis sélectionnez **+ Ajouter une question alternative**. Ensuite, entrez `Hiya` en tant que formulation alternative pour « Bonjour ».
1. En haut du volet **Paires question/réponse**, sélectionnez **Enregistrer** pour enregistrer votre base de connaissances.

## Entraîner et tester la base de connaissances

Maintenant que vous avez une base de connaissances, vous pouvez la tester.

1. En haut du volet **Paires question/réponse**, sélectionnez **Tester** pour tester votre base de connaissances.
1. Dans la partie inférieure du volet de test, entrez le message `Hi`. La réponse *Salut* doit être renvoyée.
1. Dans la partie inférieure du volet de test, entrez le message `I want to book a flight`. Une réponse appropriée du FAQ devrait être retournée.

    > **Remarque** La réponse comprend une *réponse brève* ainsi qu’un *passage de réponse* plus détaillé. Le passage de réponse affiche le texte complet figurant dans le document de FAQ pour la question correspondante la plus proche, tandis que la réponse brève est extraite intelligemment du passage. Vous pouvez contrôler si la version courte vient de la réponse à l’aide de la case à cocher **Afficher la réponse courte** en haut du volet de test.

1. Essayez une autre question, par exemple `How can I cancel a reservation?`
1. Lorsque vous avez fini de tester la base de connaissances, sélectionnez **Tester** pour fermer le volet de test.

## Créer un bot pour la base de connaissances

La base de connaissances fournit un service principal que les applications clientes peuvent utiliser pour répondre aux questions via une sorte d’interface utilisateur. Généralement, ces applications clientes sont des bots. Pour mettre la base de connaissances à la disposition d’un bot, vous devez la publier en tant que service accessible via HTTP. Vous pouvez ensuite utiliser l’Azure Bot Service pour créer et héberger un bot utilisant la base de connaissances pour répondre aux questions des utilisateurs.

1. Dans le volet de gauche, sélectionnez **Déployer la base de connaissances**.
1. En haut de la page, sélectionnez **Déployer**. Une boîte de dialogue va vous demander si vous voulez déployer le projet. Sélectionnez **Déployer**.

 ![Déployez la base de connaissances.](media/create-a-bot/deploy-knowledge-base.png)

1. Une fois le service déployé, sélectionnez **Créer un bot**. Cela a pour effet d’ouvrir le portail Azure dans un nouvel onglet de navigateur pour vous permettre de créer un bot d’application web dans votre abonnement Azure.
1. Dans le portail Microsoft Azure, créez un **bot d’application web**. (Vous pouvez voir un message d’avertissement demandant de vérifier si la source du modèle est fiable. Vous n’avez pas besoin d’effectuer une action pour ce message.) Continuez en mettant à jour les paramètres suivants :

    - **Détails du projet**
        - **Abonnement** : *votre abonnement Azure*
        - **Groupe de ressources** : *groupe de ressources contenant votre ressource linguistique*
    - **Détails de l’instance**
        - **Emplacement du groupe de ressources** : *le même emplacement que votre service de langage*.
    - **Azure Bot**
        - **Descripteur du bot** : *nom unique de votre bot* (*prérempli*)
    - **Choisir votre niveau tarifaire**
        - **Niveau tarifaire** : Gratuit (F0) (Il peut être nécessaire de sélectionner *Changer de plan*)
    - **ID d’application Microsoft**
        - **Type de création** : *Sélectionnez **Créer une identité managée affectée par l’utilisateur*** 

5. Sélectionnez **Suivant** pour continuer la mise à jour des paramètres. 
    - **App Service**
        - **Nom de l’application** : *identique au **Descripteur du bot** avec **.azurewebsites.net** ajouté automatiquement*
        - **Langage du Kit de développement logiciel (SDK)**  : *choisissez C# ou Node.js*
    - **Plan App Service**
        - **Type de création** : *Sélectionnez **Créer un plan App Service***
    - **Paramètres de l’application**
        - **Clé de ressource Language** : *Vous devez copier votre clé de ressource Language et la coller ici* :
            - Ouvrez un autre onglet du navigateur et accédez au portail Microsoft Azure à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true).
            - Accédez à votre ressource de service Language.
            - Dans la page **Clés et point de terminaison**, copiez l’une des clés.
            - Collez-la ici.
        - **Nom du projet de langue** : MargiesTravel
        - **Nom d’hôte du point de terminaison du service de langue** : *prérempli avec votre point de terminaison de service de langue*
    - **Détails du service de langue**
        - **ID d’abonnement** : *prérempli avec votre ID d’abonnement*
        - **Nom du groupe de ressources** : *prérempli avec le nom de votre groupe de ressources*
        - **Nom du compte** : *prérempli avec le nom de votre ressource*

1. Sélectionnez **Créer**. Puis, attendez que votre bot soit créé (l’icône de notification en haut à droite, qui ressemble à une cloche, sera animée pendant que vous attendez). Ensuite, dans la notification indiquant que le déploiement est terminé, sélectionnez **Aller à la ressource** (ou alternativement, sur la page d’accueil, cliquez sur **Groupes de ressources**, ouvrez le groupe de ressources où vous avez créé le bot et sélectionnez la ressource **Bot Azure**).
1. Dans le volet gauche de votre bot, recherchez **Paramètres**, sélectionnez **Tester dans Web Chat**, puis attendez que le bot affiche le message **Bonjour et bienvenue** (l’initialisation peut prendre quelques secondes).
1. Utilisez l’interface de test de conversation pour vous assurer que votre bot répond aux questions à partir de votre base de connaissances comme prévu. Par exemple, essayez d’envoyer `I need to cancel my hotel`.

Essayez le bot. Vous constaterez probablement qu’il peut répondre à des questions du FAQ de manière très précise, mais qu’il est limité quant à sa capacité à interpréter les questions auxquelles son apprentissage ne l’a pas préparé. Vous pouvez toujours utiliser Language Studio pour modifier la base de connaissances afin de l’améliorer, puis la republier.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Microsoft Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée. 
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

- Pour en savoir plus sur le service Réponses aux questions, consultez [cette documentation](https://docs.microsoft.com/azure/cognitive-services/language-service/question-answering/overview).
- Pour en savoir plus sur le Microsoft Bot Service, consultez la [page Azure Bot Service](https://azure.microsoft.com/services/bot-service/).
