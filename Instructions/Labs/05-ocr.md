---
lab:
  title: Lire du texte dans Vision Studio
---

# Lire du texte dans Vision Studio

Dans cet exercice, vous utiliserez le service Azure AI pour explorer les capacités de reconnaissance optique de caractères d'Azure AI Vision. Vous utiliserez Vision Studio pour expérimenter l'extraction de texte à partir d'images, sans avoir à écrire de code.

Un défi courant en matière de vision par ordinateur consiste à détecter et à interpréter du texte intégré dans une image. C’est ce qu’on appelle la reconnaissance optique de caractères (OCR). Dans cet exercice, vous utiliserez une ressource Azure AI services, qui comprend les services Azure AI Vision. Vous utiliserez ensuite Vision Studio pour tester l’OPR avec différents types d’images.

## Créer une ressource *Azure AI services*

Vous pouvez utiliser les capacités d’OPR Azure AI Vision avec une ressource multiservices **Azure AI Services**. Si ce n’est déjà fait, créez une ressource **Azure AI services** dans votre abonnement Azure.

1. Dans un nouvel onglet de navigateur, ouvrez le **Portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et connectez-vous avec le compte Microsoft associé à votre abonnement Azure.

1. Cliquez sur le bouton **&#65291;Créer une ressource** et recherchez *Azure AI services*. Sélectionnez **créer** un plan **Azure AI services**. Vous accédez à une page pour créer une ressource Azure AI services. Configurez-la avec les paramètres suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
    - **Région** : USA Est.
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

## Extraire du texte à partir d’images dans Vision Studio
    
1. Dans un navigateur web, accédez à **Vision Studio** à l’adresse [https://portal.vision.cognitive.azure.com](https://portal.vision.cognitive.azure.com?azure-portal=true).

1. Dans la page d’accueil **Prise en main de Vision**, sélectionnez **Reconnaissance optique des caractères**, puis **extrayez le texte de la vignette d’images**.

1. Sous le sous-titre **Essayer**, acceptez la stratégie d’utilisation des ressources en lisant et en cochant la case.  

1. Sélectionnez [**https://aka.ms/mslearn-ocr-images**](https://aka.ms/mslearn-ocr-images) pour télécharger **ocr-images.zip**. Ouvrez ensuite le dossier.

1. Sur le portail, sélectionnez **Rechercher un fichier** et accédez au dossier sur votre ordinateur où vous avez téléchargé **ocr-images.zip**. Sélectionnez **advert.jpg** et sélectionnez **Ouvrir**.

1. Examinez maintenant ce qui est renvoyé :
    - Dans **Attributs détectés**, tout texte trouvé dans l’image est organisé en une structure hiérarchique de régions, de lignes et de mots.
    - Sur l’image, l’emplacement du texte est indiqué par un cadre englobant, comme illustré ici :

    ![Image du texte dans l’image décrite.](media/read-text-computer-vision/advert-bounding-boxes.jpg)

1. Vous pouvez maintenant essayer une autre image. Sélectionnez **Rechercher un fichier** et accédez au dossier dans lequel vous avez enregistré les fichiers depuis GitHub. Sélectionnez **letter.jpg**.

    ![Image d’une lettre dactylographiée.](media/read-text-computer-vision/letter.jpg)

1. Examinez les résultats de la deuxième image. Elle doit retourner le texte et les cadres englobants du texte. Si vous avez du temps, essayez **note.jpg** et **receipt.jpg**.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le **Portail Azure** à l’adresse [https://portal.azure.com](https://portal.azure.com?azure-portal=true) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Pour en savoir plus sur ce que vous pouvez faire avec ce service, consultez la documentation d'Azure AI Vision sur la [reconnaissance optique de caractères](https://learn.microsoft.com/azure/ai-services/computer-vision/overview-ocr).
