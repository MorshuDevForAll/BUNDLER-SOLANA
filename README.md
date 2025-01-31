If you want to get the package contact https://t.me/MorshuDevForAll

First Time Installation

Install NodeJS (https://nodejs.org/en/download/)
Install Dependencies (npm install)
Run the project (npm run start)
** DO NOT SHARE YOUR PRIVATE KEYS WITH ANYONE ** ** I SUGGEST HIGHLY TO RUN STEPS 1-6 IN ORDER (4 is optional) FOR BEST RESULTS ** ** STOP USING FREE RPCS AND COMPLAINING NOTHING LANDS, USE A PAID RPC **

ENV SETUP RENAME THE FILE TO .env

SIGNER_PRIVATE_KEY = PRIVATE KEY OF DEV WALLET DEV_ADDRESS = WALLET ADDRESS OF DEV WALLET (PUBLIC KEY) FUNDER_PRIVATE_KEY = PRIVATE KEY OF FUNDER WALLET (WALLET THAT WILL FUND THE SUB WALLETS) RPC_URL = YOUR RPC URL (HTTP OR HTTPS) WS = YOUR WS URL (WSS OR WS) BLOCKENGINEURL = JITO BLOCKENGINE URL (see list below) JITO_TIP = JITO TIP AMOUNT (SOL) SELL_TIP = SELL TIP AMOUNT (SOL) NFT_STORAGE_TOKEN = DO NOT EDIT THIS DO NOT EDIT THIS DO NOT EDIT THIS DO NOT EDIT THIS DO NOT EDIT THIS DEVBUY = AMOUNT OF SOL TO BUY ON DEV WALLET MINBUY = NO LONGER USED MAXBUY = NO LONGER USED LUT_Address = LOOKUP TABLE ADDRESS (DO NOT EDIT THIS, THE BOT WILL CREATE & UPDATE THIS) BLOXKEY = BLOXROUTE API KEY (BEARER/HEADER/AUTH TOKEN FROM DASHBOARD) BLOX_EP = BLOXROUTE ENDPOINT (LIST BELOW) COMPUTE_LIMIT_PRICE = COMPUTE LIMIT PRICE (LAMPORTS) (https://www.solconverter.com/) COMPUTE_UNIT = COMPUTE UNIT (LAMPORTS) (https://www.solconverter.com/) CAP_SOLVER_API_KEY = CAP SOLVER API KEY (https://www.capsolver.com/)

NOTE: DUE TO SLIPPAGE THESE VALUES MAY NOT BE EXACT SO FUND WALLETS WITH EXTRA SOL

(METADATA SETUP)

name: Token Name symbol: Ticker (max 10 char) description: Token Description (Max 30 char) image: LEAVE BLANK showName: DON'T EDIT twitter: Twitter link telegram: Telegram channel link website: website URL

NOTES:

Socials can be left blank if you dont want to use any. MAKE SURE TO LEAVE IMAGE VALUE BLANK YOU MUST PUT THE TOKEN IMAGE IN THE /img DIRECTORY TICKER / SYMBOL MAX 10 CHARACTERS ONE IMAGE IN DIRECTORY ONLY (FILE NAME + EXTENTION DON'T MATTER)

BLOCKENGINEURLS (pick the closest to your location): AMSTERDAM: amsterdam.mainnet.block-engine.jito.wtf FRANKFURT: frankfurt.mainnet.block-engine.jito.wtf NEW YORK: ny.mainnet.block-engine.jito.wtf TOKYO: tokyo.mainnet.block-engine.jito.wtf

BLOXROUTE ENDPOINTS: NEW YORK: https://ny.solana.dex.blxrbdn.com ENGLAND: https://uk.solana.dex.blxrbdn.com

MODES:

WALLET GEN: Generates wallets and stores the keypairs to /keypairs directory as JSON files & wallet.txt as pubkey:privkey

WALLET UI:

*FUND: Funds the wallets with SOL (MUST RUN THIS BEFORE BUNDLER) *BALANCE: Checks SOL Balance of all Sub Wallets *TRANSFER TOKENS: Transfers the token from the SUB Wallets to the DEV wallet *REFUND SOL: Returns all SOL from SUB wallets to funder Wallet! (note 0.0008xx SOL is left in each wallet to pay rent fees) *VANITY GEN: Generates vanity token address ending in "pump" stored in /token folder. (08/25/2024 -> this mode is depreciated) *CLOSE TOKEN ACCTS: Closes all token accounts reclaiming the rent fee in SOL. *WALLET WARMUP: This mode will buy & sell recently traded tokens with a random SOL amount between your 0.01/0.05 SOL to generate human-like activity on sub wallets. *BURN DEV SUPPLY: This mode, will prompt entry (0-100) for the percent of devs holdings to burn. *IMPORT WALLETS: This mode will prompt amount of wallets (max 20) to import, then ask for the BASE58 Value Private Key for each wallet, and properly write to wallets.txt allowing you to use out of bot generated wallets like bullX or photon. *EXIT: Return to main menu

*CREATE LOOKUP TABLE: Creates a lookup table to allow for 20 wallet to work for buying/selling (MUST RUN THIS BEFORE BUNDLER)

*PROFILE GEN: Generates profiles for the sub wallets on pump.fun (Random username + bio + coin holdings)

*LAUNCH UI: *SET BUY AMT: Sets the buy amounts per wallet for all modes. *LAUNCH PUMP: Executes the token creation + bundle buy of all sub wallets *MAGIC MODE: Executes the token creation, and then snipes all sub wallets after token is made *SNIPE ONLY: Snipes all sub wallets on the coin you input when prompted *STAGGER BUY: This mode will prompt you to launch + stagger or only stagger buys (enter CA manually), along with the delay set between sending each sub wallet buy! *FRONT RUN MODE: This mode will create the token & dev buy in the same TX WITHOUT JITO, it will be sent (at maximum) 6 blocks before the next JITO leader, then it will send the bundle snipes when the next JITO leader is within 2 slots, essentially, you are trying to land the create, 2 blocks before the snipes. I have found this mode to be most successful if the leader is over 8 slots away (minimum), so I have added logic to wait for next leader if this condition is not met. THIS MODE IS EXTREMEEEEEEEEELY EXPERIMENTAL *SIMULATE BUYS: This mode will display estimated data of how much tokens u will buy, the % of supply per wallet, and the cost with 15% slippage. It will also display total sum values of the above! *FAKE LIVESTREAM: Fakes a livestream on your coin, displaying the "this coin is live" banner on terminal. *CLONE METADATA: This mode will clone the metadata + image of any token inputted so you can launch it yourself! (MUST BE A PF TOKEN)

MAIN MENU: Returns to main menu

SELL: *DUMP ALL: DUMPS 100% of tokens in every SUB wallet AND DEV WALLET in 1 bundle *DUMP %: DUMPS A SPECIFIC PERCENTAGE OF TOKENS IN EVERY SUB WALLET AND DEV WALLET *DELAY SELL ALL: Sells 100% of supply in all SUB wallets with a delay between each TX *DELAY SELL %: Sells a specific percentage of supply in all SUB wallets with a delay between each TX *SINGLE SELL (%): Sells a specific percentage of supply in a single SUB wallet (enter 100 to sell all tokens in a single wallet) *DEV DUMP: Transfers all tokens from SUB wallets -> Dev Address from .env then DUMPS 100% of tokens in Dev Wallet *TRANSFER SELL: Transfer Tokens from Sub Wallets -> Seller Wallet & dumps in 1 TX *AUTO SELL: This mode will prompt for the target Market Cap and once reached, will execute dump all mode!

RAYDIUM: *CREATE WSOL: Creates WSOL Accounts for every wallet + dev wallet *RAY LUT: Extends LUT to include Raydium Data (SUPER IMPORTANT) *RAY SELL: Sells tokens on Raydium (Enter % and include dev (T/F)) (T = True, F = False) (0-100 %) *TRANSFER SELL: Transfer Tokens from Sub Wallets -> Seller Wallet & dumps in 1 TX *DELAY SELL: Sells tokens on Raydium (Enter % and include dev) (T = True, F = False) (0-100%) with a delay between each wallets sell TX. *UNWRAP: Unwraps WSOL to SOL *EXIT: Exits the program

🍬 Tips & Tricks Tips & Tricks for Running Infinity AIO

How To Guide Step 1: Generate Wallets (20 max)

Step 2: Wallet UI -> fund wallets -> Vanity Gen (optional)

Step 3: Create LUT (MUST RUN THIS EVERY LAUNCH W NEW SUB-WALLETS)

Step 4: Create Profiles (optional)

Step 5: Launch UI -> Set Buy Amounts -> Launch Pump / Launch + Snipe

Step 6: Sell UI -> Pick desired sell method

Step 7: Raydium UI -> Create WSOL -> Extend LUT (ONLY AFTER TRADING IS LIVE ON RAY) -> Sell -> Unwrap wSOL

JITO Stuff Tip Amt: I suggest running default values as they've been tested and work well

Block Engine: Suggested to pick the closest to your location

Tips are paid from dev wallet (signer_priv_key/dev_address in env)

Wallets Ideally fund each wallet with 0.1 sol MORE THAN its buy amount.

RPC We cannot help you figure out what RPC to use, this is up to you (the user) to figure out We are partnered with o7 Node (https://discord.gg/wHzwnFfW2R) which is a good RPC but for the snipe/experimental modes you may want to find something else, ideally a private RPC hosted in the same location as your VPS/Server

SERVER/VPS Google Cloud Servers offer affordable VPSs along with free trial credits, however this is on the user to decide what VPS to use.

NOTE:

WALLETS WILL BE OVERWRITTEN IF YOU RUN WALLET GEN AGAIN SO REMOVE ALL SOL FROM THEM BEFORE RUNNING WALLET GEN AGAIN
NOTE: As of v0.04 All Keypairs/Wallets ever made on the version will be stored in /keypairBackup directory & /walletBackup directory

DO NOT MODIFY MINT.JSON or ANY FILES IN THE /res directory
DO NOT MODIFY THE NFT STORAGE KEY IN .env
DO NOT MODIFY THE PUMP-IDL.JSON FILE
** DO NOT SHARE YOUR PRIVATE KEYS WITH ANYONE ** ** I SUGGEST HIGHLY TO RUN STEPS 1-6 IN ORDER (4 is optional) FOR BEST RESULTS ** ** STOP USING FREE RPCS AND COMPLAINING NOTHING LANDS, USE A PAID RPC **
