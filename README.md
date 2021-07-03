# E Voting DApp

Built a voting application with 4 Indian political parties such that there is a chairperson who is authorized to register voters. Voters have the permission to vote only once and the chairperson's vote carries a weightage of 2.

## Business Logics handled
1. Chairperson registers accounts to vote
2. No other account can register accounts to vote, the option to register isn't made available to any other used logged in who is not the chairperson
3. Can't register already registered user
4. Unregistered account can't vote
5. Registered accounts cannot vote twice
6. Can't vote a person who is not there, option isn't even there on the web application

## Prerequisite
1. NodeJs
2. Metamask (3.14.1)
3. Truffle (v4.0.4)
4. Ganache

## Instruction for truffle testing
1. Clone the repository to a local folder
2. Go to the cloned folder using command line ( for this example, inside the "main" folder ) 
3. Execute truffle compile
4. Open a new command line and execute truffle migrate --reset
5. Execute truffle test

This should print the following in the console

 Contract: BallotContract
    ✓ contract deployment
    ✓ valid users registration
    ✓ valid voting
    ✓ validate winner
    ✓ valid votes
    ✓ should NOT accept unauthorized registration
    ✓ should NOT register already registered user
    ✓ should NOT vote from unauthorized account
    ✓ should NOT vote twice
    ✓ should NOT vote unknown person

    10 passing

### The testing isn't required to be done again and again. Once any changes are made to either the Smart Contract or the test parameters, then it makes sense to repeat this process. If no change has been made, then even "truffle compile" isn't required, you can directly write "truffle migrate --reset" on the terminal after quickstarting the Ganache Ethereum Server.

## Instructions for DApp

### Firstly, open Ganache and quickstart an Ethereum server. 

1. Now to start the nodeJs server execute npm run dev in the same terminal you typed "truffle migrate --reset". The npm run dev command follows the "truffle migrate --reset" command.
2. This should start the front end of the application at localhost:3000
3. Open Metamask in your chrome browser and enter the key phrase you got after executing Ganache
4. Now connect to private network using http://127.0.0.1:7545 and Chain ID 1337 and create as many accounts as you want.
5. Now you should be in the first account in the metamask and connect all other accounts by copying their private key provided in Ganache.
6. Connect them to the network.
7. Now to register, register as many voters as you want using the account 1.
8. Now to cast vote from the account 2 change the account in Metamask from account 1 to account 2 and then click vote. 
9. To vote from any account switch to that account in metamask and then click vote.
10. Finally, after voting you can click declare winner.

Note:
1. To deploy a new instance of the contract exit the npm server and then execute truffle migrate --reset and then start the server again.
2. The contract is deployed from account[0] i.e the first account in the Ganache window.
3. Refer to the Outputs provided to get a better idea of the instructions for DApp.
