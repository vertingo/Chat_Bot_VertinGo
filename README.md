
![Image](https://raw.githubusercontent.com/vertingo/Easy_Admin_YouTube_Newsletter_Firebase/master/web/assets/images/github/vertin_go_website.jpg)
### 🌐 Apporter votre soutien au projet :heart: pour de futures évolutions!
[![GitHub stars](https://img.shields.io/github/stars/vertingo/screenshott.svg?style=social&label=Star)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub forks](https://img.shields.io/github/forks/vertingo/screenshott.svg?style=social&label=Fork)](https://github.com/vertingo/Calcul_Graphique_Integral/fork) [![GitHub watchers](https://img.shields.io/github/watchers/vertingo/screenshott.svg?style=social&label=Watch)](https://github.com/vertingo/Calcul_Graphique_Integral) [![GitHub followers](https://img.shields.io/github/followers/vertingo.svg?style=social&label=Follow)](https://github.com/vertingo)
[![Twitter Follow](https://img.shields.io/twitter/follow/Vertin_Go.svg?style=social)](https://twitter.com/Vertin_Go)


#Français

# Déployer le Chat Bot sur Azure

Créer un compte sur Azure à l'adresse suivante: https://azure.microsoft.com/fr-fr/free/search/?WT.srch=1&wt.mc_id=AID719808_SEM_V5APtzy9&dclid=CP_s1s6Pt98CFcsT0wodbjIFaA

Egalement le gestionnaire CLI: https://docs.microsoft.com/en-us/cli/azure/install-azure-cli?view=azure-cli-latest

Ensuite créer une ressource dans le portail azure en recherchant web app bot. Renseigner tous les différents champs nécessaires dont notamment le nom du chat bot, 
le type de souscription, etc..

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot2.gif" width="700" height="450"/></a>
</p> 

Enregistrer votre chat bot dans Bot Channel Registration pour les identifiants qu'il faudra remplacer dans Web.config dans le projet en .NET!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot.gif" width="700" height="450"/></a>
</p> 

Ensuite télécharger le profil de déploiement depuis azure et dans Visual Studio Code en faisant clique droit sur le projet -> publier et importer le fichier profil dans le menu 
de publication!

Ou Télécharger le projet depuis le portail Azure et ouvrer le avec Visual Studio Code 2017

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/chat-bot.png" width="700" height="450"/></a>
</p> 


Dans un premier temps il faut renseigner les variables botFilePath et botFileSecret dans appsettings.json en les récupérant depuis le portail Azure dans Paramètres ensuite pour déployer il 
suffit simplement d'aller copier le mot de passe dans le fichier PublishSettings qui se trouve dans le dossier PostDeployScripts et ensuite clique droit sur le projet --> Publier
Cliquer sur Publier et on vous demande de taper le mot de passe! Coller le mot passe copier précédement et votre chat-bot sera publié ou plutôt mettra à jour la version précédente sur Azure!


Vous pouvez également tester votre chat-bot en local avec Bot FrameWork Emulator. Pour cela installer l'émulateur depuis le lien suivant: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1
et dans Visual Studio Code exécuter le chat-bot pour qu'il puisse être accessible depuis le localhost et ouvrer le fichier .bot!

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot5.gif" width="700" height="450"/></a>
</p> 


# 🌐 Créer un bot avec le Bot Builder SDK en Javascript et .NET et déployer sur Azure(https://portal.azure.com)

# Version en Node.JS
npm install -g windows-build-tools

npm install -g npm

npm install -g yo generator-botbuilder

yo botbuilder

npm start

Ensuite pour tester votre bot localement il faut installer Bot Emulator à l'adresse suivante: 

Une fois installé il suffit simplement d'ouvrir le fichier .bot avec l'application Bot Emulator: https://github.com/Microsoft/BotFramework-Emulator/releases/tag/v4.2.1


# Version en .NET


Installer II Express(Internet Information Express) (https://www.microsoft.com/fr-fr/download/details.aspx?id=48264)

Aller dans Visual Studio Code et rechercher dans l'onglet en ligne Enterprise Template Bot installer ce dernier!

Créer ensuite un projet Enterprise Template Bot

<p align="center">
  <a href="https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1"><img src="https://raw.githubusercontent.com/vertingo/Chat_Bot_VertinGo/master/Images/Azure-Bot3.gif" width="700" height="450"/></a>
</p> 



```
Un petit coup de pouce suivez nous sur YouTube et Facebook!
[You Tube] ==> https://www.youtube.com/channel/UC2g_-ipVjit6ZlACPWG4JvA?sub_confirmation=1 
[Facebook] ==> https://www.facebook.com/vertingo/ 
```

#English

# Basic Bot template
This bot has been created using [Microsoft Bot Framework](https://dev.botframework.com),
- Use [LUIS](https://luis.ai) to implement core AI capabilities
- Implement a multi-turn conversation using Dialogs
- Handle user interruptions for such things as Help or Cancel
- Prompt for and validate requests for information from the user

# Prerequisite to run this bot locally
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


## Run in Visual Studio
- Open the .sln file with Visual Studio.
- Press F5.
## Run in Visual Studio Code
- Open the bot project folder with Visual Studio Code.
- Bring up a terminal.
- Type 'dotnet run'.
## Testing the bot using Bot Framework Emulator
[Microsoft Bot Framework Emulator](https://aka.ms/botframework-emulator) is a desktop application that allows bot developers to test and debug
their bots on localhost or running remotely through a tunnel.
- Install the Bot Framework Emulator from [here](https://aka.ms/botframework-emulator).
### Connect to bot using Bot Framework Emulator
- Launch the Bot Framework Emulator
- File -> Open bot and navigate to the bot project folder
- Select `<your-bot-name>.bot` file

# Deploy this bot to Azure
## Publish from Visual Studio
- Open the .PublishSettings file you find in the PostDeployScripts folder
- Copy the userPWD value
- Right click on the Project and click on "Publish..."
- Paste the password you just copied and publish

## Publish using the CLI tools
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

