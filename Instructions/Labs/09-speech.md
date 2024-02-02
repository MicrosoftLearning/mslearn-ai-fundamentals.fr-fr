---
lab:
  title: Explorer Speech Studio
---

# Explorer Speech Studio

Le service **Azure AI Speech** transcrit la parole en texte et le texte en parole audible. Vous pouvez utiliser AI Speech pour créer une application capable de transcrire des notes de réunion ou de générer du texte à partir de l'enregistrement d'entretiens.

Dans cet exercice, vous allez tester les fonctionnalités d'Azure AI Speech à l’aide d'Azure AI Speech Studio. 

## Créer une ressource *Azure AI Speech*

Vous pouvez utiliser le service Speech en créant une ressource **Speech** ou **Azure AI services**.

Dans cet exercice, vous allez créer une ressource AI Speech, à moins que vous ne disposiez déjà d'une ressource que vous pouvez utiliser.

1. Sous un autre onglet de navigateur, ouvrez [Azure AI Speech Studio](https://speech.microsoft.com/) en vous connectant avec votre compte Microsoft.

1. Sélectionnez **Paramètres**, puis **Créer une ressource.** Configurez-la avec les paramètres suivants :
    - **Nom de la nouvelle ressource** : *Saisissez un nom unique*.
    - **Abonnement** : *votre abonnement Azure*.
    - **Région** : *Sélectionnez une [région prise en charge](https://learn.microsoft.com/azure/ai-services/speech-service/regions)*.
    - **Niveau tarifaire** : *FO gratuit (si disponible, sinon sélectionnez Standard S0).*
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
1. Sélectionnez **Créer une ressource**. Attendez que la ressource ait été créée, puis sélectionnez **Utiliser la ressource**. La page Démarrage de Speech s’affiche.

## Explorer la reconnaissance vocale dans Speech Studio

1. Sélectionnez [**https://aka.ms/mslearn-speech-files**](https://aka.ms/mslearn-speech-files) pour télécharger **speech.zip**. Ouvrez le dossier . 

1. Dans la page Prise en main de la reconnaissance vocale, sous *Speech*, recherchez *Reconnaissance vocale en temps réel*. Sélectionnez **Essayer la reconnaissance vocale en temps réel**.

    ![Bien démarrer avec Speech](media/recognize-synthesize-speech/try-out-speech-to-text.png)

1. Sous *Choisir des fichiers audio*, sélectionnez **Rechercher des fichiers** et accédez au dossier dans lequel vous avez enregistré le fichier. Sélectionnez **WhatAICanDo.m4a**, puis **Ouvrir**.

    ![Parcourir les fichiers](media/recognize-synthesize-speech/browse-files-speech.png)

1. Le service Speech transcrit et affiche le texte en temps réel. Si vous disposez d'un système audio sur votre ordinateur, vous pouvez écouter l'enregistrement pendant la transcription du texte.
1. Passez en revue la sortie, qui aurait normalement reconnu et transcrit l’audio en texte.

    > **Remarque** Si vous recevez un message d’erreur, attendez quelques minutes avant de réessayer. Il faut un peu de temps pour que la ressource Speech soit disponible pour une première utilisation.

Dans cet exercice, vous avez créé une ressource AI Speech dans Speech Studio. Vous avez ensuite utilisé la reconnaissance vocale en temps réel pour transcrire un enregistrement audio. Vous avez pu voir la transcription du texte générée au fur et à mesure de la lecture du fichier audio.

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [Portail Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource et choisissez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Cet exercice n’a démontré que quelques fonctionnalités du service Speech. Pour en savoir plus sur ce que ce service est capable de faire, consultez la [page Speech](https://azure.microsoft.com/services/cognitive-services/speech-services).
