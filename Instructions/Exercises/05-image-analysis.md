---
lab:
  title: "Analyser des images dans le portail Azure\_AI\_Foundry"
---

# Analyser des images dans le portail Azure AI Foundry

**Azure AI Vision** regroupe de nombreuses fonctionnalités qui permettent de comprendre le contenu et le contexte des images et d’en extraire des informations. Dans cet exercice, vous allez utiliser Azure AI Vision dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, afin d’analyser des images à l’aide des expériences de test intégrées. 

Supposons que la société de vente au détail fictive *Les Commerçants du Vent du Nord* ait décidé de mettre en place un « magasin intelligent », dans lequel des services d’IA supervisent la boutique afin d’identifier les clients qui ont besoin d’aide et d’orienter les employés pour qu’ils les assistent. Grâce à Azure AI Vision, les images prises par les caméras du magasin peuvent être analysées pour fournir des descriptions utiles de leur contenu.

Cet exercice prend environ **20** minutes.

## Télécharger et extraire des fichiers image

1. Téléchargez **[image-analysis.zip](https://aka.ms/mslearn-images-for-analysis)** à partir de `https://aka.ms/mslearn-images-for-analysis`.
1. Extrayez le fichier .zip téléchargé dans un dossier sur votre ordinateur.

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil du portail Azure AI Foundry.](./media/ai-foundry-portal.png)

1. Faites défiler vers le bas de la page, puis sélectionnez la vignette **Explorer Azure AI Services**.

    ![Capture d’écran de la vignette Explorer Azure AI Services.](./media/ai-services.png)

1. Dans la page Azure AI Services, sélectionnez la vignette **Vision + Document**.

    ![Capture d’écran de la vignette Vision + Document.](./media/vision-tile.png)

1. Dans la page **Vision + Document**, affichez l’onglet **Image** et sélectionnez la vignette **Légende d’image**.

    ![Capture d’écran de la vignette de légende d’image.](./media/image-captioning-tile.png)

1. Dans le volet **Ajouter des légendes aux images**, utilisez le bouton **Sélectionner un hub** pour **créer un hub** avec les paramètres suivants :
    - **Nom du hub** : *entrez un nom valide pour votre hub.*
    - **Abonnement** : *votre abonnement Azure*
    - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
    - **Emplacement** : *sélectionnez l’un des emplacements suivants* :
        - USA Est
        - France Centre
        - Centre de la Corée
        - Europe Ouest
        - USA Ouest
    - **Se connecter à Azure AI Services** : *créer une ressource Azure AI Services avec un nom valide*
    - **Connecter la Recherche Azure AI** : ignorer la connexion

    \**Au moment de l’écriture, Azure AI Vision est pris en charge dans les hubs de ces régions*.

1. Une fois le hub créé, vous serez invité à créer un projet. Entrez un nom de projet approprié et sélectionnez **Créer un projet**.

## Générer des légendes pour une image

Utilisons la fonctionnalité de sous-titrage d’image d’Azure AI Vision pour analyser les images prises par une caméra dans le magasin *Northwind Traders*. Les légendes d’image sont accessibles via les fonctionnalités **Légende** et **Légendes denses**.

1. Dans le volet des tâches de gauche, sélectionnez **Services IA**.

    *Vous devez maintenant répéter les étapes que vous avez exécutées précédemment pour revenir à l’interface de légende d’image et utiliser votre nouveau projet hub.*

1. Dans la page **Services IA**, sélectionnez la vignette **Vision + Document**. Ensuite, dans la page **Vision + Document**, sous l’onglet **Image**, sélectionnez la vignette **Légende d’image**.

1. Sur la page **Ajouter des légendes aux images**, sous le menu de sélection *Services Azure AI connectés*, vérifiez que la ressource des services Azure AI que vous avez créée dans votre hub est sélectionnée.

1. Utilisez le lien **Rechercher un fichier** pour charger l’image **store-camera-1.jpg** à partir des fichiers que vous avez téléchargés et extraits précédemment.

1. Observez le texte de la légende générée, visible dans le panneau **Attributs détectés** à droite de l’image.

    ![Capture d’écran de la page Ajouter des légendes aux images avec une image analysée.](./media/image-captioning.png)

    La fonctionnalité **Légende** fournit une phrase en anglais, facile à lire et qui décrit le contenu de l’image.

1. Utilisez ensuite la même image pour obtenir un **Texte de légende dense**. Revenez à la page **Vision + Document** en sélectionnant la **&larr;** flèche *arrière* en haut de la page, puis sur la page **Vision + Document**, sous l’onglet **Image**, en sélectionnant la vignette **Légende dense**.

    La fonctionnalité **Texte de légende denses** diffère de la fonctionnalité **Légende** car elle fournit plusieurs légendes faciles à lire pour une image, dont l’une décrit le contenu de l’image et les autres décrivent les objets principaux détectés dans l’image. Chaque objet détecté dispose d’un cadre englobant qui définit les coordonnées des pixels de l’image associés à l’objet.

1. Chargez à nouveau l’image **store-camera-1.jpg** et affichez les résultats de la légende dense.

    ![Capture d’écran des résultats de la légende dense.](./media/dense-captioning.png)

    Passez votre souris sur l’une des légendes de la liste **Attributs détectés** pour voir qu’une légende est générée pour chaque objet détecté dans l’image.

## Étiquetage des images 

La fonctionnalité suivante que vous allez essayer est la fonctionnalité *Extraire des étiquettes*. Extraire des étiquettes est basé sur des milliers d’objets reconnaissables, y compris des êtres vivants, des paysages et des actions.

1. Revenez à la page **Vision + Document** en sélectionnant la **&larr;** flèche *arrière* en haut de la page. Ensuite, dans la page **Vision + Document**, sous l’onglet **Image**, sélectionnez la vignette **Extraction de balise courante**.
1. Chargez le fichier **store-camera-2.jpg** à partir du dossier que vous avez extrait précédemment.
1. Passez en revue la liste des balises extraites de l’image et le score de confiance pour chacune d’entre elles dans le panneau des attributs détectés. Le score de confiance correspond ici à la probabilité que le texte de l’attribut détecté décrive réellement ce qui se trouve dans l’image. Remarquez dans la liste des étiquettes qu’elle inclut non seulement des objets, mais aussi des actions, telles que *faire des achats*, *vendre*et *se tenir debout*.

    ![Capture d’écran du panneau des attributs de détection dans Vision Studio avec le texte et les indices de confiance affichés à côté de l’image originale.](./media/analyze-images-vision/detect-attributes.png)

## Détection d’objets

Dans cette tâche, vous utilisez la fonctionnalité **Détection d’objet** de Analyse d’images. La détection d’objets permet de détecter et d’extraire des cadres englobants sur la base de milliers d’objets et d’êtres vivants reconnaissables.

1. Revenez à la page **Vision + Document** en sélectionnant la **&larr;** flèche *arrière* en haut de la page. Ensuite, sous l’onglet **Image**, sélectionnez la vignette **Détection d’objet courant**.

1. Chargez le fichier **store-camera-3.jpg**.

1. Dans la zone **Attributs détectés**, observez la liste des objets détectés et leurs scores de confiance.

    ![Capture d’écran des résultats de la légende dense.](./media/object-detection.png)

1. Essayez de détecter les objets dans **store-camera-4.jpg**.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressource que vous avez créées. 
1. Sélectionnez **Supprimer le groupe de ressources**, puis **entrez le nom du groupe de ressources** pour confirmer. Le groupe de ressources est ensuite supprimé.

## En savoir plus

Pour en savoir plus sur ce que vous pouvez faire avec ce service, consultez la [page Azure AI Vision](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
