<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/d7ef9a12-fdab-4da7-a7fc-b17a77bd4c9f">

</p>
<h2>
<p align="center"> Powerloom </p>
<p align="center"> Powerloom is a consensus-backed data network protocol that enables builders to create verifiable data applications in Web3, offering flexible data markets with pre-computed APIs and validated datasets through lightweight, easily deployable nodes that ensure data integrity through cryptographic proofs </p>
</h2>

<p align="center">
  <a href="https://powerloom.io/">Home</a> |
  <a href="https://discord.com/invite/powerloom">Discord</a> |
  <a href="https://twitter.com/PowerloomHQ">Twitter</a> |
  <a href="https://docs.powerloom.io/">Docs</a> 
</p>


Minimum Hardware:

| OS | CPU | RAM | SSD |
|:---|:---|:---|:---|
| Ubuntu 22.04 | 4 | 8 | 400 GB |


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
### Update
~~~
git pull
~~~
~~~
./build.sh
~~~

