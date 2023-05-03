Download Link: https://assignmentchef.com/product/solved-cs310-project-1-switch-3
<br>
<strong><u>Topics Covered</u></strong>

Generics, Array Lists, and Linked Lists

<strong> </strong>Step 0: Overview

You are going to build a small card game called <strong>SWITCH</strong> using expendable array and linked list. You will be given two abstract classes – <strong>Card</strong> and<strong> Board</strong>, from which you will implement the game specific classes – <strong>CardSwitch</strong> and <strong>BoardSwitch. </strong>You will also implement an array list-like data structure that keeps track of the cards in a player’s hand. This is the <strong>Hand</strong> class, used to represent a <strong>Player</strong> and a <strong>Deck</strong>. The <strong>Board</strong> class maintains a linked list-like data structure that keeps track of all players in the game and decides the winner of the game.




<h2>Step 1: JavaDocs</h2>

You are required to complete the JavaDoc comments for <strong>ALL</strong> classes including the ones you did not implement (except for <strong>PlaySwitch</strong>). As part of understanding this project, start with writing JavaDoc comments for the classes that are implemented for you: <strong>Card</strong>, <strong>Deck</strong>, and <strong>Board</strong>. Yes, you will be graded on this, and yes, you need to add comments to the methods and instance variables.

<h2>Step 2: Implementing and Understanding the Code<u>  </u></h2>

There is a total of <strong>7</strong> classes in the project. However, you are only required to implement some of them. See the project starter package for all the files.

<h3>The abstract Card Class (see Card.java)</h3>

<h4>[code provided: should not be modified except for adding JavaDoc comments]</h4>

A card consists of rank and suit. A regular deck of 52 cards contains 13 different ranks and 4 different

suits. Ranks consist of ACE, TWO, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, TEN, JACK, QUEEN, and KING. Suits consist of HEARTS, CLUBS, DIAMONDS, and

SPADES. In our design, every card has a point and a priority which should be implemented in its inherited classes.

<h3>The CardSwitch Class (see CardSwitch.java)</h3>

Write a class specific to the game SWITCH by extending the abstract class Card. Required methods:

public CardSwitch(Rank rank, Suit suit)

<ul>

 <li>Create a card with a given rank and suit</li>

</ul>

public int getPoints()

<ul>

 <li>Returns an integer according to the point of this card. <strong>ACE</strong> = 1 point, <strong>2</strong> = 2 points, <strong>3</strong> = 3 points, . . . , <strong>9</strong> = 9 points, (<strong>10, JACK, QUEEN, KING)</strong> = 10 points each.</li>

</ul>

public boolean equals(Card anotherCard)

<ul>

 <li>Returns true if the card is of the same rank and suit of another Card</li>

</ul>

public String toString()

<ul>

 <li>Return a string representation of the card in the form of (Rank,Suit) with all capital letters and no space. For example: (KING,SPADES) or (EIGHT,HEARTS)</li>

</ul>

<h3>The Hand&lt;T extends Card&gt; Class (see Hand.java)</h3>

Hand holds an array of cards that can be expanded. You need to implement the required methods and make sure their big-O value is as required.  Required methods:

public Hand()

<ul>

 <li>Create an empty hand</li>

</ul>




public int numCards()

<ul>

 <li>Returns the number of cards in hand</li>

</ul>




public T getCard(int index)

<ul>

 <li>Returns the card at the given index. Should throw a <strong>RuntimeException</strong> for invalid index</li>

</ul>




public void setCard(int index, T c)

<ul>

 <li>Place the given card at the given index: this will replace a card that is already at that index. Should throw a <strong>RuntimeException</strong> for invalid index</li>

</ul>




public void addCard(T c)

<ul>

 <li>Append a card to the end of the hand. Remember to expand the array if it gets full</li>

</ul>




public int indexOf(T c)

<ul>

 <li>Return the index of the given card in the hand. If the card is not present, return -1</li>

</ul>




public T removeCard(int index)

<ul>

 <li>Remove and return the card at the given index in the hand. Should throw a <strong>RuntimeException</strong> for invalid index</li>

</ul>




public boolean removeCard(T card)

<ul>

 <li>Remove the first occurrence of the given card from the hand and return true if removal was successful</li>

</ul>

<strong> </strong>

<h3>The Player&lt;T extends Card&gt; Class (see Player.java)</h3>

Player is a linked list node class consisting of name, points, hand, and next player. Required methods:




public Player(String name)

<ul>

 <li>Create a player setting the player’s name and initializing points, hand, and the next player</li>

</ul>




public void setNext(Player&lt;T&gt; p)

<ul>

 <li>Set the next player. i.e., connect the linked list node to its next</li>

</ul>




public Player&lt;T&gt; getNext()

<ul>

 <li>Get the next player. i.e., get the linked list node connected to the current</li>

</ul>




public boolean hasNext()

Return true if the player has a next player. i.e., if the current linked list node is connected







public int getPoints()

<ul>

 <li>Return the player’s points. Total points accumulated by a player in SWITCH game is the sum of points of all cards the player currently has in the hand.</li>

</ul>




public String getName()

<ul>

 <li>Return name of the player</li>

</ul>




public boolean receiveCard(T c)

Add a card to the hand and update points accordingly. Return false if the hand already contains the card, otherwise return true. If the user already has the card in hand, do NOT add it and return false.




public boolean hasCard(T c)

<ul>

 <li>Return true if the given card is present in the hand</li>

</ul>




public boolean playCard(T card)

<ul>

 <li>Remove the given card from the hand and update points accordingly. Return false if the hand does not have the card, otherwise return true</li>

</ul>




public T playCard(int index)

<ul>

 <li>Remove and return the card at the given index in the hand. Should throw a <strong>RuntimeException</strong> for invalid index</li>

</ul>




<strong>The </strong><strong>abstract Board&lt;T extends Card&gt;</strong><strong> Class  </strong>

<h4>[code provided: should not be modified except to add JavaDoc comments]</h4>

The board keeps track of the deck, current player, and the number of players. A board should be able to add players and maintains a <strong><u>circularly linked list</u></strong> of players. i.e. Player1 à Player2 à Player3 à Player1 for a 3-player board.




<h3>The BoardSwitch&lt;T extends Card&gt; Class (see BoardSwitch.java)</h3>

Write a class specific to the game SWITCH by extending the abstract class Board. Required methods:




public BoardSwitch(Deck&lt;T&gt; deck)

<ul>

 <li>Construct a board with the given deck. Make necessary initializations for other fields of Board</li>

</ul>




public Player&lt;T&gt; getCurrentPlayer()

<ul>

 <li>Return current player</li>

</ul>

public int getNumPlayers()

<ul>

 <li>Return the number of players on the board</li>

</ul>




public Deck&lt;T&gt; getDeck()

<ul>

 <li>Return board’s deck</li>

</ul>




public boolean changeTurn()

Change current player to the next player in the circular linked list. Return true if successful




public Player&lt;T&gt; findWinner()

Go through the players on the board and return the player with maximum points. Use the player’s name to break the tie (lexicographical order).  You can assume the names are unique.




public boolean addPlayer(Player&lt;T&gt; p)

<ul>

 <li>Add the given player to the left of the current player. Don’t forget to keep the linked list circular. See example below:</li>

</ul>










<h3>The Deck&lt;T extends Card&gt; Class (see Deck.java)</h3>

<h4>[code provided: should not be modified except for adding JavaDoc comments]</h4>

A deck consists of a Hand of cards. The Deck class should be able to add cards, shuffle them, deal the next card, and check the number of cards.  You will need to perform big-O analysis to all methods listed here except for the constructor.




public Deck()

<ul>

 <li>Create a deck initializing the set of cards and the card count</li>

</ul>




public boolean addCard(T c)

<ul>

 <li>Returns false if the deck already has the card. Otherwise, add the card to the deck and update the card count</li>

</ul>

public boolean hasCard(T c)

<ul>

 <li>Returns true if the deck has the given card</li>

</ul>




public void shuffle()

<ul>

 <li>Randomly shuffles the deck</li>

</ul>




public T dealNextCard()

Returns false if the deck has no cards. Otherwise, return the last card in the deck, remove it from the deck and update the card count




public boolean isEmpty()

<ul>

 <li>Returns true if the deck is empty. Otherwise returns false</li>

</ul>




public int cardCount()

<ul>

 <li>Returns the number of cards in the deck</li>

</ul>

public String toString()

<ul>

 <li>Returns a string consisting of the cards in the deck</li>

</ul>

<strong> </strong>

<h3>The PlaySwitch Class (see PlaySwitch.java)</h3>

<h4>[code provided: should not be modified.  No JavaDoc comments required]</h4>

A provided implementation of a simple game with cards.  The game follows these steps:

<ol>

 <li>Creating a full deck of 52 cards</li>

 <li>Creates players and adds them to board</li>

 <li>Deal all cards to users one by one (all players may not receive same number of cards)</li>

 <li>Switch the first n cards between the players</li>

 <li>Player with the higher total points of all cards in hand is the winner</li>

</ol>




<h2>Step 3: Big-O</h2>

Template given to you in the starter package contains instructions on the REQUIRED Big-O runtime for each method. Your methods should <strong><u>not</u></strong> have a higher Big-O. For class <strong>Deck</strong>, you are required to present Big-O run time for all methods (as comments within the code) in addition to Javadoc commenting. Again yes, you will be graded on this.




<strong> </strong>

<h1>Step 4: Testing</h1>

Test cases will not be provided for this project. However, feel free to create test cases by yourselves. In addition, the main methods provided along with the template classes contain useful code to test your code. You can use command like “java CardSwitch” to run the testing defined in main( ).  You could also edit main( ) to perform additional testing.  And yes, a part of your grade will be based on automatic grading using test cases that are not provided to you.

<strong>          </strong>




<h1><u>EXAMPLE RUNS </u></h1>

<strong> </strong>

<h2><u>SAMPLE RUN#1 </u></h2>

Enter the number of players: 3

Enter Name of Player 1:

Daenerys

Enter Name of Player 2:

Jon

Enter Name of Player 3:

Cersei

How many cards should be switched?

5

———————————–

-Starting ROUND 1-

switch from Jon:  card (TEN,CLUBS),  switch to Cersei switch from Cersei:  card (KING,HEARTS),  switch to Daenerys switch from Daenerys:  card (JACK,CLUBS),  switch to Jon

-Starting ROUND 2-

switch from Jon:  card (FIVE,CLUBS),  switch to Cersei switch from Cersei:  card (NINE,SPADES),  switch to Daenerys switch from Daenerys:  card (SIX,SPADES),  switch to Jon

-Starting ROUND 3-

switch from Jon:  card (JACK,DIAMONDS),  switch to Cersei switch from Cersei:  card (KING,CLUBS),  switch to Daenerys switch from Daenerys:  card (KING,DIAMONDS),  switch to Jon

-Starting ROUND 4-

switch from Jon:  card (QUEEN,SPADES),  switch to Cersei switch from Cersei:  card (SEVEN,DIAMONDS),  switch to Daenerys switch from Daenerys:  card (JACK,SPADES),  switch to Jon

-Starting ROUND 5-

switch from Jon:  card (ACE,DIAMONDS),  switch to Cersei switch from Cersei:  card (SIX,HEARTS),  switch to Daenerys switch from Daenerys:  card (ACE,CLUBS),  switch to Jon

———————————–

Winner is: Daenerys with 127 points





































<h2><u>SAMPLE RUN#2 </u></h2>

Enter the number of players: 5

Enter Name of Player 1:

Ironman

Enter Name of Player 2:

Hulk

Enter Name of Player 3:

CaptainAmerica

Enter Name of Player 4:

Hawkeye

Enter Name of Player 5:

BlackWidow

How many cards should be switched?

3

———————————–

-Starting ROUND 1-

switch from CaptainAmerica:  card (TEN,DIAMONDS),  switch to Hawkeye switch from Hawkeye:  card (NINE,HEARTS),  switch to BlackWidow switch from BlackWidow:  card (JACK,HEARTS),  switch to Ironman switch from Ironman:  card (QUEEN,SPADES),  switch to Hulk switch from Hulk:  card (JACK,CLUBS),  switch to CaptainAmerica

-Starting ROUND 2-

switch from CaptainAmerica:  card (KING,SPADES),  switch to Hawkeye switch from Hawkeye:  card (SEVEN,HEARTS),  switch to BlackWidow switch from BlackWidow:  card (KING,DIAMONDS),  switch to Ironman switch from Ironman:  card (SIX,CLUBS),  switch to Hulk

switch from Hulk:  card (NINE,DIAMONDS),  switch to CaptainAmerica

-Starting ROUND 3-

switch from CaptainAmerica:  card (THREE,CLUBS),  switch to Hawkeye switch from Hawkeye:  card (FIVE,DIAMONDS),  switch to BlackWidow switch from BlackWidow:  card (TWO,HEARTS),  switch to Ironman switch from Ironman:  card (EIGHT,SPADES),  switch to Hulk switch from Hulk:  card (SEVEN,DIAMONDS),  switch to CaptainAmerica

———————————–

Winner is: Hulk with 77 points


