---
lab:
  title: "Analyser des images dans le portail Azure\_AI\_Foundry"
---

# Analyser des images dans le portail Azure AI Foundry

**Azure AI Vision** regroupe de nombreuses fonctionnalités qui permettent de comprendre le contenu et le contexte des images et d’en extraire des informations. Dans cet exercice, vous allez utiliser Azure AI Vision dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, afin d’analyser des images à l’aide des expériences de test intégrées. 

Supposons que la société de vente au détail fictive *Les Commerçants du Vent du Nord* ait décidé de mettre en place un « magasin intelligent », dans lequel des services d’IA supervisent la boutique afin d’identifier les clients qui ont besoin d’aide et d’orienter les employés pour qu’ils les assistent. Grâce à Azure AI Vision, les images prises par les caméras du magasin peuvent être analysées pour fournir des descriptions utiles de leur contenu.

## Créer un projet dans le portail Azure AI Foundry

1. Dans un onglet de navigateur, accédez à [Azure AI Foundry](https://ai.azure.com?azure-portal=true).

1. Connectez-vous avec votre compte. 

1. Sur la page d’accueil du portail Azure AI Foundry, sélectionnez **Créer un projet**. Dans Azure AI Foundry, les projets sont des conteneurs qui aident à organiser votre travail.  

    ![Capture d’écran de la page d’accueil d’Azure AI Foundry avec l’option de création d’un projet sélectionné.](./media/azure-ai-foundry-home-page.png)

1. Dans le volet *Créer un projet*, vous verrez un nom de projet généré, que vous pouvez conserver en l’état. Selon que vous avez créé un hub par le passé, vous verrez une liste de *nouvelles* ressources Azure à créer ou une liste déroulante de hubs existants. Si vous voyez la liste déroulante des hubs existants, sélectionnez *Créer un hub*, créez un nom unique pour votre hub, puis sélectionnez *Suivant*.  
 
    ![Capture d’écran du volet Créer un projet avec des noms générés automatiquement pour le hub et le projet.](./media/azure-ai-foundry-create-project.png)

    > **Important** : vous aurez besoin d’une ressource de services Azure AI configurée dans un emplacement spécifique pour effectuer le reste du labo.

1. Dans le même volet *Créer un projet*, sélectionnez **Personnaliser** et sélectionnez l’un des **emplacements** suivants : *USA Est, France Centre, Corée Centre, Europe Ouest ou USA Ouest* pour terminer le reste du labo. Sélectionnez **Suivant**, puis **Créer**. 

1. Notez les ressources créées : 
    - Azure AI services
    - Azure AI Hub
    - Projet Azure AI
    - Compte de stockage
    - Key vault
    - Resource group  
 
1. Une fois les ressources créées, vous serez redirigé vers la page *Vue d’ensemble* de votre projet. Dans le menu de gauche de l’écran, sélectionnez **Services d’IA**.
 
    ![Capture d’écran du menu de gauche de l’écran du projet avec Services d’IA sélectionnés.](./media/azure-ai-foundry-ai-services.png)  

1. Dans la page *Services d’IA*, sélectionnez la vignette *Vision + Document* pour essayer les fonctionnalités Azure AI Vision et Document.

    ![Capture d’écran de la vignette Vision et Document sélectionnée dans la page Services d’IA.](./media/vision-document-tile.png)

## Générer des légendes pour une image

Utilisons la fonctionnalité de sous-titrage d’image d’Azure AI Vision pour analyser les images prises par une caméra dans le magasin *Northwind Traders*. Les légendes d’image sont accessibles via les fonctionnalités **Légende** et **Légendes denses**.

1. Dans la page *Vision + Document*, faites défiler vers le bas et sélectionnez **Image** dans *Afficher toutes les autres fonctionnalités de vision*. Sélectionnez ensuite la vignette de **Sous-titrage d’image**.

    ![Capture d’écran de la vignette de sous-titres d’image dans la section Image de la page Vision et Document.](./media/vision-image-captioning-tile.png)

1. Dans la page **Ajouter des sous-titres à des images**, passez en revue la ressource à laquelle vous êtes connecté, qui est répertoriée dans le sous-titre **Essayer**. Vous ne devez pas avoir à apporter de modifications. (*Remarque* : si vous n’avez pas personnalisé un emplacement de ressource valide précédemment lors de la création de la ressource, vous devrez peut-être créer une ressource Azure AI Services qui se trouve dans une région valide. Vous devez créer la nouvelle ressource pour continuer avec le labo.)  

1. Sélectionnez [**https://aka.ms/mslearn-images-for-analysis**](https://aka.ms/mslearn-images-for-analysis) pour télécharger **image-analysis.zip**. Ouvrez le dossier sur votre ordinateur et localisez le fichier nommé **store-camera-1.jpg**, qui contient l’image suivante :

    ![Image d’un parent utilisant une caméra de téléphone portable pour prendre une photo d’un enfant dans un magasin](./media/analyze-images-vision/store-camera-1.jpg)

1. Chargez l’image **store-camera-1.jpg** en la faisant glisser vers la zone **Glisser-déposer des fichiers ici**, ou en la recherchant sur votre système de fichiers.

1. Observez le texte de la légende générée, visible dans le panneau **Attributs détectés** à droite de l’image.

    La fonctionnalité **Légende** fournit une phrase en anglais, facile à lire et qui décrit le contenu de l’image.

1. Utilisez ensuite la même image pour obtenir un **Texte de légende dense**. Revenez à la page **Vision + Document** en sélectionnant la flèche *arrière* en haut de la page. Dans la page *Vision + Document*, sélectionnez l’onglet **Image**, puis la vignette **Sous-titrage dense**.

    La fonctionnalité **Texte de légende denses** diffère de la fonctionnalité **Légende** car elle fournit plusieurs légendes faciles à lire pour une image, dont l’une décrit le contenu de l’image et les autres décrivent les objets principaux détectés dans l’image. Chaque objet détecté dispose d’un cadre englobant qui définit les coordonnées des pixels de l’image associés à l’objet.

1. Placez le curseur de la souris sur l’une des légendes dans la liste des attributs **Détectés** et observez ce qui se passe dans l’image.

    ![L’image et ses légendes s’affichent.](./media/analyze-images-vision/dense-captioning.png)

    Déplacez le curseur de votre souris sur les autres légendes de la liste et observez comment le cadre se déplace dans l’image pour mettre en évidence la partie de l’image utilisée pour générer la légende.

## Étiquetage des images 

La fonctionnalité suivante que vous allez essayer est la fonctionnalité *Extraire des étiquettes*. Extraire des étiquettes est basé sur des milliers d’objets reconnaissables, y compris des êtres vivants, des paysages et des actions.

1. Revenez à la page *Vision + Document* d’Azure AI Foundry, sélectionnez l’onglet **Image**, puis la vignette **Extraction de balise commune**.

2. Dans la section **Choisir le modèle que vous souhaitez essayer**, ne décochez pas l’option **Produit prédéfini et modèle différentiel**. Dans le champ **Choisissez votre langue**, sélectionnez **Anglais** ou la langue de votre choix.

3. Ouvrez le dossier qui contient les images que vous avez téléchargées et recherchez le fichier nommé **store-image-2.jpg**, qui ressemble à ceci :

    ![Image d’une personne munie d’un panier d’achat dans un supermarché](./media/analyze-images-vision/store-camera-2.jpg)

4. Chargez le fichier **store-camera-2.jpg**.

5. Passez en revue la liste des balises extraites de l’image et le score de confiance pour chacune d’entre elles dans le panneau des attributs détectés. Le score de confiance correspond ici à la probabilité que le texte de l’attribut détecté décrive réellement ce qui se trouve dans l’image. Remarquez dans la liste des étiquettes qu’elle inclut non seulement des objets, mais aussi des actions, telles que *faire des achats*, *vendre*et *se tenir debout*.

    ![Capture d’écran du panneau des attributs de détection dans Vision Studio avec le texte et les indices de confiance affichés à côté de l’image originale.](./media/analyze-images-vision/detect-attributes.png)

## Détection d’objets

Dans cette tâche, vous utilisez la fonctionnalité **Détection d’objet** de Analyse d’images. La détection d’objets permet de détecter et d’extraire des cadres englobants sur la base de milliers d’objets et d’êtres vivants reconnaissables.

1. Revenez à la page *Vision + Document* d’Azure AI Foundry, sélectionnez l’onglet **Image**, puis la vignette **Détection d’objet courante**.

1. Dans la section **Choisir le modèle que vous souhaitez essayer**, ne décochez pas l’option **Produit prédéfini et modèle différentiel**.

1. Ouvrez le dossier qui contient les images que vous avez téléchargées et recherchez le fichier nommé **store-image-3.jpg**, qui ressemble à ceci :

    ![Image d’une personne munie d’un caddie](./media/analyze-images-vision/store-camera-3.jpg)

1. Chargez le fichier **store-camera-3.jpg**.

1. Dans la zone **Attributs détectés**, observez la liste des objets détectés et leurs scores de confiance.

1. Passez le curseur de votre souris sur les objets de la liste **Attributs détectés** pour mettre en surbrillance le cadre englobant de l’objet dans l’image.

1. Déplacez le curseur de **Valeur du seuil** jusqu’à ce qu’une valeur de 70 soit affichée à droite du curseur. Observez ce qui se passe avec les objets de la liste. Le curseur de seuil spécifie que seuls les objets identifiés avec un score de confiance ou une probabilité supérieure au seuil doivent être affichés.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1.  Ouvrez le [portail Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient les ressource que vous avez créées. 
1.  Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Pour en savoir plus sur ce que vous pouvez faire avec ce service, consultez la [page Azure AI Vision](https://learn.microsoft.com/azure/ai-services/computer-vision/overview).
