---
lab:
  title: "Explorer Azure\_AI Services"
---

# Explorer Azure AI Services

Azure AI services aide les utilisateurs à créer des applications avec des API et modèles prêts à l’emploi, prédéfinis et personnalisables. Dans cet exercice, vous allez examiner l’un des services, Azure AI Content Safety, dans Content Safety Studio.

Le Studio de Sécurité du Contenu vous permet d’explorer la façon dont le contenu texte et image peut être modéré. Vous pouvez exécuter des tests sur des exemples de texte ou d’images et obtenir un score de gravité allant de sécurisé à élevé pour chaque catégorie. Dans cet exercice du lab, vous allez créer une ressource à service unique dans Content Safety Studio et tester ses fonctionnalités. 

> **Remarque** L’objectif de cet exercice est d’avoir une idée générale de la façon dont les services Azure AI services sont provisionnés et utilisés. Content Safety est utilisé à titre d’exemple, vous n’êtes pas censé devenir un expert en sécurité du contenu après cet exercice.

## Naviguer dans Content Safety Studio 

![Capture d’écran de la page d’accueil de Content Safety Studio.](./media/content-safety/content-safety-getting-started.png)

1. Ouvrez [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). Si vous n’êtes pas connecté, vous devez le faire. Sélectionnez **Se connecter** en haut à droite de l’écran. Utilisez l’adresse e-mail et le mot de passe associés à votre abonnement Azure pour vous connecter. 

1. Content Safety Studio est configuré comme de nombreux autres studios des Azure AI services. Dans le menu en haut de l’écran, cliquez sur l’icône à gauche d’*Azure AI*. Vous verrez une liste déroulante d’autres studios conçus pour le développement avec Azure AI services. Vous pouvez cliquer à nouveau sur l’icône pour masquer la liste.

![Capture d’écran du menu de Content Safety Studio avec une sélection bascule ouverte pour passer à d’autres studios.](./media/content-safety/studio-toggle-icon.png)  

## Associer une ressource au studio 

Avant d’utiliser le studio, vous devez associer une ressource Azure AI services au studio. En fonction du studio, vous constaterez qu’il vous faut une ressource de service unique spécifique ou que vous pouvez utiliser une ressource multiservice générale. Dans le cas de Content Safety Studio, vous pouvez utiliser le service en créant une ressource *Sécurité du contenu* de service unique ou une ressource multiservice générale *Azure AI services*. Dans les étapes ci-dessous, nous allons créer une ressource Content Safety de service unique. 

1. En haut à droite de l’écran, cliquez sur l’icône **Paramètres**. 

![Capture d’écran de l’icône des paramètres en haut à droite de l’écran, à côté des icônes de cloche, du point d’interrogation et du sourire.](./media/content-safety/settings-toggle.png)

2. Dans la page **Paramètres**, vous verrez un onglet *Répertoire* et un onglet *Ressource*. Sous l’onglet *Ressource*, sélectionnez **Créer une ressource**. Cela vous amène à la page pour créer une ressource dans le Portail Azure.

> **Remarque** L’onglet *Répertoire* permet aux utilisateurs de sélectionner différents répertoires à partir desquels créer des ressources. Vous n’avez pas besoin de modifier ses paramètres, sauf si vous souhaitez utiliser un autre répertoire. 

![Capture d’écran montrant où sélectionner « Créer une ressource » dans la page des paramètres de Content Safety Studio.](./media/content-safety/create-new-resource-from-studio.png)

3. Dans la page *Créer une sécurité du contenu* dans le [Portail Azure](https://portal.azure.com?azure-portal=true), vous devez configurer plusieurs détails pour créer votre ressource. Configurez-la avec les paramètres suivants :
    - **Abonnement** : *votre abonnement Azure*.
    - **Groupe de ressources** : *sélectionnez ou créez un groupe de ressources portant un nom unique*.
    - **Région** : *choisissez une région disponible. Si vous êtes dans l’est des États-Unis, utilisez « USA Est 2 »*.
    - **Nom** : *entrez un nom unique.*
    - **Niveau tarifaire** : F0 gratuit

4. Sélectionnez **Vérifier + créer**, puis passez en revue la configuration. Sélectionnez ensuite **Créer**. L’écran indique quand le déploiement est terminé. 

*Félicitations ! Vous venez de créer ou d’approvisionner une ressource Azure AI services. Celle que vous avez approvisionnée dans ce cas précis est une ressource de service Content Safety de service unique.*

5. Une fois le déploiement terminé, ouvrez un nouvel onglet et revenez à [Content Safety Studio](https://contentsafety.cognitive.azure.com?azure-portal=true). 

6. Sélectionnez à nouveau l’icône **Paramètres** en haut à droite de l’écran. Cette fois, vous devriez voir que votre ressource nouvellement créée a été ajoutée à la liste.  

7. Dans la page Paramètres de Content Safety Studio, sélectionnez la ressource eu service Azure AI que vous venez de créer, puis cliquez sur **Utiliser la ressource** en bas de l’écran. Vous serez redirigé vers la page d’accueil du studio. Vous pouvez maintenant commencer à utiliser le studio avec votre ressource nouvellement créée.

## Essayer la modération de texte dans Content Safety Studio

1. Dans la page d’accueil Content Safety Studio, sous *Exécuter des tests de modération*, accédez à la zone **Modérer le contenu de texte**, puis cliquez sur **Essayer**.
1. Sous Exécuter un test simple, cliquez sur **Contenu sécurisé**. Le texte est affiché dans la zone ci-dessous. 
1. Cliquez sur **Run test**. L’exécution d’un test appelle le modèle Deep Learning de Content Safety Service. Le modèle Deep Learning a déjà été entraîné pour reconnaître le contenu non sécurisé.
1. Dans le panneau *Résultats*, examinez les résultats. Il y a quatre niveaux de gravité allant de sécurisé à élevé, et quatre types de contenu nuisible. Le service AI Sécurité du Contenu considère-t-il cet exemple comme acceptable ou non ? Il est important de souligner que les résultats se situent dans un intervalle de confiance. Un modèle bien entraîné, comme l’un des modèles prêts à l’emploi d’Azure AI, peut retourner des résultats qui ont une forte probabilité de correspondre à ce qu’un humain qualifierait pour le résultat. Chaque fois que vous exécutez un test, vous appelez à nouveau le modèle. 
1. Essayez maintenant un autre échantillon. Sélectionnez le texte sous Contenu violent avec une faute d’orthographe. Vérifiez que le contenu s’affiche dans la zone ci-dessous.
1. Cliquez sur **Exécuter le test** et examinez à nouveau les résultats dans le panneau Résultats. 

Vous pouvez exécuter des tests sur tous les exemples fournis, puis examiner les résultats.

## Examiner les clés et le point de terminaison

Ces fonctionnalités que vous avez testées peuvent être programmées dans toutes sortes d’applications. Les clés et le point de terminaison utilisés pour le développement d’applications se trouvent tous dans Content Safety Studio et le Portail Azure. 

1. Dans Content Safety Studio, revenez à la page **Paramètres**, avec l’onglet *Ressources* sélectionné. Recherchez la ressource que vous avez utilisée. Faites défiler l’écran pour voir le point de terminaison et la clé de votre ressource. 
1. Dans le Portail Azure, vous verrez qu’il s’agit du *même* point de terminaison et de *différentes* clés que dans votre ressource. Pour vérifier cela, accédez au [Portail Azure](https://portal.azure.com?auzre-portal=true). Recherchez *Sécurité du contenu* dans la barre de recherche supérieure. Recherchez votre ressource et cliquez dessus. Dans le menu de gauche, en dessous de *Gestion des ressources*, cherchez *Clés et points de terminaison*. Sélectionnez **Clés et points de terminaison** pour afficher le point de terminaison et les clés de votre ressource. 

Une fois que vous avez terminé, vous pouvez supprimer la ressource Sécurité du contenu du Portail Azure. La suppression de la ressource est un moyen de réduire les coûts qui s’accumulent lorsque la ressource existe déjà dans l’abonnement. Pour cela, accédez à la page **Vue d’ensemble** de votre ressource Sécurité du contenu. En haut de l’écran, sélectionnez **Supprimer**.

