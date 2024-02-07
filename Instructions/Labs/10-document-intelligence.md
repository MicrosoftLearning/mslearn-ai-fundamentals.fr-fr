---
lab:
  title: Extraire des données de formulaire dans le Studio Intelligence documentaire (Document Intelligence)
---

# Extraire des données de formulaire dans le Studio Intelligence documentaire (Document Intelligence)

Azure AI Intelligence documentaire est en mesure d’analyser et d’extraire des informations à partir de formulaires et de documents, puis d’identifier les noms de champs et les données. 

Comment Intelligence documentaire se base-t-il sur la reconnaissance optique de caractères (OCR) ? Bien que l’OCR puisse lire des documents imprimés ou manuscrits, elle extrait du texte dans un format non structuré qui est difficile à stocker dans une base de données ou à analyser. Intelligence documentaire donne un sens aux données non structurées en capturant la structure du texte, comme les paires clé/valeur et les informations contenues dans les tableaux. 

Dans cet exercice, vous allez examiner un modèle prédéfini dans Intelligence documentaire qui est formé pour reconnaître les données pour les reçus. 

> **REMARQUE :** Azure AI Intelligence documentaire est le nouveau nom d’Azure Form Recognizer. Il est possible que vous voyiez encore Azure Form Recognizer sur le portail Azure ou dans le Studio Intelligence documentaire.

## Créer une ressource *Intelligence documentaire*

Vous pouvez utiliser Azure AI Intelligence documentaire en créant une ressource *Intelligence documentaire* ou *Azure AI services*. Dans cet exercice, vous allez créer une ressource *Intelligence documentaire*, si vous n’en avez pas déjà.

1. Dans un autre onglet de navigateur, ouvrez [Studio Intelligence documentaire](https://formrecognizer.appliedai.azure.com/studio), puis connectez-vous avec votre compte Microsoft.
1. Sélectionnez **Paramètres** et sélectionnez l’onglet **Ressource**. Sélectionnez **Créer une ressource**.
1. Dans la boîte de dialogue Créer une ressource, entrez les éléments suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
    - **Nouveau nom de la ressource** : *Saisissez un nom unique*.
    - **Emplacement** : *Sélectionnez une région*.
    - **Niveau tarifaire** : *Gratuit FO (si disponible, sinon sélectionnez Standard SO)*.
1. Sélectionnez **Continuer**, puis **Terminer**. Attendez que la ressource soit déployée.

    >**Remarque** Si votre ressource n’est pas encore affichée, vous devrez peut-être **Actualiser** la page.

Laissez le Studio Intelligence documentaire ouvert.

## Analyser un reçu dans le Studio Intelligence documentaire

Vous êtes maintenant prêt à analyser un reçu pour la société de vente au détail fictive Northwind Traders.

1. Sélectionnez [**https://aka.ms/mslearn-receipt**](https://aka.ms/mslearn-receipt) pour télécharger un exemple de document sur votre ordinateur. Ouvrez le dossier . 
1. Sélectionnez **Form Recognizer Studio** pour revenir à la page **Prise en main du Studio Intelligence documentaire**, puis, sous Reçus, sélectionnez **Essayer**.
1. Dans la liste déroulante Prédéfini, vérifiez que **Reçus** est sélectionné.
1. Sélectionnez **Parcourir les fichiers** et accédez au dossier où vous avez enregistré l’image. Sélectionnez l’image du reçu, puis **Ouvrir**. L’image apparaît sur le côté gauche de l’écran.

    ![Reçu Northwind.](media/document-intelligence/northwind-receipt.jpg)

1. Sur la droite, sélectionnez **Exécuter l’analyse**.
1. Une fois l’analyse exécutée, les résultats sont retournés. Notez que le service a reconnu des champs de données spécifiques tels que le nom du prestataire, l’adresse, le numéro de téléphone et la date et l’heure de la transaction, ainsi que les éléments de ligne, les sous-totaux, les taxes et les montants totaux. À côté de chaque champ figure un pourcentage de probabilité que le champ soit correct.

Dans cet exercice, vous avez utilisé le Studio Intelligence documentaire pour créer une ressource Intelligence documentaire. Vous avez ensuite utilisé le service pour analyser un reçu. À partir des résultats retournés, vous avez vu comment Intelligence documentaire a pu identifier des champs spécifiques, ce qui permet de traiter plus facilement les données des documents quotidiens. Avant de fermer le Studio Intelligence documentaire, pourquoi ne pas essayer certains exemples de reçus, y compris ceux dans différentes langues ?

## Nettoyage

Si vous n’avez pas l’intention d’effectuer plus d’exercices, supprimez les ressources dont vous n’avez plus besoin. Cela évite d’accumuler des coûts inutiles.

1. Ouvrez le [portail Microsoft Azure]( https://portal.azure.com) et sélectionnez le groupe de ressources qui contient la ressource que vous avez créée.
1. Sélectionnez la ressource, puis sélectionnez **Supprimer**, puis **Oui** pour confirmer. La ressource est alors supprimée.

## En savoir plus

Cet exercice n’a montré que certaines des fonctionnalités du service AI Intelligence documentaire. Pour en savoir plus sur ce que vous pouvez faire avec ce service, consultez la page [Intelligence documentaire](https://learn.microsoft.com/azure/ai-services/document-intelligence/overview?view=doc-intel-3.1.0).
