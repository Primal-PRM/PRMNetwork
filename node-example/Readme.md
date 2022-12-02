# Run a PRM Validator
## Setting up a node
1. Git clone https://github.com/Primal-PRM/PRMNetwork.git

2. Copy source form node-example to root folder
```
cp -r PRMNetwork/node-example/PRM  /root/
```
3. Create an Account

```
cd /root/PRM
chmod +x openethereum
./openethereum account new --config nodes/validator/node.toml
```
Returned address like that 0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2

Copy result address to mode.toml
Ex:
```
...
[account]
unlock = ["0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"]
password = ["password"]

[mining]
force_sealing = true
engine_signer = "0x00aa39d30f0d20ff03a22ccfc30b7efbfca597c2"
reseal_on_txs = "none"
...
```
4. Run the authority nodes
```
./openethereum --config ./nodes/validator/node.toml

```
5. Stake

    Stake

    To stake PRM coin, all you should do is sending your PRM coin to the PRM Consensus contract address over the PRM network from the validator address.
    The PRM Consensus contract address: 0x849cb7e7929DFedd35F66a3F0445C4B7c035fB91
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to PRM and send the PRM coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /PRM/nodes/validator/keys/PRM/UTC--xxxx
    /PRM/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
