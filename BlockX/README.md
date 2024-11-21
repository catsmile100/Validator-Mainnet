<p align="center">
  <img height="350" height="350" src="https://github.com/catsmile100/Validor-Mainnet/assets/85368621/c663dab8-87f7-48b6-aa64-22f608530c5b">

</h2>
<p align="center"> BlockX </p>
<p align="center"> BlockX is a comprehensive Web3 ecosystem that combines Layer 1 blockchain, SupperWallet, and GPT Core to provide decentralized infrastructure for DePIN, AI, and Web3 applications. The project aims to revolutionize decentralized computing by offering secure asset management, GPU-as-a-Service, and venture studio support for building essential dApps in the Web3 space </p>
</h2>

<p align="center">
  <a href="https://www.blockxnet.com/">Home</a> |
  <a href="https://twitter.com/BlockXnet">Twitter</a> |
  <a href="https://ping.blockxnet.com/">Explorer</a> 
</p>

### Minimum Hardware :
OS  | CPU     | RAM      | SSD     | 
| ------------- | ------------- | ------------- | -------- |
| Ubuntu 22.04 | 4          | 8         | 400 GB  | 

### Setup Server
```
sudo apt update && apt upgrade -y
sudo apt install curl git jq lz4 build-essential unzip fail2ban ufw -y
```

### Set Firewall
```
sudo ufw default allow outgoing
sudo ufw default deny incoming
sudo ufw allow ssh
sudo ufw allow 9100
sudo ufw enable
```

### Install GO
```
ver="1.21.5"
wget "https://golang.org/dl/go$ver.linux-amd64.tar.gz"
sudo rm -rf /usr/local/go
sudo tar -C /usr/local -xzf "go$ver.linux-amd64.tar.gz"
rm "go$ver.linux-amd64.tar.gz"
echo "export PATH=$PATH:/usr/local/go/bin:$HOME/go/bin" >> $HOME/.bash_profile
source $HOME/.bash_profile
go version
```

### Node Installation
```
# Install blockx through repository
cd $HOME
rm -rf blockx
git clone https://github.com/BlockXLabs/BlockX-Genesis-Mainnet1 blockx
cd blockx
git checkout c940d186c0d118ea017f6abc00225fdd9b26fe14
make install
```

### Set Configuration for your node
```
blockxd config chain-id blockx_100-1
blockxd config keyring-backend file
```

### Init your node
```
# You can change "MyNode" to anything you like
blockxd init MyNode --chain-in blockx_100-1
```

### Add Genesis File and Addrbook
```
curl -Ls https://snapshots.indonode.net/blockx/genesis.json > $HOME/.blockxd/config/genesis.json
curl -Ls https://snapshots.indonode.net/blockx/addrbook.json > $HOME/.blockxd/config/addrbook.json

```

### Configure Seeds and Peers
```
PEERS="$(curl -sS https://rpc.blockx.indonode.net/net_info | jq -r '.result.peers[] | "(.node_info.id)@(.remote_ip):(.node_info.listen_addr)"' | awk -F ':' '{print $1":"$(NF)}' | sed -z 's|
|,|g;s|.$||')"
sed -i -e "s|^persistent_peers *=.*|persistent_peers = "$PEERS"|" $HOME/.blockxd/config/config.toml
```
### Set Pruning, Enable Prometheus, Gas Prices, and Indexer
```
PRUNING="custom"
PRUNING_KEEP_RECENT="100"
PRUNING_INTERVAL="19"

sed -i -e "s/^pruning *=.*/pruning = "$PRUNING"/" $HOME/.blockxd/config/app.toml
sed -i -e "s/^pruning-keep-recent *=.*/pruning-keep-recent = "$PRUNING_KEEP_RECENT"/" $HOME/.blockxd/config/app.toml
sed -i -e "s/^pruning-interval *=.*/pruning-interval = "$PRUNING_INTERVAL"/" $HOME/.blockxd/config/app.toml
sed -i 's|^prometheus *=.*|prometheus = true|' $HOME/.blockxd/config/config.toml
```

### Set Service file
```
sudo tee /etc/systemd/system/blockxd.service > /dev/null <<EOF
[Unit]
Description=blockx mainnet node
After=network-online.target
[Service]
User=$USER
ExecStart=$(which blockxd) start
Restart=always
RestartSec=3
LimitNOFILE=65535
[Install]
WantedBy=multi-user.target
EOF
sudo systemctl daemon-reload
sudo systemctl enable blockxd
```

### Set Custom Port
```
CUSTOM_PORT=13
sed -i.bak -e "s%^proxy_app = "tcp://127.0.0.1:26658"%proxy_app = "tcp://127.0.0.1:${CUSTOM_PORT}658"%; s%^laddr = "tcp://127.0.0.1:26657"%laddr = "tcp://127.0.0.1:${CUSTOM_PORT}657"%; s%^pprof_laddr = "localhost:6060"%pprof_laddr = "localhost:${CUSTOM_PORT}060"%; s%^laddr = "tcp://0.0.0.0:26656"%laddr = "tcp://0.0.0.0:${CUSTOM_PORT}656"%; s%^prometheus_listen_addr = ":26660"%prometheus_listen_addr = ":${CUSTOM_PORT}660"%" $HOME/.blockxd/config/config.toml
sed -i.bak -e "s%^address = "tcp://0.0.0.0:1317"%address = "tcp://0.0.0.0:${CUSTOM_PORT}317"%; s%^address = ":8080"%address = ":${CUSTOM_PORT}080"%; s%^address = "0.0.0.0:9090"%address = "0.0.0.0:${CUSTOM_PORT}090"%; s%^address = "0.0.0.0:9091"%address = "0.0.0.0:${CUSTOM_PORT}091"%; s%^address = "0.0.0.0:8545"%address = "0.0.0.0:${CUSTOM_PORT}545"%; s%^ws-address = "0.0.0.0:8546"%ws-address = "0.0.0.0:${CUSTOM_PORT}546"%" $HOME/.blockxd/config/app.toml
```
### Download Latest Snapshot
```
# Download Latest Snapshot
curl -L https://snapshots.indonode.net/blockx/blockx-latest.tar.lz4 | tar -Ilz4 -xf - -C $HOME/.blockxd
[[ -f $HOME/.blockxd/data/upgrade-info.json ]] && cp $HOME/.blockxd/data/upgrade-info.json $HOME/.blockxd/cosmovisor/genesis/upgrade-info.json
```
### RUN
```
sudo systemctl restart blockxd
sudo journalctl -fu blockxd -o cat
```

### Create Validator
```
blockxd tx staking create-validator \
  --amount "1000000abcx" \
  --pubkey $(blockxd tendermint show-validator) \
  --moniker "<MONIKER>" \
  --identity "" \
  --details "Indonode Guide" \
  --website "YOUR WEBSITE" \
  --chain-id blockx_100-1 \
  --commission-rate "0.01" \
  --commission-max-rate "0.2" \
  --commission-max-change-rate "0.01" \
  --min-self-delegation "1" \
  --gas-prices 0.025abcx \
  --gas "auto" \
  --gas-adjustment "1.5" \
  --from wallet \
  -y
```

### Unjail Validator
```
blockxd tx slashing unjail \
--chain-id blockx_100-1 \
--gas-prices 0.025abcx \
--gas-adjustment 1.5\
--gas "auto" \
--from wallet \
-y 
```
### Vote
```
blockxd tx gov vote 1 yes \
--from wallet \
--chain-id blockx_100-1 \
--gas-prices 0.025abcx \
--gas-adjustment 1.5 \
--gas "auto" \
-y 
```

### Cheat-Sheet
```
blockxd keys add wallet
```
```
blockxd keys add wallet --recover
```
```
blockxd keys list
```
```
blockxd keys delete wallet
```
```
blockxd q bank balances $(blockxd keys show wallet -a)
```
```
blockxd status 2>&1 | jq .SyncInfo.catching_up
```
```
sudo systemctl daemon-reload
```
```
sudo systemctl enable blockxd
```
```
sudo systemctl start blockxd
```
```
sudo systemctl stop blockxd
```
```
sudo systemctl restart blockxd
```
```
sudo systemctl status blockxd
```
```
sudo systemctl status blockxd
```
```
sudo journalctl -u blockxd -f --no-hostname -o cat
```
