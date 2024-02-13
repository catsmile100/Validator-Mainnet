<h1 align="centre"> 

<p align="center">  
    
![powerloom](https://github.com/catsmile100/Validor-Mainnet/assets/85368621/d7ef9a12-fdab-4da7-a7fc-b17a77bd4c9f)

</p>

<p align="center">  POWERLOOM LITENODE </p>

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
### Install
~~~
sudo apt update && sudo apt upgrade -y
~~~
~~~
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
~~~
~~~
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
~~~
~~~
sudo apt-get update
~~~
~~~
sudo apt-get install docker-ce docker-ce-cli containerd.io
~~~
~~~
sudo docker --version
~~~
### Clone
~~~
git clone -b simulation_mode https://github.com/PowerLoom/snapshotter-lite powerloom
cd powerloom
~~~

### Settup & RUN

~~~
screen -S powerloom
./build.sh
~~~
- *`SOURCE_RPC_URL`: Use any Ethereum Mainnet RPC, such as Ankr, Infura, or Alchemy*
- *`SIGNER_ACCOUNT_ADDRESS`: Utilize a burner wallet for the signer account address. Please DO NOT use your main/primary wallet*
- *`SIGNER_ACCOUNT_PRIVATE_KEY`: Use the private key from your burner wallet*
