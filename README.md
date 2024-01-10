# Foundry Simple Storage

Contract is deployed at 0x94953A47a9385e4549Ca575c541937B38F4dd7a4
[View on Sepolia](https://sepolia.etherscan.io/address/0x94953a47a9385e4549ca575c541937b38f4dd7a4)

It is a simple contract used for storing number. And change the stored number anytime we want.
It is a small contract but efficient for learning foundry basics and what a contract looks like.

# Getting Started

## Requirements

- [ganache](https://trufflesuite.com/ganache/)
  - You'll know you did it right if you can run the application and see:
    <br>
    <img src="https://github.com/Cyfrin/foundry-simple-storage-f23/blob/main/img/ganache-picture.png" alt="ganache" width="200"/>
  - You can alternatively use [ganache-cli](https://www.npmjs.com/package/ganache-cli) or [hardhat](https://hardhat.org/)
- [foundry](https://getfoundry.sh/) or foundry Anvil command: `anvil` as Ganache could be deprecated or discontinued by the time.
  - You'll know you did it right if you can run `forge --version` and you see a response like `forge 0.2.0 (816e00b 2024-01-16T00:05:26.396218Z)`

If you're installing foundry for the first time, you can put this in your `.bash_profile` or `.zshrc` depending on if you're using bash or zsh shell.

You can check which shell you are currently using by looking at the value of the SHELL environment variable or examining the current process name. Run the following command in your terminal:

```bash
echo $SHELL
```

And you'll see if you're using bash or zsh.


```bash
if [ -f ~/.bashrc ]; then
    source ~/.bashrc
fi
```


If you are using zsh, make sure to place your configurations, aliases, and functions in the .zshrc file located in your home directory. If the file doesn't exist, you can create it with touch ~/.zshrc. 


## Setup

Clone this repo

```
git clone https://github.com/Jer-B/Foundry_Simple_storage
cd Foundry_Simple_storage
```

## Usage

### If using Ganache
1. Run your ganache local chain, by hitting `quickstart` on your ganache application

> Save the workspace. This way, next time you open ganache you can start the workspace you've created, otherwise you'll have to redo all the steps below.

2. Hit the key on one of the accounts, and copy the key you see and place it into your `.env` file, similar to what you see in `.env.example`. Like the Below

PRIVATE_KEY_GANACHE=11ee3108a03081fe260ecdc106554d09d9d1209bcafd46942b10e02943effc4a

### If using Anvil
1. You can use the same informations for the Key and RPC URL that is inside the `.env.example`

Then, 

2. Compile your code

Run

```
forge compile
```

3. Deploy your contract

```
forge create --private-key <PRIVATE_KEY>
```
Be sure to replace `<PRIVATE_KEY>` by the Wallet private key Variables that correspond to the RPC you chose

## Windows, WSL, & Ganache
If you're using WSL, for the ganache UI you'll have to use a different endpoint.
You have 4 options to fix this:

1. Use the WSL endpoint on the ganache UI (this sometimes doesn't work)
2. Use `anvil` 


### Deploying to a testnet

Make sure you have a [metamask](https://metamask.io/) or other wallet, and export the private key.

**IMPORTANT**

USE A METAMASK THAT DOESNT HAVE ANY REAL FUNDS IN IT. Just in case you accidentally push your private key to a public place. I _highly_ recommend you use a different metamask or wallet when developing.

1. [Export your private key](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key) and place it in your `.env` file, as done above.

2. Go to [Alchemy](https://alchemy.com/?a=673c802981) and create a new project on the testnet of choice (ie, Sepolia)
3. Grab your URL associated with the testnet, and place it into your `.env` file.
4. Make sure you have [testnet ETH](https://faucets.chain.link/) in your account. You can [get some here](https://faucets.chain.link/). You should get testnet ETH for the same testnet that you made a project in Alchemy (ie, Goerli)
5. Run

```
forge create --private-key <PRIVATE_KEY> --rpc-url <ALCHEMY_URL>
```

Or, you can use a deploy script!

```
forge script script/DeploySimpleStorage.s.sol --private-key <PRIVATE_KEY> --rpc-url <ALCHEMY_URL>
```
Be sure to replace `<PRIVATE_KEY>` by the Wallet private key Variables that correspond to the RPC you chose
