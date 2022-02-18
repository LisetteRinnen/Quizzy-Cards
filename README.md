<!-- Output copied to clipboard! -->

<!-----

Yay, no errors, warnings, or alerts!

Conversion time: 0.529 seconds.


Using this Markdown file:

1. Paste this output into your source file.
2. See the notes and action items below regarding this conversion run.
3. Check the rendered output (headings, lists, code blocks, tables) for proper
   formatting and use a linkchecker before you publish this page.

Conversion notes:

* Docs to Markdown version 1.0β33
* Thu Feb 17 2022 21:05:13 GMT-0800 (PST)
* Source doc: Untitled document
* Tables are currently converted to HTML tables.
----->


**Project Description: Quizzy Cards**

	Quizzy Cards will be a website where students can store all their study materials. Being ready for independent study or fun group games to help them learn! We have chosen college students as our target audience since college requires students to independently set up their own ways to study. Having to re-add all your questions from flashcards in a multiple choice format to a site such as kahoot can be an unnecessary amount of work that discourages students from creating fun study games. Our goal is to help students have fun while learning and make it simpler to make games by allowing students to start games from their existing flashcards requiring no extra work. We want to develop Quizzy Cards because it is something we would have used throughout our time in college as well as being a good learning experience for server-side development. 


<table>
  <tr>
   <td>Priority 
   </td>
   <td>User
   </td>
   <td>Description
   </td>
   <td>Technical Implementation
   </td>
  </tr>
  <tr>
   <td>P0
   </td>
   <td>As a user
   </td>
   <td>I want to be able to create a flash card and view it.
   </td>
   <td>When creating  a new flash card, it should be saved in the database and will be able to be pulled back for the user to see
   </td>
  </tr>
  <tr>
   <td>P0
   </td>
   <td>As a user
   </td>
   <td>I want to be able to add flashcards to a card set.
   </td>
   <td>When adding cards to a card set, there first will be the set creation that will have a unique id in the database. Adding cards will add the cards to the unique id in the database.
   </td>
  </tr>
  <tr>
   <td>P0
   </td>
   <td>As a user
   </td>
   <td>I want to be able to create my own account and login/logout.
   </td>
   <td>When creating a new account, the user information will be stored in the backend for future logins. When logging in, the system will create a session for that user that will be removed when the user logs out.
   </td>
  </tr>
  <tr>
   <td>P0
   </td>
   <td>As a user
   </td>
   <td>I want to be able to share my flash card sets with other users.
   </td>
   <td>When sharing flash card sets, the card set’s id will be added to the other user’s database so the other user can access it.
   </td>
  </tr>
  <tr>
   <td>P1
   </td>
   <td>As a user
   </td>
   <td>I want to be able to create a game room to start a game with my selection of a flashcard set
   </td>
   <td>The room creation will use the websocket connection. When selecting a specific flashcard set, the database will return the selected set so that users can start the game
   </td>
  </tr>
  <tr>
   <td>P1
   </td>
   <td>As a user
   </td>
   <td>I want to be able to edit the setting of the game (e.g. review mode)
   </td>
   <td>When setting up the game, the corresponding version of the game HTML file will be executed on the client side based on the user's choice. 
   </td>
  </tr>
  <tr>
   <td>P1
   </td>
   <td>As a user
   </td>
   <td>I want to be able to vote on other users’ answers
   </td>
   <td>All users’ answers will be shown on the client side through websocket so that users can vote. 
   </td>
  </tr>
  <tr>
   <td>P2
   </td>
   <td>As a user
   </td>
   <td>I want to view the game history
   </td>
   <td>When the game ends, the game result will be stored into the database with a unique id. Users’ id will be added to the game result as an attribute so that all users can view the results. 
   </td>
  </tr>
  <tr>
   <td>P2
   </td>
   <td>As a user
   </td>
   <td>I want to view all the public flashcard decks created by other users
   </td>
   <td>All public flashcard decks’ id will be saved into the database so that all users can access them. 
   </td>
  </tr>
</table>


Endpoints:

/api/profile/



* /api/profile/getProfile/:userID
* /api/profile/updateProfile/:userID

/api/card_set/



* /api/card_set/createCardSet
* /api/card_set/updateCardSet
* /api/card_set/deleteCardSet

/api/game/



* /api/game/saveGameHistory/:roomId

Socket.io



* client.emit(“initializeGame”)
* client.emit(“gameCode”)
* client.on(“startGame”)
* client.emit(“gameState”)
* client.on(“cardResponse”)
* client.on(“voteOnCard”)
* client.on(“progressGame”)
* client.on(“restartRequest”)
* client.emit(“gameComplete”)
