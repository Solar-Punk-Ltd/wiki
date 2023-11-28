# Bee with testnet

## Developer solution (Go):

- Download from https://github.com/ethersphere/bee (Not the release)
- Open bee/cmd/bee
- Run: `go run . start printconfig`
- Copy-paste the content to a new file and save as `bee-testnet.yaml`
- Modify this raws:
    ```
    block-time: "15"
    blockchain-rpc-endpoint: "https://ethereum-sepolia.publicnode.com"
    bootnode: ['/dnsaddr/testnet.ethswarm.org']
    config: bee-testnet.yaml
    data-dir: ~/.bee-testnet
    mainnet: false
    network-id: "10"
    password: <your password> //not necessary, but its more comfortable when you don’t need it type in always
    ```
- Save the `bee-testnet.yaml` to `bee/cmd/bee`
- `go run . start --debug-api-enable --config bee-testnet.yaml --cors-allowed-origins="*"`

Check it with swarm-cli status or run bee-dashboard

## General solution:

Goerli testnet not working properly, not connecting to other peers. Sepolia only working in the current development version.

- Download Bee
- Make it executable (`chmod -x && open -a`)
- Change the config file as mentioned above, save it
    ```
    ./bee start --debug-api-enable --config bee-testnet.yaml --cors-allowed-origins="*"
    ```

- Be aware of the naming and placing of config files and data-dir. When changing the config file new overlay address is generated, so data-dir should be backuped and deleted, otherwise bee will hangup with overlay address mismatch.

- Get Sepolia testnet faucet: 
    - https://infura.io
    - https://sepolia-faucet.pk910.de/ (mining)