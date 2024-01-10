# English README　[Jump to Japanese Version](#japanese)

# Preview
For an easy interaction with the contract use abi.ninja website.
Here is a link to the contract loaded on it: [Simple Storage contract](https://abi.ninja/0x94953A47a9385e4549Ca575c541937B38F4dd7a4/sepolia?functions=getNameFromNumber%2CgetNumberFromName%2CgetPersonAtIndex)

Click on function on the left to add them in the center of the page and interact with them.
Functions under the 'READ' category are for getting actual values.
Functions under the 'Write' category are for inserting new data.

# Foundry Simple Storage

Contract is deployed at 0x94953A47a9385e4549Ca575c541937B38F4dd7a4
[View on Sepolia](https://sepolia.etherscan.io/address/0x94953a47a9385e4549ca575c541937b38f4dd7a4)

It is a simple contract used for storing number. And change the stored number anytime we want.
It is a small contract but efficient for learning foundry basics and what a contract looks like.

I used the 32 hours long video from Cyfrin Foundry Blockchain course to learn about Foundry.  
[Cyfrin Foundry](https://github.com/Cyfrin/foundry-full-course-f23)

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

<a name="japanese"></a>
# 日本語版のREADME

# プレビュー
コントラクトとの簡単な対話には abi.ninja ウェブサイトを使用してください。
以下は、それにロードされたコントラクトへのリンクです: [Simple Storage contract](https://abi.ninja/0x94953A47a9385e4549Ca575c541937B38F4dd7a4/sepolia?functions=getNameFromNumber%2CgetNumberFromName%2CgetPersonAtIndex)

左側の関数をクリックして、それらをページの中央に追加し、それらと対話します。
「READ」カテゴリーの下にある関数は実際の値を取得するためのものです。
「Write」カテゴリーの下にある関数は新しいデータを挿入するためのものです。

# Foundry Simple Storage

このコントラクトは、0x94953A47a9385e4549Ca575c541937B38F4dd7a4 にデプロイされています。
[Sepoliaで表示](https://sepolia.etherscan.io/address/0x94953a47a9385e4549ca575c541937b38f4dd7a4)

これは数値を格納するためのシンプルなコントラクトです。そして、いつでも格納された数値を変更できます。
これは小さなコントラクトですが、Foundryの基本やコントラクトの構造を学ぶのに効果的です。

Foundryを学ぶために、Cyfrin Foundry Blockchainコースの32時間の長いビデオを使用しました。
[Cyfrin Foundry](https://github.com/Cyfrin/foundry-full-course-f23)

# 開始方法

## 必要なもの

- [ganache](https://trufflesuite.com/ganache/)
  - アプリケーションを実行し、以下の画像を表示できれば成功です:
    <br>
    <img src="https://github.com/Cyfrin/foundry-simple-storage-f23/blob/main/img/ganache-picture.png" alt="ganache" width="200"/>
  - 代替として [ganache-cli](https://www.npmjs.com/package/ganache-cli) または [hardhat](https://hardhat.org/) を使用できます。
- [foundry](https://getfoundry.sh/) または foundry Anvil コマンド: Ganache が廃止されるか廃止される可能性があるためです。
  - `forge --version` を実行して、次のようなレスポンスが表示されれば成功です: `forge 0.2.0 (816e00b 2024-01-16T00:05:26.396218Z)`

初めて foundry をインストールする場合、`.bash_profile` または .zshrc に次のコードを追加できます。使用しているシェルに応じて、.bashrc または .zshrc に追加してください。
現在使用しているシェルは、SHELL 環境変数の値を確認するか、現在のプロセス名を調べることで確認できます。ターミナルで次のコマンドを実行します:

```bash
echo $SHELL
```

そうすることで、使用しているシェルが bash か zsh かを確認できます。

```bash
if [ -f ~/.bashrc ]; then
    source ~/.bashrc
fi
```
zsh を使用している場合は、設定、エイリアス、および関数をホームディレクトリにある .zshrc ファイルに配置するようにしてください。ファイルが存在しない場合は、touch ~/.zshrc で作成できます。

## 設定
このリポジトリをクローンします

```
git clone https://github.com/Jer-B/Foundry_Simple_storage
cd Foundry_Simple_storage
```

## 使用方法
### Ganache を使用する場合
1. ganache ローカルチェーンを実行して、ganache アプリケーションで quickstart をクリックします。

> ワークスペースを保存します。これにより、次回 ganache を開いたときに作成したワークスペースを開始できます。それ以外の場合、以下の手順をすべて再度行う必要があります。

2. アカウントの一つで鍵をクリックし、表示される鍵をコピーして、.env ファイルに配置します。.env.example に示されている内容と同様です。以下のようになります。

PRIVATE_KEY_GANACHE=11ee3108a03081fe260ecdc106554d09d9d1209bcafd46942b10e02943effc4a

### Anvil を使用する場合
1. `.env.example` 内部にあるキーと RPC URL の情報を使用できます。

2. ソースコードをコンパイルします

```
forge compile
```

3. コントラクトをデプロイします

```
forge create --private-key <PRIVATE_KEY>
```
RPC を選択した対応するウォレットプライベートキー変数で <PRIVATE_KEY> を置き換えてください

## Windows、WSL、および Ganache を使用する場合
WSL を使用している場合、ganache UI では別のエンドポイントを使用する必要があります。これを修正するためのオプションが 4 つあります。

1. ganache UI で WSL エンドポイントを使用します（これは時々動作しないことがあります）
2. `anvil` を使用します


# テストネットへのデプロイ

 [metamask](https://metamask.io/) または他のウォレットがあることを確認し、プライベートキーをエクスポートします。
 
 **重要**
 
リアルな資金が含まれていない Metamask を使用してください。誤ってプライベートキーを公共の場所に公開してしまう可能性があるためです。開発中には、別の Metamask またはウォレットを使用することを強くお勧めします。

1. [プライベートキーをエクスポート](https://metamask.zendesk.com/hc/en-us/articles/360015289632-How-to-Export-an-Account-Private-Key) し、.env ファイルに配置します。上記のように行います。

2. [Alchemy](https://alchemy.com/?a=673c802981) に移動し、選択したテストネットの新しいプロジェクトを作成します（たとえば Sepolia）。

3. テストネットに関連する URL を取得し、.env ファイルに配置します。

4. [テストネット ETH](https://faucets.chain.link/) をアカウントに持っていることを確認してください。[こちらから取得できます](こちらから取得できます)。アルケミーでプロジェクトを作成したテストネットと同じテストネット用のテストネット ETH を取得する必要があります（たとえば、Goerli）。

5. 実行します

```
forge create --private-key <PRIVATE_KEY> --rpc-url <ALCHEMY_URL>
```

Or, you can use a deploy script!

```
forge script script/DeploySimpleStorage.s.sol --private-key <PRIVATE_KEY> --rpc-url <ALCHEMY_URL>
```
選択した RPC に対応するウォレットのプライベートキー変数で <PRIVATE_KEY> を置き換えてください。
