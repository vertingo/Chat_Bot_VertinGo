
![Image](https://raw.githubusercontent.com/vertingo/Easy_Admin_YouTube_Newsletter_Firebase/master/web/assets/images/github/vertin_go_website.jpg)
### Apporter votre soutien au projet :heart: pour de futures évolutions!
[![GitHub stars](https://img.shields.io/github/stars/vertingo/screenshott.svg?style=social&label=Star)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub forks](https://img.shields.io/github/forks/vertingo/screenshott.svg?style=social&label=Fork)](https://github.com/vertingo/Calcul_Graphique_Integral/fork) [![GitHub watchers](https://img.shields.io/github/watchers/vertingo/screenshott.svg?style=social&label=Watch)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub followers](https://img.shields.io/github/followers/vertingo.svg?style=social&label=Follow)](https://github.com/vertingo)
[![Twitter Follow](https://img.shields.io/twitter/follow/Vertin_Go.svg?style=social)](https://twitter.com/Vertin_Go)


## Créer le Chat Bot sur Azure + Téléchargement du projet pour l'éditer depuis Visual Studio Code en local + Ajout des Services QnA et Luis(Version Française)

Créer un compte sur Azure à l'adresse suivante: (https://azure.microsoft.com/fr-fr/free/search/?WT.srch=1&wt.mc_id=AID719808_SEM_V5APtzy9&dclid=CP_s1s6Pt98CFcsT0wodbjIFaA)

Egalement le gestionnaire CLI: (https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

Petite précision avant de créer l'application App Bot si vous souhaitez pour intégrer les services QnA sinon vous pouvez passer à la section suivante!

Aller sur https://www.qnamaker.ai/ (Connecter-vous avec vos identifiants Azure et cliquer sur créer une base de connaissance!) et suiver les différentes 
étapes à commencer par créer une ressource de type QnA Maker!

#### [Etape 1]
Pour la ressource QnA Maker indiquer les valeurs suivantes:
- Le nom du Service
- L'abonnement Free Trial par défaut
- L'emplacement sélectionner Ouest des États-Unis(Précisez avant le type de tarification sinon impossible de sélectionner une valeur pour la tarification)
- Le type de tarification (F0 gratuit)
- Resource groupe (Laisser par défaut)
- Recherche prix tiers(F (3 indexes))

Le reste peut rester par défaut et vous pouvez créer la ressource QnA Maker!

#### [Etape 2]
Une fois que vous avez créer la ressource QnA Maker renseigner les 3 valeurs suivantes:
- Microsoft Azure Directory ID(Sélectionner dans la liste!)
- Azure subscription name(Sélectionner dans la liste!)
- Azure QnA service(Sélectionner dans la liste!)

#### [Etape 3]
Donner un nom à votre base de connaissance!

#### [Etape 4]
Ajouter des valeurs à votre base de connaissance en ajoutant par exemple un url redirigeant vers un Faq(Frenquency ask question) d'un site!
Exemple: https://docs.microsoft.com/fr-fr/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq

Sinon ajouter un fichier de Questions Réponses!

#### [Etape 5]
Cliquer sur Create your KB

Une fois créé cliquer sur: 
+ Add QnA pair (Ajouter en question: Hi et en réponse: Hello. Ask me bitlocker questions)
Ensuite cliquer sur Save And Train! Vous pouvez tester votre bot en tapant hi dans test!
Refermer l'onglet test en cliquant sur test puis publier votre base de connaissance!

Vous obtenez les informations suivantes:
```
POST /knowledgebases/<QnAKnowledgebaseId>/generateAnswer
Host:  <QnAEndpointHostName>
Authorization: EndpointKey <QnAAuthKey> 
Content-Type: application/json
{"question":"<Your question>"}
```

Ce qui nous intéresse ce sont les 3 premières lignes POST, Host, Authorization!
Plus précisement:
```
<QnAKnowledgebaseId>, <QnAEndpointHostName>, <QnAAuthKey> 
```
Gardez ces valeurs de côté et rendez-vous dans Azure pour créer une ressource de type Web App Bot!

#### [Création de la ressource Web App Bot]
Créer une ressource dans le portail azure en recherchant Web App Bot. 
Renseigner tous les différents champs nécessaires dont notamment: 
- Le nom du Chat Bot
- Le type de souscription (par défaut celui que vous possédez)
- Le niveau tarifaire FO pour gratuit
- Le modèle de bot (Choissisez le modèle Question and Answer en allant sur le kit de développement V3 pour un robot de type Qna sinon choissisez Basic Bot pour intégrer les services Luis)
- Le plan app service (Choissisez le plan QnA créer précèdement pour un robot de type Qna sinon celui par défaut App)
- Le stockage azure créer un nouveau ou choissisez en un si vous en avez déjà un!
- L'id d'application Microsoft (Automatique)

Une illustration ci-dessous sans prendre en compte QnA!

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

<p align="center">
            <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/youtube2.png" width="400" height="250"/></a>
            <a href="https://www.facebook.com/vertingo/"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="250"/></a>
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

#### Bot Channel Registration
Enregistrer votre Chat Bot dans la Bot Channel Registration pour récupérer les identifiants qu'il faudra remplacer dans Web.config dans le projet en .NET!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot.gif" width="800" height="450"/></a>
</p> 

Ensuite télécharger le profil de déploiement depuis azure et dans Visual Studio Code en faisant clique droit sur le projet -> publier et importer le fichier profil dans le menu de publication!

Ou Télécharger le projet depuis le portail Azure et ouvrer le avec Visual Studio Code 2017(Etape recommendé et déjà expliqué plus haut!)

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/chat-bot.png" width="800" height="550"/></a>
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
            <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/youtube2.png" width="400" height="250"/></a>
            <a href="https://www.facebook.com/vertingo/"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="250"/></a>
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

