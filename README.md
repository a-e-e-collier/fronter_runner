# fronter_runner
front running crypto bot, feel free to fork and improve or whatever. 
you should be able to modify it to work on various exchanges
if you fork and modify please give credit
This is a tutorial to help run the front-runner bot (javascript version).

Let’s get started.

Part 1. Main software installations.

Extract the front-run-bot.zip anywhere you like.

If you don’t have Node.Js installed, download and install Node.js (LTS version, recommended).

dotenv also needs installed
# install locally (recommended)
npm install dotenv --save

Part 2. Editing the settings.

Open the bot folder find ‘.env’ file and try to open it with a text-editor:

REACT_APP_RPC_URL and REACT_APP_RPC_URL_WSS:
Here comes your providers HTTP-URL and WSS, for example: Infura. You can register on Infura for free, and get a 100.000 requests / day limit. Make sure, you don’t share these two links, because others can abuse it. Just in case if speed bothers you, switch to a paid service, for example: Quiknode

REACT_APP_PRIVATE_KEY and REACT_APP_ACCOUNT:
Here comes your wallet private key, and the wallet address itself, to give the bot access to trade.
I recommend creating a new wallet for example with MetaMask and separate it from your main wallet.

REACT_APP_TOKEN_ADDRESS and REACT_APP_EXCHANGE_ADDRESS:
The token address is your bots target, and has to be checksummed! To checksum an address.


 Change the exchange address, it will need to be updated. (ie. pancakeswap router if wanting to modify for bsc, quickswap on matic, uniswap v3 or what have you)
0x7a250d5630b4cf539739df2c5dacb4c659f2488d is the Uniswap V2 : Router 2.

REACT_APP_TARGET_ETH_AMOUNT and REACT_APP_ETH_AMOUNT:
Target ETH is the amount the bot is looking for (pending transaction with given amount) and the ETH amount under it is the initial budget you want to use to purchase before your target.


Part 3. Guide to usage.

WARNING! Before you run the bot, make sure to approve the tokens ! Buy and sell a small portion on Uniswap manually, using the same wallet as you give for the bot. OTHERWISE it's gonna buy in
but fail to sell everytime:



After approving the token you wish to front-run on, let’s run the script. To execute the process, go to START and type in: node.js command prompt and open it.

Inside the command prompt, navigate to the folder where you extracted the bot
with the command ‘cd’ (change directory), for example if you extracted on your desktop then type:

cd C:\Users\<user_name>\Desktop\bot-folder

MAKE SURE your settings are correct in the ‘.env’ file, then type in the following line to start the bot:

node index.js

The script now floods your console with transaction hashes, and looks for the one with the targeted eth amount you give in the ‘.env’ file. If the bot spots the right transaction you’ll see this pattern below:



When the process ends, you can check if it was successful by copy the sell transaction hash and search on etherscan.

Happy hunting! :)
