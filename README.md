#Battleship
##Description
The application is a single and multi-player battleship game entirely made with Oracle Application Express 5.0. 
The game is played on four grids, two for each player. The grids are 10×10. On one grid the player arranges ships and records of the opponent's shots is shown. On the other grid records of the player's shots are shown.

Before play begins, each player secretly arranges their ships on their primary grid. Each ship occupies a number of consecutive squares on the grid, arranged either horizontally or vertically. The number of squares for each ship is determined by the type of the ship. The ships cannot overlap (i.e., only one ship can occupy any given square in the grid). The types and numbers of ships allowed are the same for each player.

| Type of ship | Size |
| :----------- | :--: |
| Carrier      | 5    |
| Battleship   | 4    |
| Submarine    | 3    |
| Cruiser      | 3    |
| Destroyer    | 2    |

After the ships have been positioned, the game proceeds in a series of rounds. In each round, each player takes a turn to select a target square in the opponent's grid which is to be shot at. If the targeted square in the opponent's grid is occupied by a ship, it's marked as a hit (red square), otherwise, it's marked as a miss (blue square).

When all of the squares of a ship have been hit, the ship is sunk. If all of a player's ships have been sunk, the game is over and their opponent wins.

This game was designed and built to be part of the [ODTUG APEX Gaming Competition 2015](http://competition.odtug.com/).

##Game Features
* Play against other user
* Play against the AI
* Desktop, tablet and smartphone compatible
* In-game sound effects
* Drag and drop ship placement
* Chat with online users
* User profile with statistics and game history
* Game replay
* Resume unfinished game
* Fully integrated with Apex
* Bidirectional communication

##Demo
A demo application is available at:
http://max-playground.no-ip.org/ords/f?p=BATTLESHIP

You will have to create an account and login using your email address.

##Requirements
In order to install and run the application, you will require the following:

* A free pubnub account ([register here](https://www.pubnub.com/))
* An Oracle Database 11gR2 or later with Oracle Application Express release 5.0
  * Be able to connect as SYS using the SYSDBA role
  * Network services must be enabled for the Oracle Application Express' user

##Installation
###1. Oracle Application Express
1. Create a new Workspace
2. Import the battleship application (battleship.sql)
  * The import process will create all of the required database objects (tables, sequences, triggers, packages, etc.)
    * All of the database objects are prefixed with "BS_"

###2. Database
1. Connect to the database where Oracle Application Express is installed as SYS specifying the SYSDBA role.
 * Grant to dbms_crypto (needed for password encryption/decryption in the app)

> grant execute on sys.dbms_crypto to APP_SCHEMA;

##Configuration
###App Settings - Substitution Strings
* Change the string HOST_URL and HOST_LOCATOR to the actual url of the server.
  * e.g.: `http://max-playground.no-ip.org/ords/f?p=BATTLESHIP`
    * HOST_URL : `http://max-playground.no-ip.org`
    * HOST_LOCATOR: `ords`
* Change the string PUBNUB_PUBLISH_KEY with your Pubnub's account publish key
* Change the string PUBNUB_SUBSCRIBE_KEY with your Pubnub's account subscribe key
* Change the string APP_FROM_EMAIL with the corresponding Oracle Application Express from email address

You are now ready to go, chat and play with other users.

Enjoy !!

##Changelog
###1.13 Resume unfinished game with the AI or a user

###1.12 New themes
* Can only be changed from the Theme Roller
  * Dark theme (default theme)
  * Light theme
  
###1.10 Improved the AI
* When a ship has been hit, the AI will only try adjacent cells, if the corresponding ship can be placed in a way so that it can be placed on the corresponding adjacent cell

###1.10 AI implementation

###1.09 Presence detection
* User leaves or joins the chat
* User leaves a game

###1.08 Security enhancement
* Make sure it's the player's turn when making a move
* Make sure the ship has not been placed already when placing a ship

###1.07 Tablet and smartphone adjustments

###1.06 Game replay from the game history

###1.05 Statistics page with game history

###1.04 Sound effects when a hit/miss 

###1.03 Drag and drop ship placement

###1.02 Retrieve and show game progress
* When a user refreshes the page while in a game

###1.01 Manual ship placement

###1.00 Initial release
* Basic chat
* Random ship placement

##Libraries
###[PubNub](https://www.pubnub.com/)
Service used for the bidirectional communication

###[Howler.js](https://github.com/goldfire/howler.js)
Used in game to play sound effects.

###[jQuery-contextMenu](https://github.com/swisnl/jQuery-contextMenu)
Used in the chat to have a context menu on the user list.

###[Notify.js](http://notifyjs.com)
Used in game to show notifications.

##Oracle Application Express Plugin
###[Select2](https://github.com/nbuytaert1/apex-select2)
Used in the user profile

##License
This application is under MIT License
[LICENSE](https://github.com/maxime-tremblay/apex-battleship/blob/master/LICENSE)
