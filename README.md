# Solidity
First dapp in solidity


#### Lesson 1: Configuring google compute engine
https://www.youtube.com/watch?v=rmtsh7Q7sbE
https://gist.github.com/AlwaysBCoding/9ce09281e5e097ce8ab7add2602c2fc7

sudo apt-get install git  
sudo apt-get install nodejs  
sudo apt-get install tmux  
sudo apt-get install remote-atom  
curl -o /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate  
sudo chmod +x /usr/local/bin/rmate  
mv /usr/local/bin/rmate /usr/local/bin/ratom  

#### Configure tmux
nano .tmux.conf  
paste the following:  
set -g mouse on  

#### Tmux aid  
tmux new-session -n session1  
ctrlb+x -> kill panel  
" horizontal split, % vertical split  

#### Allow editing of a file in local atom
On local atom start server 
ratom test.txt   

#### More installing
sudo apt-get install -y build-essential  
wget -qO- https://deb.nodesource.com/setup_10.x | sudo -E bash -  
sudo apt-get install -y nodejs  
sudo npm install -g ganache-cli  

#### Run ganache https://github.com/trufflesuite/ganache-cli
ganache-cli

#### Switch screen and create new folder, we will work from there  
mkdir test  
cd test  
ratom package.json  

{  
  "dependencies": {  
    "web3": "0.17.0-alpha"  
  }  
}  

Then run the below to install dependency:  
npm install  

Then run node:  
node  

In the node console write:  
var Web3 = require("web3")  
var web3 = new Web3(new Web3.providers.HttpProvider("http://localhost:8545"))  
web3.eth.accounts  

// If web3.eth.accounts matches the accounts in your genache-cli screen, you are good to go  

### Lesson 2: Creating Ethereum Keypairs
mkdir eth-keypairs
ratom package.json  

{  
  "dependencies": {
    "web3": "0.17.0-alpha",
    "ethereumjs-util": "4.5.0"
  }
}  

npm install

node
var Web3 = require("web3")
> undefined
var web3 = new Web3


Private key is always 64 characters
Wallet address is 40 last characters of public key with 0x in front of it.
web3.sha("40 digits") to generate hashes. 

ratom keypairs.js  
  
var EthUtil = require("ethereumjs-util")  
  
var hexToBytes = function(hex) {  
  for (var bytes = [], c = 0; c < hex.length; c+=2)  
  bytes.push(parseInt(hex.substr(c, 2), 16));  
  return bytes;  
}  
  
var privateKeyToAddress = function(privateKey) {  
  return `0x${EthUtil.privateToAddress(hexToBytes(privateKey)).toString('hex')}`  
}  
  
console.log(privateKeyToAddress(process.argv[2]))  

Then run node keypairs.js "64bitstring", so
node keypairs.js 1234567890123456789012345678901234567890123456789012345678901234
