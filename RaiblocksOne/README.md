<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/e1097346-f60e-4404-a74a-878a7557ceff">

</p>
<h1>
<p align="center"> RaiblocksOne </p>
</h1>

Documentation
> - [Link](https://raione.cc/)
> - [Discord](https://discord.com/invite/RRMh2s8ZWT)
> - [Github](https://github.com/raiblocksone/raione-vault)
> - [Explorer](https://explorer.raione.cc/)
> - [Dashboard](https://vault.raione.cc/accounts)
> - [Market](https://nanswap.com/)


Minimum Hardware :
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 20.04 | 2      | 4 GB       | 120 GB     | 


Installation

Update and Install Dependencies
```
apt update -y && apt upgrade -y && apt autoremove -y && apt install screen curl -y
```

Install Docker
```
apt install docker.io -y
```

Pull Images From Docker Hub
```
docker pull raiblocksone/raione:R1_V.02
```

Run Nodes Once To Get Settings File
```
docker run --restart=unless-stopped -d -p 7075:7075 -p 127.0.0.1:7076:7076 -p 127.0.0.1:7078:7078 -v /root/raiblocksone/:/root --name raione-node raiblocksone/raione:R1_V.02 
```
Stop Nodes 
```
docker stop raione-node
```
Enable Voting
```
sudo nano raiblocksone/Nano/config-node.toml
```
Edit config-node.toml [Copy this code at the top of file config-node.toml]
```
[node]
​
enable_voting = true
```

Change RPC Settings

change enable_control = true
```
sudo nano raiblocksone/Nano/config-rpc.toml
```

Restart Services
```
docker restart raione-node
```

Check Version
```
curl -g -d '{ "action": "version"}' 'localhost:7076'
```

Block Count [wait "unchecked" = 0]
```
curl -g -d '{ "action": "block_count"}' 'localhost:7076'
```

Create New Wallet ID
save %WALLET_ID
```
curl -g -d '{ "action": "wallet_create"}' 'localhost:7076'
```

Create New Wallet Account (Xro_)
```
curl -g -d '{ "action": "account_create", "wallet": "%WALLET_ID% "}' 'localhost:7076'
```
Backup SEED:
```
docker exec -it raione-node /bin/bash
```
```
/usr/bin/./nano_node --wallet_decrypt_unsafe --wallet=%YOUR_WALLLET_ID%
```

Import Wallet 
- Go to https://vault.raione.cc/accounts
- Select Setting
- Select Configure New Wallet
- Import Seed

Setting Representatives 
- Go to https://vault.raione.cc/accounts
- Select Setting
- Select Representatives
- Select Account to change to All current accounts
- Input New Representative same to your wallet account

Minimum 1 Xro for active
- Faucet : https://faucet-xro.codeblocklabs.com/index.php
- Faucet : https://monke42.tk/

Confirm in Discord if node is ready
