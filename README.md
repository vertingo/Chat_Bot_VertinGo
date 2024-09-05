
![Image](https://raw.githubusercontent.com/vertingo/Easy_Admin_YouTube_Newsletter_Firebase/master/web/assets/images/github/vertin_go_website.jpg)
### Apporter votre soutien au projet :heart: pour de futures évolutions!
[![GitHub stars](https://img.shields.io/github/stars/vertingo/screenshott.svg?style=social&label=Star)](https://github.com/vertingo/Chat_Bot_VertinGo) [![GitHub forks](https://img.shields.io/github/forks/vertingo/screenshott.svg?style=social&label=Fork)](https://github.com/vertingo/Chat_Bot_VertinGo/fork) [![GitHub watchers](https://img.shields.io/github/watchers/vertingo/screenshott.svg?style=social&label=Watch)](https://github.com/vertingo/Chat_Bot_VertinGo) [![GitHub followers](https://img.shields.io/github/followers/vertingo.svg?style=social&label=Follow)](https://github.com/vertingo)
[![Twitter Follow](https://img.shields.io/twitter/follow/Vertin_Go.svg?style=social)](https://twitter.com/Vertin_Go)
[![Facebook](https://img.shields.io/badge/Facebook-vertingo-blue?style=social&logo=facebook)](https://www.facebook.com/vertingo)
[![YouTube Subscribe](https://img.shields.io/youtube/channel/subscribers/UC2g_-ipVjit6ZlACPWG4JvA?style=social)](https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1)

# 🌐 Projet Chatbot App
![App Progress Status](https://img.shields.io/badge/Status-Finished-0520b7.svg?style=plastic)
[![Download](https://img.shields.io/badge/Download-Repo-brightgreen)](https://github.com/vertingo/vertingo-website-chatbot-app/archive/refs/heads/main.zip)

<!-- BEGIN LATEST DOWNLOAD BUTTON -->
[![Download zip](https://custom-icon-badges.demolab.com/badge/-Download-blue?style=for-the-badge&logo=download&logoColor=white "Download zip")](https://github.com/vertingo/vertingo-website-chatbot-app/archive/1.0.2.zip)
<!-- END LATEST DOWNLOAD BUTTON -->

## Créer un Chat Bot sur Azure + Téléchargement et Édition avec Visual Studio Code (Ajout des Services QnA et Luis)

### Étape 1: Créer un compte Azure
Pour commencer, inscrivez-vous sur la plateforme Azure en suivant ce lien: [Créer un compte Azure gratuit](https://azure.microsoft.com/fr-fr/free/search/?WT.srch=1&wt.mc_id=AID719808_SEM_V5APtzy9&dclid=CP_s1s6Pt98CFcsT0wodbjIFaA). Vous pourrez bénéficier d'une offre gratuite avec un crédit initial valable 30 jours.

### Étape 2: Installer Azure CLI
Pour interagir avec les services Azure via votre terminal, vous devrez installer l'Azure CLI. Suivez la documentation officielle pour l'installation sur votre système d'exploitation ici: [Installer Azure CLI](https://docs.microsoft.com/fr-fr/cli/azure/install-azure-cli?view=azure-cli-latest).

### Étape 3: Créer une application Bot sur Azure (avec ou sans QnA Maker)
Avant de commencer, si vous souhaitez intégrer le service QnA Maker à votre Bot, suivez les étapes ci-dessous. Sinon, vous pouvez passer directement à la création du Bot.

1. **Accéder à QnA Maker**  
   Rendez-vous sur [QnA Maker](https://www.qnamaker.ai/), connectez-vous avec vos identifiants Azure, puis cliquez sur "Créer une base de connaissance". Suivez les étapes pour configurer la ressource QnA Maker.

2. **Créer une ressource QnA Maker**  
   - **Nom du Service**: Donnez un nom à votre service.
   - **Abonnement**: Sélectionnez "Free Trial" par défaut.
   - **Emplacement**: Choisissez "Ouest des États-Unis".
   - **Tarification**: Sélectionnez F0 (gratuit).
   - **Groupe de Ressources**: Laissez par défaut ou créez-en un.
   - **Recherche de Prix Tiers**: Choisissez l'option "F (3 indexes)".

   Les autres options peuvent rester par défaut. Cliquez ensuite sur "Créer".

3. **Configurer la base de connaissances**  
   Une fois la ressource créée, renseignez les informations suivantes :
   - **Microsoft Azure Directory ID** (choisissez depuis la liste).
   - **Nom de l'abonnement Azure** (choisissez depuis la liste).
   - **Service QnA Azure** (sélectionnez le service précédemment créé).

4. **Ajouter des questions à la base de connaissances**  
   Donnez un nom à votre base de connaissances et ajoutez du contenu :
   - Vous pouvez ajouter un URL redirigeant vers une FAQ ou importer un fichier de questions/réponses. Exemple d'URL : [FAQ BitLocker](https://docs.microsoft.com/fr-fr/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq).

5. **Entraînez votre Bot**  
   Ajoutez un exemple de paire QnA (ex: "Question : Hi", "Réponse : Hello, ask me bitlocker questions"). Ensuite, cliquez sur "Save and Train". Vous pouvez tester votre bot via l’onglet de test avant de publier votre base de connaissances.

Vous recevrez alors les informations suivantes à garder sous la main:
```
POST /knowledgebases/<QnAKnowledgebaseId>/generateAnswer
Host:  <QnAEndpointHostName>
Authorization: EndpointKey <QnAAuthKey> 
Content-Type: application/json
{"question":"<Your question>"}
```

Les éléments à noter sont `<QnAKnowledgebaseId>`, `<QnAEndpointHostName>`, et `<QnAAuthKey>`.

### Étape 4: Créer une ressource Web App Bot sur Azure
1. **Créer un Bot**  
Sur le portail Azure, recherchez "Web App Bot" et créez une nouvelle ressource. Renseignez les champs suivants:
- **Nom du Bot**: Choisissez un nom unique pour votre Bot.
- **Abonnement**: Utilisez l'abonnement par défaut.
- **Niveau tarifaire**: Sélectionnez FO (gratuit).
- **Modèle de Bot**: Choisissez "Question and Answer" si vous utilisez QnA Maker, ou "Basic Bot" si vous souhaitez intégrer les services LUIS.
- **Plan App Service**: Utilisez le plan de service associé au Bot.
- **Stockage Azure**: Créez-en un nouveau si nécessaire.
- **ID d'Application Microsoft**: Ce champ sera automatiquement rempli.

2. **Déployer et Tester**  
Une fois le Bot déployé, vous pouvez le tester directement depuis Azure ou via des outils comme Bot Framework Emulator.

<p align="center">
<a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot2.gif" width="800" height="450"/></a>
</p>


#### [Etape spécifique pour Web App Bot de type QnA]
Une fois l'application Web App Bot créé rendez-vous dans Paramètres d'application et dans Paramètres de l'application renseigner les valeurs suivantes
récupérer depuis l'étape de publication de notre base de connaissance:
- QnAAuthKey
- QnAEndpointHostName
- QnAKnowledgebaseId

#### [Etape spécifique pour Web App Bot de type Basic Bot Luis]
- Aller sur le portail LUIS à l'adresse suivante: https://www.luis.ai 
- Connectez-vous avec vos identifiants Azure et aller dans l'onglet My Apps!
- Cliquer sur l'application créer précèdement et tout en bas à gauche Prebuilt Domains!
- Sélectionner le domaine de votre choix(Pour rester cohérant avec la suite choissisez HomeAutomation) et puis train et pour finir publier!
- Retourner dans Azure et sélectionner votre ressource Web App Bot aller dans le menu Build!
- Cliquer sur télécharger un fichier zip(Attendez un peu le temps que votre fichier soit prêt à télécharger!)
- Si vous n'avez pas Visual Studio 2017 télécharger le afin de pouvoir ouvrir le projet de votre Web App Bot
- Ensuite créer un nouveau dossier avec le nom de votre bot à l'emplacement suivant C:\Users\<users>\source\repos 
- Placer le contenu de votre fichier zip dans ce dernier dossier et faites clique droit extraire ici!
- Ensuite ouvrer Visual Studio 2017 et aller dans votre dossier créé et sélectionner le fichier à l'extension .sln
- Dans le appsettings.json renseigner les valeurs suivantes: botFilePath, botFileSecret que vous pouvez récupérer 
dans Paramètres d'application sur le portail Azure de votre Web App Bot!
- Ouvrer le fichier BasicBot.cs et dans [Supported LUIS Intents] rajouter les deux lignes suivantes:

```
public const string TurnOnIntent = "HomeAutomation_TurnOn"; // new intent
public const string TurnOffIntent = "HomeAutomation_TurnOff"; // new intent
```

Et ensuite dans la méthode OnTurnAsync au niveau du deuxième switch imbriqué rajouter les valeurs suivantes:

```
case TurnOnIntent:
    await turnContext.SendActivityAsync("TurnOn intent found, JSON response: " + luisResults?.Entities.ToString());
    break;
case TurnOffIntent:
    await turnContext.SendActivityAsync("TurnOff intent found, JSON response: " + luisResults?.Entities.ToString());
    break;
```

Ensuite éxecuter le bot en local et dans l'émulateur de bot ouvrer le fichier .bot et si demandé entrer la valeur du botFileSecret
Pour le bot entrer la valeur suivante:

Turn on the livingroom lights to 50%

Le bot devrait vous retourner les valeurs suivantes:

```
{
    "$instance": {
        "HomeAutomation_Device": [
            {
                "startIndex": 23,
                "endIndex": 29,
                "score": 0.9776345,
                "text": "lights",
                "type": "HomeAutomation.Device"
            }
        ],
        "HomeAutomation_Room": [
            {
                "startIndex": 12,
                "endIndex": 22,
                "score": 0.9079433,
                "text": "livingroom",
                "type": "HomeAutomation.Room"
            }
        ]
    },
    "HomeAutomation_Device": [
        "lights"
    ],
    "HomeAutomation_Room": [
        "livingroom"
    ]
}
```

Ci-dessous vous trouverez des illustrations et détails supplémentaires!

#### Commande Ludown Chat-Bot + Build du robot depuis l'éditeur en ligne

```
npm i -g msbot luis-apis ludown (Installation du Gestionnaire Ludown, MSBOT, luis-apis CLI Tools)

ludown parse toluis --in dialogs/greeting/resources/main.lu -o cognitiveModels/ --out basicBot.luis -n 'basic-bot-LUIS' -d 'Basic bot Bot Builder V4 sample.' --verbose (Génére le model basicBot.luis)

luis import application --in cognitiveModels/basicBot.luis --appName BasicBot

msbot list --secret [val_botFileSecret] (Récuperer botFileSecret dans appsettings.json ou si non renseigné dans appsettings.json aller sur le portail Azure, et dans le projet correspondant à votre 
Chat-Bot et Paramètres d'App Service -> paramètres d'application!)

luis train version --appId [val_app_id] --versionId [val_version] [--wait] (Récupérer [val_app_id] et [val_version] sur le portail LUIS(http://luis.ai/))
```

<p align="center">
            <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/youtube2.png" width="400" height="150"/></a>
            <a href="https://www.facebook.com/vertingo/"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="150"/></a>
</p>


## Créer un Bot avec le Bot Builder SDK de Visual Studio Code 2017 en Javascript et .NET et déployer sur Azure(https://portal.azure.com)

#### Créer un Chat Bot depuis une invite de commande en version en Node.JS

```
npm install -g windows-build-tools

npm install -g npm

npm install -g yo generator-botbuilder

yo botbuilder

npm start

Ensuite pour tester votre bot localement il faut installer Bot Emulator à  l'adresse suivante: 

Une fois installé il suffit simplement d'ouvrir le fichier .bot avec l'application Bot Emulator: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1
```

#### Créer un Chat Bot depuis Visual Studio 2017 en version en .NET

Installer II Express(Internet Information Express) (https://www.microsoft.com/fr-fr/download/details.aspx?id=48264)

Aller dans Visual Studio Code et rechercher dans l'onglet en ligne Enterprise Template Bot, installer ce dernier!

Créer ensuite un projet Enterprise Template Bot

#### Bot Channel Enregistrement
Enregistrer votre Chat Bot dans la Bot Channel Registration pour récupérer les identifiants qu'il faudra remplacer dans Web.config dans le projet en .NET!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot.gif" width="800" height="450"/></a>
</p> 

Ensuite télécharger le profil de déploiement depuis azure et dans Visual Studio Code en faisant clique droit sur le projet -> publier et importer le fichier profil dans le menu de publication!

Ou Télécharger le projet depuis le portail Azure et ouvrer le avec Visual Studio Code 2017(Etape recommandé et déjà expliqué plus haut!)

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/chat-bot.png" width="900" height="250"/></a>
</p> 

Dans un premier temps il faut renseigner les variables botFilePath et botFileSecret dans appsettings.json en les récupérant depuis le portail Azure dans Paramètres ensuite pour déployer il 
suffit simplement d'aller copier le mot de passe dans le fichier PublishSettings qui se trouve dans le dossier PostDeployScripts et ensuite clique droit sur le projet --> Publier
Cliquer sur Publier et on vous demande de taper le mot de passe! Coller le mot passe copier précédement et votre chat-bot sera publié ou plutôt mettra à  jour la version précédente sur Azure!

Vous pouvez également tester votre chat-bot en local avec Bot FrameWork Emulator. Pour cela installer l'émulateur depuis le lien suivant: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1
et dans Visual Studio Code exécuter le chat-bot pour qu'il puisse être accessible depuis le localhost et ouvrer le fichier .bot!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot5.gif" width="800" height="450"/></a>
</p> 

<p align="center">
            <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/youtube2.png" width="400" height="150"/></a>
            <a href="https://www.facebook.com/vertingo/"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="150"/></a>
</p>

## Create Basic Bot template with LUIS(English version)
This bot has been created using [Microsoft Bot Framework](https://dev.botframework.com),
- Use [LUIS](https://luis.ai) to implement core AI capabilities
- Implement a multi-turn conversation using Dialogs
- Handle user interruptions for such things as Help or Cancel
- Prompt for and validate requests for information from the user

#### Prerequisite to run this bot locally
- Download the bot code from the Build blade in the Azure Portal
- Update the `appsettings.json` file in the root of the bot project with the botFilePath and botFileSecret 
- You can find the botFilePath and botFileSecret in the Azure App Service application settings.

Your appsettings.json file should look like this
```bash
{
    "botFilePath": "<copy value from App settings>",
    "botFileSecret": "<copy value from App settings>"
}
```

#### Run in Visual Studio
- Open the .sln file with Visual Studio.
- Press F5.
#### Run in Visual Studio Code
- Open the bot project folder with Visual Studio Code.
- Bring up a terminal.
- Type 'dotnet run'.
#### Testing the bot using Bot Framework Emulator
[Microsoft Bot Framework Emulator](https://aka.ms/botframework-emulator) is a desktop application that allows bot developers to test and debug
their bots on localhost or running remotely through a tunnel.
- Install the Bot Framework Emulator from [here](https://aka.ms/botframework-emulator).
#### Connect to bot using Bot Framework Emulator
- Launch the Bot Framework Emulator
- File -> Open bot and navigate to the bot project folder
- Select `<your-bot-name>.bot` file

## Deploy this bot to Azure
#### Publish from Visual Studio
- Open the .PublishSettings file you find in the PostDeployScripts folder
- Copy the userPWD value
- Right click on the Project and click on "Publish..."
- Paste the password you just copied and publish

#### Publish using the CLI tools
You can use the [MSBot](https://github.com/microsoft/botbuilder-tools) Bot Builder CLI tool to clone and configure any services this sample depends on. 
To install all Bot Builder tools - 

Ensure you have [Node.js](https://nodejs.org/) version 8.5 or higher

```bash
npm i -g msbot chatdown ludown qnamaker luis-apis botdispatch luisgen
```
To clone this bot, run
```
msbot clone services -f deploymentScripts/msbotClone -n <BOT-NAME> -l <Azure-location> --subscriptionId <Azure-subscription-id>
```
# Further reading
- [Bot Framework Documentation](https://docs.botframework.com)
- [Bot basics](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-basics?view=azure-bot-service-4.0)
- [Activity processing](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-concept-activity-processing?view=azure-bot-service-4.0)
- [LUIS](https://luis.ai)
- [Prompt Types](https://docs.microsoft.com/en-us/azure/bot-service/bot-builder-prompts?view=azure-bot-service-4.0&tabs=javascript)
- [Azure Bot Service Introduction](https://docs.microsoft.com/en-us/azure/bot-service/bot-service-overview-introduction?view=azure-bot-service-4.0)
- [Channels and Bot Connector Service](https://docs.microsoft.com/en-us/azure/bot-service/bot-concepts?view=azure-bot-service-4.0)
- [QnA Maker](https://qnamaker.ai)

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/easy-admin-youtube-newsletter-firebase/master/web/assets/images/reseaux-sociaux/youtube2.png" width="400" height="250"/></a>
  <a href="https://www.facebook.com/vertingo/"><img src="https://raw.githubusercontent.com/vertingo/easy-admin-youtube-newsletter-firebase/master/web/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="250"/></a>
</p>
