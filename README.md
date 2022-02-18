# Quizzy-Cards

Project Description: Quizzy Cards

Quizzy Cards will be a website where students can store all their study materials. Being ready for independent study or fun group games to help them learn! We have chosen college students as our target audience since college requires students to independently set up their own ways to study. Having to re-add all your questions from flashcards in a multiple choice format to a site such as kahoot can be an unnecessary amount of work that discourages students from creating fun study games. Our goal is to help students have fun while learning and make it simpler to make games by allowing students to start games from their existing flashcards requiring no extra work. We want to develop Quizzy Cards because it is something we would have used throughout our time in college as well as being a good learning experience for server-side development. 

Priority

User

Description

Technical Implementation

P0

As a user
  
I want to be able to create a flash card and view it.
    
When creating  a new flash card, it should be saved in the database and will be able to be pulled back for the user to see

P0

As a user
  
I want to be able to add flashcards to a card set.
    
When adding cards to a card set, there first will be the set creation that will have a unique id in the database. Adding cards will add the cards to the      
unique id in the database.

P0

As a user
  
I want to be able to create my own account and login/logout.
    
When creating a new account, the user information will be stored in the backend for future logins. When logging in, the system will create a session for that 
user that will be removed when the user logs out.
      
P0

As a user
  
I want to be able to share my flash card sets with other users.
    
When sharing flash card sets, the card set’s id will be added to the other user’s database so the other user can access it.
      
P1

As a user
  
I want to be able to create a game room to start a game with my selection of a flashcard set
    
The room creation will use the websocket connection. When selecting a specific flashcard set, the database will return the selected set so that users can 
start the game
      
P1

As a user
  
I want to be able to edit the setting of the game (e.g. review mode)
    
When setting up the game, the corresponding version of the game HTML file will be executed on the client side based on the user's choice. 
      
P1

As a user
  
I want to be able to vote on other users’ answers
    
All users’ answers will be shown on the client side through websocket so that users can vote. 
      
P2

As a user
  
I want to view the game history
    
When the game ends, the game result will be stored into the database with a unique id. Users’ id will be added to the game result as an attribute so that all 
users can view the results. 
      
P2

As a user
  
I want to view all the public flashcard decks created by other users
    
All public flashcard decks’ id will be saved into the database so that all users can access them. 

 

Endpoints:

/api/profile/
/api/profile/getProfile/:userID
/api/profile/updateProfile/:userID

/api/card_set/
/api/card_set/createCardSet
/api/card_set/updateCardSet
/api/card_set/deleteCardSet

/api/game/
/api/game/saveGameHistory/:roomId

Socket.io
client.emit(“initializeGame”)
client.emit(“gameCode”)
client.on(“startGame”)
client.emit(“gameState”)
client.on(“cardResponse”)
client.on(“voteOnCard”)
client.on(“progressGame”)
client.on(“restartRequest”)
client.emit(“gameComplete”)
