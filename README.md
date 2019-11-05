# neo-paper

This is a paper wallet for the Neo Smart Economy. neo-paper is the introductory work for neo-burner.

This work is largely inspired by, and structurally plagiarized from, the work of Austin Griffith for Ethereum. Thank you for your fantastic work, informative videos, and creative problem solving.

See:

[Burner Wallet](https://github.com/austintgriffith/burner-wallet)

[Paper Wallet](https://github.com/austintgriffith/paper-wallet)


# Install

`yarn`

# Build

Coming soon!

# Run

Coming soon!

# Port Module to Neo Smart Economy Status

This section shows which modules have been ported to work in the Neo Smart Economy.

generate.js HAS been ported.

airdrop.js HAS NOT been ported.
batch.js HAS NOT been ported.
create.js HAS NOT been ported.
index.js HAS NOT been ported.
report.js HAS NOT been ported.
parseListToAccounts.js HAS NOT been ported.


# paperwallet
Paper wallets to seed the [Burner Wallet](https://github.com/austintgriffith/burner-wallet) with private keys.

![paperwallets](https://user-images.githubusercontent.com/2653167/51704894-6c7be780-1fd7-11e9-8bf9-09d9a55f6943.jpg)

# install
```bash
git clone https://github.com/austintgriffith/paper-wallet
cd paper-wallet
npm i
```



# generate accounts
```bash
node generate.js
```
(This will output an `accounts.json` file with the JSON format `[{address,pk}])`

# edit design and copy
edit `template.html` to make changes and replace `front.png`, `back.png`, `inside-left.png`, and `inside-right.png` to update images

you can also set a global background with the `background.png` and a quick edit to `template.html`

# create wallets from accounts
```bash
node index.js
```

(this will output `wallets.pdf`)

# print wallets
```bash
lp wallets.pdf
```

-------------------------

You can print out `private.svg` if you are in a pinch.

If you would like me to generate you a special wallet design `cspaperwallet.jpg` hit me up on Twitter or Telegram @austingriffith

![walletsinfold](https://user-images.githubusercontent.com/2653167/51705218-3ab75080-1fd8-11e9-9495-66458938d9f9.jpg)


# batch generation

If you want to make a large batch of wallets and merge them into a single pdf for ease of printing, there is a `batch.js`:

First, get your `template.html` looking right.

Then, edit `HOWMANY` in the `batch.js` and run it:
```
node batch.js
```
This will generate a file called `wallets.pdf` and also `addresses.txt` for airdropping.

![image](https://user-images.githubusercontent.com/2653167/55583840-18306a80-56e0-11e9-80ef-16d177b415fa.png)

Finally... print, fold, cut, and glue your way to freedom!

![paperwalletprinted](https://user-images.githubusercontent.com/2653167/55584775-48790880-56e2-11e9-93b6-4034c2b0ff5d.jpg)

# air dropping

You will need a distribution account. I would suggest using a mnemonic you can remember in the Burner Wallet and then copy the private key the wallet generates.

You will then pass this private key into the airdrop script within the command you run it with or in a `.env` file:

```
echo "SENDING_PK=0xdeadbeef" > .env
```

If this account has the necessary funds on the network `provider`, it will drop whatever you specify in the `AMOUNT_OF_ERC20_TO_SEND` and `AMOUNT_OF_NATIVE_TOKEN_TO_SEND` to all `accounts.json`:
```
node airdrop.js
```

Use the CONFIG options like `justChecking`, `dryRun`, `testRun` for more control and testing.

![walletcutting](https://user-images.githubusercontent.com/2653167/51705234-4440b880-1fd8-11e9-93ed-93338376cfdc.jpg)
