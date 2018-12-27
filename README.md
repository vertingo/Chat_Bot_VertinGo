
![Image](https://raw.githubusercontent.com/vertingo/Easy_Admin_YouTube_Newsletter_Firebase/master/web/assets/images/github/vertin_go_website.jpg)
### Apporter votre soutien au projet :heart: pour de futures �volutions!
[![GitHub stars](https://img.shields.io/github/stars/vertingo/screenshott.svg?style=social&label=Star)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub forks](https://img.shields.io/github/forks/vertingo/screenshott.svg?style=social&label=Fork)](https://github.com/vertingo/Calcul_Graphique_Integral/fork) [![GitHub watchers](https://img.shields.io/github/watchers/vertingo/screenshott.svg?style=social&label=Watch)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub followers](https://img.shields.io/github/followers/vertingo.svg?style=social&label=Follow)](https://github.com/vertingo)
[![Twitter Follow](https://img.shields.io/twitter/follow/Vertin_Go.svg?style=social)](https://twitter.com/Vertin_Go)


## Cr�er le Chat Bot sur Azure + T�l�chargement du projet pour l'�diter depuis Visual Studio Code en local + Ajout des Services QnA et Luis(Version Fran�aise)

Cr�er un compte sur Azure �l'adresse suivante: (https://azure.microsoft.com/fr-fr/free/search/?WT.srch=1&wt.mc_id=AID719808_SEM_V5APtzy9&dclid=CP_s1s6Pt98CFcsT0wodbjIFaA)

Egalement le gestionnaire CLI: (https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest)

Petite pr�cision avant de cr�er l'application App Bot si vous souhaitez pour int�grer les services QnA sinon vous pouvez passer � la section suivante!

Aller sur https://www.qnamaker.ai/ (Connecter-vous avec vos identifiants Azure et cliquer sur cr�er une base de connaissance!) et suiver les diff�rentes 
�tapes � commencer par cr�er une ressource de type QnA Maker!

#### [Etape 1]
Pour la ressource QnA Maker indiquer les valeurs suivantes:
- Le nom du Service
- L'abonnement Free Trial par d�faut
- L'emplacement s�lectionner Ouest des �tats-Unis(Pr�cisez avant le type de tarification sinon impossible de s�lectionner une valeur pour la tarification)
- Le type de tarification (F0 gratuit)
- Resource groupe (Laisser par d�faut)
- Recherche prix tiers(F (3 indexes))

Le reste peut rester par d�faut et vous pouvez cr�er la ressource QnA Maker!

#### [Etape 2]
Une fois que vous avez cr�er la ressource QnA Maker renseigner les 3 valeurs suivantes:
- Microsoft Azure Directory ID(S�lectionner dans la liste!)
- Azure subscription name(S�lectionner dans la liste!)
- Azure QnA service(S�lectionner dans la liste!)

#### [Etape 3]
Donner un nom � votre base de connaissance!

#### [Etape 4]
Ajouter des valeurs � votre base de connaissance en ajoutant par exemple un url redirigeant vers un Faq(Frenquency ask question) d'un site!
Exemple: https://docs.microsoft.com/fr-fr/windows/security/information-protection/bitlocker/bitlocker-overview-and-requirements-faq

Sinon ajouter un fichier de Questions R�ponses!

#### [Etape 5]
Cliquer sur Create your KB

Une fois cr�� cliquer sur: 
+ Add QnA pair (Ajouter en question: Hi et en r�ponse: Hello. Ask me bitlocker questions)
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

Ce qui nous int�resse ce sont les 3 premi�res lignes POST, Host, Authorization!
Plus pr�cisement:
```
<QnAKnowledgebaseId>, <QnAEndpointHostName>, <QnAAuthKey> 
```
Gardez ces valeurs de c�t� et rendez-vous dans Azure pour cr�er une ressource de type Web App Bot!

#### [Cr�ation de la ressource Web App Bot]
Cr�er une ressource dans le portail azure en recherchant Web App Bot. 
Renseigner tous les diff�rents champs n�cessaires dont notamment: 
- Le nom du Chat Bot
- Le type de souscription (par d�faut celui que vous poss�dez)
- Le niveau tarifaire FO pour gratuit
- Le mod�le de bot (Choissisez le mod�le Question and Answer en allant sur le kit de d�veloppement V3 pour un robot de type Qna sinon choissisez Basic Bot pour int�grer les services Luis)
- Le plan app service (Choissisez le plan QnA cr�er pr�c�dement pour un robot de type Qna sinon celui par d�faut App)
- Le stockage azure cr�er un nouveau ou choissisez en un si vous en avez d�j� un!
- L'id d'application Microsoft (Automatique)

Une illustration ci-dessous sans prendre en compte QnA!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot2.gif" width="800" height="450"/></a>
</p> 


#### [Etape sp�cifique pour Web App Bot de type QnA]
Une fois l'application Web App Bot cr�� rendez-vous dans Param�tres d'application et dans Param�tres de l'application renseigner les valeurs suivantes
r�cup�rer depuis l'�tape de publication de notre base de connaissance:
- QnAAuthKey
- QnAEndpointHostName
- QnAKnowledgebaseId

#### [Etape sp�cifique pour Web App Bot de type Basic Bot Luis]
- Aller sur le portail LUIS � l'adresse suivante: https://www.luis.ai 
- Connectez-vous avec vos identifiants Azure et aller dans l'onglet My Apps!
- Cliquer sur l'application cr�er pr�c�dement et tout en bas � gauche Prebuilt Domains!
- S�lectionner le domaine de votre choix(Pour rester coh�rant avec la suite choissisez HomeAutomation) et puis train et pour finir publier!
- Retourner dans Azure et s�lectionner votre ressource Web App Bot aller dans le menu Build!
- Cliquer sur t�l�charger un fichier zip(Attendez un peu le temps que votre fichier soit pr�t � t�l�charger!)
- Si vous n'avez pas Visual Studio 2017 t�l�charger le afin de pouvoir ouvrir le projet de votre Web App Bot
- Ensuite cr�er un nouveau dossier avec le nom de votre bot � l'emplacement suivant C:\Users\<users>\source\repos 
- Placer le contenu de votre fichier zip dans ce dernier dossier et faites clique droit extraire ici!
- Ensuite ouvrer Visual Studio 2017 et aller dans votre dossier cr�� et s�lectionner le fichier � l'extension .sln
- Dans le appsettings.json renseigner les valeurs suivantes: botFilePath, botFileSecret que vous pouvez r�cup�rer 
dans Param�tres d'application sur le portail Azure de votre Web App Bot!
- Ouvrer le fichier BasicBot.cs et dans [Supported LUIS Intents] rajouter les deux lignes suivantes:

```
public const string TurnOnIntent = "HomeAutomation_TurnOn"; // new intent
public const string TurnOffIntent = "HomeAutomation_TurnOff"; // new intent
```

Et ensuite dans la m�thode OnTurnAsync au niveau du deuxi�me switch imbriqu� rajouter les valeurs suivantes:

```
case TurnOnIntent:
    await turnContext.SendActivityAsync("TurnOn intent found, JSON response: " + luisResults?.Entities.ToString());
    break;
case TurnOffIntent:
    await turnContext.SendActivityAsync("TurnOff intent found, JSON response: " + luisResults?.Entities.ToString());
    break;
```

Ensuite �xecuter le bot en local et dans l'�mulateur de bot ouvrer le fichier .bot et si demand� entrer la valeur du botFileSecret
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
Ci-dessous vous trouverez des illustrations et d�tails suppl�mentaires!

<p align="center">
            <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/youtube2.png" width="400" height="250"/></a>
            <a href="https://www.facebook.com/vertingo/"><img src="https://platform-media.herokuapp.com/assets/images/reseaux-sociaux/rejoins_nous.png" width="400" height="250"/></a>
</p>


## Cr�er un Bot avec le Bot Builder SDK de Visual Studio Code 2017 en Javascript et .NET et d�ployer sur Azure(https://portal.azure.com)

#### Cr�er un Chat Bot depuis une invite de commande en version en Node.JS

```
npm install -g windows-build-tools

npm install -g npm

npm install -g yo generator-botbuilder

yo botbuilder

npm start

Ensuite pour tester votre bot localement il faut installer Bot Emulator � l'adresse suivante: 

Une fois install� il suffit simplement d'ouvrir le fichier .bot avec l'application Bot Emulator: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1
```

#### Cr�er un Chat Bot depuis Visual Studio 2017 en version en .NET

Installer II Express(Internet Information Express) (https://www.microsoft.com/fr-fr/download/details.aspx?id=48264)

Aller dans Visual Studio Code et rechercher dans l'onglet en ligne Enterprise Template Bot, installer ce dernier!

Cr�er ensuite un projet Enterprise Template Bot

#### Bot Channel Registration
Enregistrer votre Chat Bot dans la Bot Channel Registration pour r�cup�rer les identifiants qu'il faudra remplacer dans Web.config dans le projet en .NET!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot.gif" width="800" height="450"/></a>
</p> 

Ensuite t�l�charger le profil de d�ploiement depuis azure et dans Visual Studio Code en faisant clique droit sur le projet -> publier et importer le fichier profil dans le menu de publication!

Ou T�l�charger le projet depuis le portail Azure et ouvrer le avec Visual Studio Code 2017(Etape recommend� et d�j� expliqu� plus haut!)

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/chat-bot.png" width="800" height="550"/></a>
</p> 

Dans un premier temps il faut renseigner les variables botFilePath et botFileSecret dans appsettings.json en les r�cup�rant depuis le portail Azure dans Param�tres ensuite pour d�ployer il 
suffit simplement d'aller copier le mot de passe dans le fichier PublishSettings qui se trouve dans le dossier PostDeployScripts et ensuite clique droit sur le projet --> Publier
Cliquer sur Publier et on vous demande de taper le mot de passe! Coller le mot passe copier pr�c�dement et votre chat-bot sera publi� ou plut�t mettra � jour la version pr�c�dente sur Azure!

Vous pouvez �galement tester votre chat-bot en local avec Bot FrameWork Emulator. Pour cela installer l'�mulateur depuis le lien suivant: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1
et dans Visual Studio Code ex�cuter le chat-bot pour qu'il puisse �tre accessible depuis le localhost et ouvrer le fichier .bot!

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

