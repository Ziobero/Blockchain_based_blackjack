# Blockchain-based blackjack
This is the repository created for the group project for Fintech and Blockchain class of the Msc in Data science and Business analytics. The group is composed by:
- Bellucci Emanuele (group leader);
- Bricarelli Paolo;
- Bruno Luca;
- Nuti Silvia;
- Roscioli Dimitri.

## Goal of the project
The goal of this project is to deliver a prototype of a blockchain-based blackjack software built as an Ethereum smart contract that exploits the characteristics of Ethereum blockchain to deliver a fairer way of playing blackjack. The main advantage of this new implementation relies on its transparency: in fact, players can see how the algorithm works behind the scenes, while in a typical blackjack software written for an online casino nobody knows what’s inside this black box (apart from the casino itself).

## How the game works 
Apart from the currency used and the system deployed to distribute cards to the player and the dealer, the rules will be the same as the ones of the classic Blackjack. Gamers can use their ETH stored in some wallet as currency to place their bets and the algorithm will distribute cards in a total random way. The Blackjack smart contract will work as follows: 
- the player starts the game by placing a bet; 
- after having run all the controls needed to check the validity of the bet, the player enters into the game and can either ask for a new card or stand; 
- whwn all the cards have been distributed (both to the player and to the croupier), the winner is declared, and the amount of ETH won is transferred instantaneously to the player or the dealer (that represents the casino in this case). 

## The random generator problem
How each random card is generated? We can write a function GenerateRandomCard() that takes as inputs the player’s address and the hash of a new (not already) mined block. When the gamer presses the button ‘get a new card’, the block hash of this newly mined block together with the player’s address, they will be hashed together to form a new hash that will be used to calculate which card will be distributed. Keep in mind that the same mechanism is applied to the croupier. To know which card will be distributed, the algorithm takes the new hash generated inside the function and it will extract only its numbers. Then the digits will be stack together to form a big number which will be divided by 132. If the remainder of this operation is 0, the card will be an ace; if the remainder is 1, the card will be a two, and so on. Having 6 decks stacked together, the possibility you get, for instance, 25 Queens (1 more than the maximum possible number) is almost insignificant, so I don’t think I must implement any system to prevent this. By using this new system, however, there could be the case in which a player who has a huge computing power mines a valid block and see in advance the card that will be distribute; then he could decide to broadcast the block to the network (or not), giving him the possibility to cheat. This situation could be avoided by setting the maximum amount of ETH a player/croupier could win to be less than the reward coming from mining a new valid block.  
