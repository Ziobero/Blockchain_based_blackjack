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
