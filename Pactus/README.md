<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/b0bac1cd-13f5-494a-ae61-9a9818f67d3a">
</p>
<h1>
<p align="center"> Pactus </p>
</h1>

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
sudo apt install tmux git curl -y
sudo apt install make clang pkg-config libssl-dev build-essential -y
```
### Download Binary
```
cd $HOME && rm -rf node_pactus && wget https://github.com/pactus-project/pactus/releases/download/v1.0.1/pactus-cli_1.0.1_linux_amd64.tar.gz && tar -xzf pactus-cli_1.0.1_linux_amd64.tar.gz && rm -rf pactus-cli_1.0.1_linux_amd64.tar.gz && mv pactus-cli_1.0.1 node_pactus && cd node_pactus
```

### Download Binary
```
sudo ./pactus-daemon init
```

### Run 
```
Screen -S pactus
```
```
sudo ./pactus-daemon start
```

### Restore Wallet 
```
./pactus-daemon init --restore "<your-mnemonic>"
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

### Sending Bond
```
./pactus-wallet tx bond <Reward address> <Validator address> <AMOUNT>
```

### Sending Transfer
```
./pactus-wallet tx transfer <sender address> <receiver address> <AMOUNT>
```
