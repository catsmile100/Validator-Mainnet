<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/d7ef9a12-fdab-4da7-a7fc-b17a77bd4c9f">

</p>
<h1>
<p align="center">  POWERLOOM </p>
</h1>

### Official
- [Site](https://powerloom.io/)
- [X](https://twitter.com/PowerloomHQ)
- [Discord](https://discord.com/invite/powerloom)
- [DOCS](https://docs.powerloom.io/)

### Minimum Hardware 

#### LineNode
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 22.04 | 4         | 4 GB	         | 40 GB   | 


### Register in *`Dasboard`*
- *`MINT NFT`: [MINT](https://mint.powerloom.network/)*
- *`Connect Wallet NFT `: [Dashboard](https://snapshotter-dashboard.powerloom.network/)*
- *`Input burner Wallet / wallet in node`*
- *`Bind Twitter`*
- *`Bind Discord`*
- *`KYC`*
### Update and Upgrade
~~~
sudo apt-get update && sudo apt-get upgrade -y
~~~
### Install Git
~~~
sudo apt-get install git -y
~~~
### Install Docker and Docker Compose
~~~
sudo apt-get update
sudo apt-get install ca-certificates curl 
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
~~~
~~~
echo \
"deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
$(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
~~~
### Docker repository
~~~
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
~~~
### Cloning the Repository
~~~
git clone https://github.com/PowerLoom/snapshotter-lite powerloom-testnet
~~~
~~~
cd powerloom-testnet
~~~
### Sett Screen
~~~
screen -S powerloom
~~~
### RUN
~~~
./build.sh
~~~
- *`SOURCE_RPC_URL`: Use any Ethereum Mainnet RPC, such as Ankr, Infura, or Alchemy*
- *`SIGNER_ACCOUNT_ADDRESS`: Utilize a burner wallet for the signer account address. Please DO NOT use your main/primary wallet*
- *`SIGNER_ACCOUNT_PRIVATE_KEY`: Use the private key from your burner wallet*
- *`SLOT_ID`: To assign your node to a specific slot, please provide the corresponding Slot ID or NFT ID. You can locate your NFT ID within your transaction details on PolygonScan*
### Detach
~~~
CTRL a + d
~~~
