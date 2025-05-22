---
lab:
  title: "Explorer Speech dans le portail Azure\_AI\_Foundry"
---

# Explorer Speech dans le portail Azure AI Foundry

Le service **Azure AI Speech** transcrit la parole en texte et le texte en parole audible. Vous pouvez utiliser AI Speech pour créer une application capable de transcrire des notes de réunion ou de générer du texte à partir de l'enregistrement d'entretiens.

Dans cet exercice, vous allez utiliser Azure AI Speech dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, afin de transcrire l’audio à l’aide des expériences de test intégrées. 

## Créer un projet dans le portail Azure AI Foundry

Commençons par créer un projet Azure AI Foundry.

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts la première fois que vous vous connectez et, si nécessaire, utilisez le logo **Azure AI Foundry** en haut à gauche pour accéder à la page d’accueil, qui ressemble à l’image suivante (fermez le volet **Aide** s’il est ouvert) :

    ![Capture d’écran de la page d’accueil d’Azure AI Foundry avec l’option de création d’un assistant sélectionné.](./media/azure-ai-foundry-home-page.png)

1. Sur la page d’accueil, sélectionnez **+Créer un agent**.

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

1. Dans la page *Terrains de jeu*, sélectionnez la vignette **Terrain de jeu Speech** pour essayer certaines fonctionnalités Azure AI Speech.

## Explorer la reconnaissance vocale dans le terrain de jeu Speech d’Azure AI Foundry

Essayons la *reconnaissance vocale* dans le terrain de jeu Speech d’Azure AI Foundry. 

1. Dans la page *Speech*, faites défiler vers le bas et sélectionnez **Transcription en temps réel** dans *Essayer les fonctionnalités Speech*. Vous serez dirigé vers le *terrain de jeu Speech*. 

1. Sélectionnez [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) pour télécharger **speech.zip**. Ouvrez le dossier . 

1. Dans *Charger les fichiers*, sélectionnez **Parcourir les fichiers** et accédez au dossier dans lequel vous avez enregistré le fichier. Sélectionnez **WhatAICanDo.m4a**, puis **Ouvrir**.

    ![Parcourir les fichiers](media/recognize-synthesize-speech/browse-files-speech.png)

1. Le service Speech transcrit et affiche le texte en temps réel. Si vous disposez d'un système audio sur votre ordinateur, vous pouvez écouter l'enregistrement pendant la transcription du texte.

1. Passez en revue la sortie, qui aurait normalement reconnu et transcrit l’audio en texte.

Dans cet exercice, vous avez essayé les services Azure AI Speech dans le terrain de jeu Speech d’Azure AI Foundry. Vous avez ensuite utilisé la transcription en temps réel pour transcrire un enregistrement audio. Vous avez pu voir la transcription du texte générée au fur et à mesure de la lecture du fichier audio.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Microsoft Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Cet exercice n’a démontré qu’une des nombreuses fonctionnalités du service de reconnaissance vocale. Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page Speech](https://azure.microsoft.com/services/cognitive-services/speech-services).
