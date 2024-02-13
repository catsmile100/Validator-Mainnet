<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/e3c63ce4-b222-4daa-9bcf-0754decf41c7">

</p>
<h1>
<p align="center"> Massa </p>
</h1>

### Documentation
> - [Site](https://massa.net/)
> - [X](https://twitter.com/massalabs)
> - [Discord](https://discord.com/invite/massa)
> - [Docs](https://docs.massa.net/docs/node/install)
> - [Explorer](https://explorer.massa.net/)

### Minimum Hardware :
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 22.04 | 4          | 8         | 400 GB  | 

### Install Dependencies
```
sudo apt update
sudo apt upgrade
```
### Install  Binary
```
wget https://github.com/massalabs/massa/releases/download/MAIN.2.1/massa_MAIN.2.1_release_linux.tar.gz
tar -xvf massa_MAIN.2.1_release_linux.tar.gz
cd massa-node
```
### Node Configuration
```
nano config/config.toml
```
### Open Port
```
sudo ufw allow 31244
sudo ufw allow 31245
```
### Start Massa Node
```
./massa-node start
```
### Check Node Status:
```
./massa-node status
```
### Configuring Massa Client
```
nano massa-client/config/config.toml
```
### Generate a Key Pair
```
./massa-client generate-keypair
```
### Buy Rolls
```
./massa-client buy-rolls --amount <amount> --payment <payment_address> --staking <staking_key_file>
```
### List Owned Rolls:
```
./massa-client list-rolls
```
### Sell Rolls
```
./massa-client sell-rolls --amount <amount> --payment <payment_address> --staking <staking_key_file>
```
