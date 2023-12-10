# Dolfje een MNOT Weerwolf bot

Deze bot is geschreven om het weerwolven spel op de MNOT weerwolven slack te begeleiden.
Wij spelen het spel met een (of meerdere) verteller(s) die het spel leiden.
Speel een keer mee op https://mnot.nl/weerwolvenslack !

## Let op!

Voor nieuwe features wordt regelmatig het database schema bijgewerkt, controleer in wwmnot.sql of je alle tabellen en kolommen daarin hebt.

## Installatie handleiding

Dolfje is als klein project begonnen en beetje uit de hand gelopen.
Het ondersteund meerdere spellen, maar maar 1 Slack te tegelijkertijd, als je dus ook van Dolfje gebruik wilt maken zal je het zelf moeten hosten.
Hieronder een beknopt stappen plan.

### Extern domein
Je server moet bereikbaar zijn voor Slack om aan te roepen. Hier voor kun je een echt domein instellen, of met een service als Ngrok aan de slag. Dit domein moet je invullen bij Slack als je het manifest genereert.

### Maak een nieuwe Slack app

Op https://api.slack.com/apps kan je een nieuwe app aan maken, het makkelijkst is omdat direct in de Slack te doen waar je Dolfje wilt gebruiken. Je kan met https://github.com/ygrange/dolfje-compose/blob/main/slack_manifest/make_manifest.py een manifest genereren die je kan invullen.

### Maak de database aan

De wwmnot.sql maakt de database aan zoals je hem nodig hebt. Dolfje gebruikt een MariaDB database.
Wil je een ander type database wilt gebruiken zal je zelf de code daar voor moeten aanpassen.

TODO: KnexJS

### Maak een .env file aan

In voorbeeld.env staat welke regels er in je .env file moeten komen te staan. De informatie is te vinden in de app administratie interface van Slack in https://app.slack.com.

**Finding the Bot Token**

A bot token is used to authenticate your bot with the Slack API and perform actions within the workspace.
1. Go to Your Slack App
    - Visit the Slack API website and log in to your account.
    - Click on your app from the list of your Slack apps.

2. Navigate to 'OAuth & Permissions'
    - On the sidebar, click on the "OAuth & Permissions" page under the "Features" section.

3. Bot User OAuth Token
    - Under the "OAuth Tokens for Your Workspace" section, you'll find a token that starts with xoxb-. This is your bot user OAuth token.
    - Click the 'Copy' button to copy the token.

**Finding the Signing Secret**

The signing secret is used to verify that incoming requests to your bot's server are from Slack.

1. Go Back to Your App's Main Page
    - In the sidebar on the Slack API website, navigate back to the main page of your app.

2. Navigate to 'Basic Information'
    - Click on the "Basic Information" in the sidebar under the "Settings" section.

3. App Credentials
    - Scroll to the "App Credentials" section.
    - Here, you'll find the "Signing Secret".
    - Click the 'Show' button and then 'Copy' to copy the signing secret.

### Installeer NodeJS

Installeer NodeJS en installeer de benodige packages met `npm i`. Het is handig om ook een tool als `nodemon` te hebben om automatisch te herstarten als je code changes hebt.

### Start index.js

Start met NodeJS index.js (ik gebruik hiervoor de pm2 proces manager). `node index.js`.

## Handleidng

De gebruikershandleiding kan je hier vinden:
https://metnerdsomtafel.nl/wiki/index.php/Dolfje

## Credit

Dolfje is gemaakt door foaly, Martin en Vincent met vertaalhulp van Maikel en testhulp van oa Thijs, Gerine, Ferry en deWiskeyNerd (aka deVerteller).
Je kunt ons vinden op onze weerwolf slack https://mnot.nl/weerwolvenslack
Heb je vragen, tips, opmeringen, suggesties of wil je iets anders over Dolfje kwijt mag je op die Slack altijd foaly DMen!
Wil je je dankbaarheid tonen, mag je altijd een kop thee voor me kopen ;) https://paypal.me/foaly
