---
lab:
  title: Détecter des visages dans Vision Studio
---

# Détecter des visages dans Vision Studio

Les solutions Vision nécessitent souvent que l’IA puisse détecter des visages humains. Supposons que la société de vente au détail Northwind Traders souhaite localiser des clients dans un magasin pour mieux les assister. Une façon d’y parvenir consiste à déterminer la présence de visages dans les images et, le cas échéant, à retourner les coordonnées du cadre englobant pour indiquer leur emplacement.

Pour tester les fonctionnalités de détection des visages du service Azure AI Visage, vous allez utiliser [Azure Vision Studio](https://portal.vision.cognitive.azure.com/). Il s’agit d’une plateforme basée sur l’interface utilisateur qui vous permet d’explorer les fonctionnalités d’Azure AI Vision sans écrire de code.

## Créer une ressource *Azure AI services*

Vous pouvez utiliser le service Azure AI Visage avec une ressource multiservices **Azure AI Services**. Si ce n’est déjà fait, créez une ressource **Azure AI services** dans votre abonnement Azure.

1. Dans un autre onglet du navigateur, ouvrez le portail Azure à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et connectez-vous avec le compte Microsoft associé à votre abonnement Azure.

1. Cliquez sur le bouton **&#65291;Créer une ressource** et recherchez *Azure AI services*. Sélectionnez **créer** un plan **Azure AI services**. Vous accédez à une page pour créer une ressource Azure AI services. Configurez-la avec les paramètres suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
    - **Région** : *Sélectionnez la région géographique la plus proche. Si vous êtes dans l’est des États-Unis, utilisez « USA Est 2 »*.
    - **Nom** : *entrez un nom unique.*
    - **Niveau tarifaire** : *Standard S0.*
    - **En cochant cette case, je reconnais avoir lu et compris toutes les conditions ci-dessous** : *Sélectionné*.

1. Sélectionnez **Vérifier + créer**, puis **Créer** et attendez la fin du déploiement.

## Connecter votre ressource de service Azure AI à Vision Studio

Ensuite, connectez la ressource Azure AI services que vous avez approvisionnée ci-dessus à Vision Studio.

1. Dans un autre onglet de navigateur, accédez à **Vision Studio** à l’adresse [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Connectez-vous avec votre compte et vérifiez que vous utilisez le même répertoire que celui dans lequel vous avez créé votre ressource Azure AI services.

1. Sur la page d’accueil de Vision Studio, sélectionnez **Afficher toutes les ressources** sous le titre **Démarrage avec Vision**.

    ![Dans Vision Studio, Le lien Afficher toutes les ressources est en surbrillance dans la section Démarrage avec Vision.](./media/analyze-images-vision/vision-resources.png)

1. Sur la page **Sélectionner une ressource à utiliser**, placez le curseur de votre souris sur la ressource que vous avez créée ci-dessus dans la liste, puis cochez la case à gauche du nom de la ressource et sélectionnez **Sélectionner comme ressource par défaut**.

    > **Remarque** : Si votre ressource n’est pas répertoriée, vous devrez peut-être **Actualiser** la page.

    ![La boîte de dialogue Sélectionner une ressource à utiliser s’affiche avec la ressource Cognitive Services cog-ms-learn-vision-SUFFIX mise en surbrillance et cochée. Le bouton Sélectionner comme ressource par défaut est en surbrillance.](./media/analyze-images-vision/default-resource.png)

1. Fermez la page des paramètres en sélectionnant le « x » en haut à droite de l’écran.

## Détecter des visages dans Vision Studio 

1. Dans un navigateur web, accédez à **Vision Studio** à l’adresse [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Dans la page d’accueil **Prise en main de Vision**, sélectionnez l’onglet **Visage**, puis la vignette **Détecter les visages dans une image**.

1. Sous le sous-titre **Essayer**, acceptez la stratégie d’utilisation des ressources en lisant et en cochant la case.  

1. Sélectionnez chacun des exemples d’images et observez les données de détection des visages retournées.

1. Nous allons maintenant essayer avec certaines de nos images. Sélectionnez [**https://aka.ms/mslearn-detect-faces**](https://aka.ms/mslearn-detect-faces) pour télécharger **detect-faces.zip**. Ouvrez ensuite le dossier sur votre ordinateur.

1. Recherchez le fichier nommé **store-camera-1.jpg**, qui contient l’image suivante :

    ![Image de personnes dans un magasin.](./media/create-face-solutions/store-camera-1.jpg)

1. Chargez **store-camera-1.jpg** et passez en revue les informations de détection des visages retournées.

1. Recherchez le fichier nommé **store-camera-2.jpg**, qui contient l’image suivante :

    ![Image d’un plus grand nombre de personnes dans un magasin.](./media/create-face-solutions/store-camera-2.jpg)

1. Chargez **store-camera-2.jpg** et passez en revue les informations de détection des visages retournées.

1. Recherchez le fichier nommé **store-camera-3.jpg**, qui contient l’image suivante :

    ![Image de personnes dans un magasin avec une plante masquant un visage.](./media/create-face-solutions/store-camera-3.jpg)

1. Chargez **store-camera-3.jpg** et passez en revue les informations de détection de visages renvoyées. Notez comment Azure AI Visage n’a pas détecté le visage masqué.

Dans cet exercice, vous avez découvert comment Azure AI services peuvent détecter des visages dans des images. Si vous avez du temps, n’hésitez pas à essayer les exemples d’images ou certaines de vos images.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **Portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page sur le service Azure AI Visage](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-identity).
