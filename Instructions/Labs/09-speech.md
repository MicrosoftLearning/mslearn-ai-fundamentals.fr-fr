---
lab:
  title: "Explorer Speech dans le portail Azure\_AI\_Foundry"
---

# Explorer Speech dans le portail Azure AI Foundry

Le service **Azure AI Speech** transcrit la parole en texte et le texte en parole audible. Vous pouvez utiliser AI Speech pour créer une application capable de transcrire des notes de réunion ou de générer du texte à partir de l'enregistrement d'entretiens.

Dans cet exercice, vous allez utiliser Azure AI Speech dans le portail Azure AI Foundry, la plateforme de Microsoft pour la création d’applications intelligentes, afin de transcrire l’audio à l’aide des expériences de test intégrées. 

## Créer un projet dans le portail Azure AI Foundry

1. Dans un navigateur web, ouvrez le [portail Azure AI Foundry](https://ai.azure.com) à l’adresse `https://ai.azure.com` et connectez-vous en utilisant vos informations d’identification Azure. Fermez les conseils ou les volets de démarrage rapide ouverts lors de votre première connexion. 

1. Dans le navigateur, accédez à `https://ai.azure.com/managementCenter/allResources` et sélectionnez **Créer**. Choisissez ensuite l’option permettant de créer une *ressource Azure AI Foundry*.

1. Dans l’Assistant *Créer un projet*, entrez un nom valide pour votre projet.

1. Développez les *options avancées* pour définir les paramètres suivants de votre projet :
    - **Abonnement** : votre abonnement Azure.
    - **Groupe de ressources** : créez ou sélectionnez un groupe de ressources.
    - **Région** : sélectionnez l’un des emplacements suivants.
        * USA Est
        * France Centre
        * Centre de la Corée
        * Europe Ouest
        * USA Ouest

    Attendez que votre projet et votre hub soient créés.

1. Lorsque le projet est créé, vous accédez à une page *Vue d’ensemble* des détails du projet.
 
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
