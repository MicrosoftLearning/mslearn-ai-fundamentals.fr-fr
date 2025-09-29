---
lab:
  title: "Explorer Speech dans le portail Azure\_AI\_Foundry"
---

# Explorer Speech dans le portail Azure AI Foundry

Azure AI Speech transcrit la parole en texte et transforme le texte en parole audible. Vous pouvez utiliser AI Speech pour créer une application qui peut transcrire des notes de réunion ou générer du texte à partir de l’enregistrement d’un entretien, ou pour prendre en charge un assistant IA interactif capable de répondre aux commandes et requêtes parlées.

Dans cet exercice, vous allez utiliser Azure AI Speech dans le portail Azure AI Foundry, plateforme de Microsoft pour créer des applications intelligentes, pour explorer les principales fonctionnalités d’Azure AI Speech. 

Cet exercice prend environ **15** minutes.

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil du portail Azure AI Foundry.](./media/ai-foundry-portal.png)

1. Faites défiler vers le bas de la page, puis sélectionnez la vignette **Explorer Azure AI Services**.

    ![Capture d’écran de la vignette Explorer Azure AI Services.](./media/ai-services.png)

1. Dans la page Azure AI Services, sélectionnez la vignette **Speech**.

    ![Capture d’écran de la vignette Speech.](./media/speech.png)

1. Dans la page **Speech**, sélectionnez **Accéder au terrain de jeu Speech**. Ensuite, lorsque vous y êtes invité, créez un projet avec les paramètres suivants :
    - **Nom du projet** : *entrez un nom valide pour votre projet.*
    - **Paramètres avancés** :
        - **Abonnement** : *votre abonnement Azure*
        - **Groupe de ressources** : *créez ou sélectionnez un groupe de ressources*
        - **Région** : *sélectionnez n’importe quelle région **AI Foundry** recommandée*
        - **AI Foundry ou Azure OpenAI** *Créer une ressource Azure AI Foundry avec un nom valide*

1. Sélectionnez **Créer**. Attendez que votre projet soit créé. Cette opération peut prendre quelques minutes.

1. Lorsque le projet est créé, vous serez redirigé vers un terrain de jeu **Speech** (si ce n’est pas le cas, dans le volet des tâches à gauche, sélectionnez **Terrains de jeu** et ouvrez le terrain de jeu Speech à partir de là.)

    Le terrain de jeu Speech est une interface utilisateur qui vous permet d’essayer certaines fonctionnalités d’Azure AI Speech.  

## Explorer la reconnaissance vocale dans le terrain de jeu Speech d’Azure AI Foundry

Essayons la *reconnaissance vocale* dans le terrain de jeu Speech d’Azure AI Foundry.

1. Dans un nouvel onglet de navigateur, téléchargez **[speech.zip](https://aka.ms/mslearn-speech-files)** à partir de `https://aka.ms/mslearn-speech-files`. Après avoir téléchargé le fichier, extrayez-le dans un dossier local. 

1. De retour dans le portail Azure AI Foundry, sur la page Speech, sous l’onglet **Reconnaissance vocale**, sélectionnez **Transcription en temps réel**.

1. Sous **Charger des fichiers**, sélectionnez **Parcourir les fichiers** et chargez **WhatAICanDo.m4a** à partir du dossier téléchargé et extrait.

    Le service Speech transcrit et affiche le texte en temps réel. Si vous disposez d'un système audio sur votre ordinateur, vous pouvez écouter l'enregistrement pendant la transcription du texte.

    ![Capture d’écran de l’interface de transcription en temps réel dans le terrain de jeu Speech.](./media/real-time-transcription.png)

1. Passez en revue la sortie. 

    >*Conseil* : Pour afficher le résultat complet, vous devrez peut-être réduire le volet *Configurer*. Pour le réduire la taille, sélectionnez l’icône à droite du titre *Configurer*.

    Dans le résultat, sous **Texte**, vous pouvez voir l’audio transcrit en texte.

## Explorer la synthèse vocale dans le terrain de jeu Speech d’Azure AI Foundry

Voyons maintenant comment Azure AI Speech peut générer des paroles audibles à partir de texte.

1. Dans le terrain de jeu Speech, sélectionnez l’onglet **Synthèse vocale** et vérifiez que **Galerie de voix** est sélectionné.
1. Affichez les voix disponibles et sélectionnez-en une (par exemple, *Ava Multilingue*).
1. Dans le volet **Détails de la voix**, sélectionnez l’onglet **Essayer**. Entrez ensuite du texte (par exemple, `The rain in Spain stays mainly in the plain`) et utilisez le bouton **Lecture** pour synthétiser la voix à partir du texte.

    ![Capture d’écran de l’interface de la galerie de voix dans le terrain de jeu Speech.](./media/voice-gallery.png)

    Le texte est parlé à l’aide de la voix sélectionnée. Vous pouvez essayer d’autres voix pour comparer la sortie parlée.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Microsoft Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez **Supprimer le groupe de ressources**, puis **entrez le nom du groupe de ressources** pour confirmer. Le groupe de ressources est ensuite supprimé.

## En savoir plus

Cet exercice n’a démontré qu’une des nombreuses fonctionnalités du service de reconnaissance vocale. Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page Speech](https://azure.microsoft.com/services/cognitive-services/speech-services).
