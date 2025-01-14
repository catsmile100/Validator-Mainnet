<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/b0bac1cd-13f5-494a-ae61-9a9818f67d3a">
</p>
</h2>
<p align="center"> Pactus </p>
<p align="center"> Pactus is an open-source layer-1 blockchain platform featuring Solid State Proof of Stake (SSPoS) consensus, focused on true decentralization through elimination of delegation and mining, while offering user-friendly GUI for node operation </p>
</h2>

<p align="center">
  <a href="https://pactus.org">Link</a> |
  <a href="https://discord.com/invite/H5vZkNnXCu">Discord</a> |
  <a href="https://twitter.com/pactuschain">Twitter</a> |
  <a href="https://pactus.org/user-guides">Docs</a> |
  <a href="https://pacscan.org">Explorer</a> 
</p>

### Minimum Hardware :
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 22.04 | 4          | 8         | 200 GB  | 

### Preparation
```
sudo apt update && apt upgrade -y
sudo apt install make clang pkg-config libssl-dev screen build-essential -y
```
### Download Binary
```
cd $HOME && \
LATEST=$(curl -s https://api.github.com/repos/pactus-project/pactus/releases/latest | grep "tag_name" | cut -d'"' -f4) && \
rm -rf node_pactus && \
wget https://github.com/pactus-project/pactus/releases/download/${LATEST}/pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
tar -xzf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
rm -rf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
mv pactus-cli_${LATEST#v} node_pactus && \
cd node_pactus
```

### Download Binary
```
sudo ./pactus-daemon init
```

### Run 
```
screen -S pactus
```
```
sudo ./pactus-daemon start
```

### Restore Wallet [If you already have a wallet before]
```
./pactus-daemon init --restore "<your-mnemonic>"
```
```
sudo ./pactus-daemon start
```
### Sett Validator Running
```
select / input : 1
```

### Wallet Seed 
```
./pactus-wallet seed
```

### List of Addresses
```
./pactus-wallet address all
```

### Get Address Balance
```
./pactus-wallet address balance <ADDRESS>
```

### Sending Bond / ReStake
```
./pactus-wallet tx bond <Reward address> <Validator address> <AMOUNT>
```

### Sending Transfer
```
./pactus-wallet tx transfer <sender address> <receiver address> <AMOUNT>
```

### UPDATE
```
screen -r pactus
cd $HOME && rm -rf node_pactus
```
Crl C
```
LATEST=$(curl -s https://api.github.com/repos/pactus-project/pactus/releases/latest | grep "tag_name" | cut -d'"' -f4) && \
rm -rf node_pactus && \
wget https://github.com/pactus-project/pactus/releases/download/${LATEST}/pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
tar -xzf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
rm -rf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
mv pactus-cli_${LATEST#v} node_pactus && \
cd node_pactus  && sudo ./pactus-daemon start
```
### MIGRATION
STOP OLD VPS PACTUS 
```
LATEST=$(curl -s https://api.github.com/repos/pactus-project/pactus/releases/latest | grep "tag_name" | cut -d'"' -f4) && \
rm -rf node_pactus && \
wget https://github.com/pactus-project/pactus/releases/download/${LATEST}/pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
tar -xzf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
rm -rf pactus-cli_${LATEST#v}_linux_amd64.tar.gz && \
mv pactus-cli_${LATEST#v} node_pactus && \
cd node_pactus  && sudo ./pactus-daemon start
```
Sett Validator Running : select / input : 1
