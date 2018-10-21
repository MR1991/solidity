# Solidity
First dapp in solidity


# Configuring google compute engine
https://www.youtube.com/watch?v=rmtsh7Q7sbE
https://gist.github.com/AlwaysBCoding/9ce09281e5e097ce8ab7add2602c2fc7

sudo apt-get install git  
sudo apt-get install nodejs  
sudo apt-get install tmux  
sudo apt-get install remote-atom  
curl -o /usr/local/bin/rmate https://raw.githubusercontent.com/aurora/rmate/master/rmate  
sudo chmod +x /usr/local/bin/rmate  
mv /usr/local/bin/rmate /usr/local/bin/ratom  

nano .tmux.conf  
paste the following:  
set -g mouse on  

### Allow editing of a file in local atom  
ratom test.txt   

### Tmux aid  
tmux new-session -n session1  
ctrlb+x -> kill panel  
" horizontal split, % vertical split  

sudo apt-get install -y build-essential
wget -qO- https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt-get install -y nodejs
sudo npm install -g ganache-cli
### Ganache github:
https://github.com/trufflesuite/ganache-cli

### Run ganache
ganache-cli


### Switch screen and create new folder, we will work from there  
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


// If web3.eth.accounts matches the accounts in your testrpc, you are good to go
