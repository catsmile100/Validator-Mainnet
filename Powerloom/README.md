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
- [DOCS](https://mint.powerloom.network/)

### Minimum Hardware 

#### LineNode
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 22.04 | 4         | 4 GB	         | 40 TB   | 


### Mint BFT
 - [MINT](https://mint.powerloom.network/)


### Install
~~~
sudo apt update && sudo apt upgrade -y
sudo apt install docker.io screen git
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
- SOURCE_RPC_URL: Use any Ethereum Mainnet RPC, such as Ankr, Infura, or Alchemy.
  SIGNER_ACCOUNT_ADDRESS: Utilize a burner wallet for the signer account address. Please DO NOT use your main/primary wallet.
- SIGNER_ACCOUNT_PRIVATE_KEY: Use the private key from your burner wallet.
