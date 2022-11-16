# Run a GBR Validator
## Setting up a node
1. Git clone https://github.com/parminderunited/GBRNetwork.git

2. Copy source form node-example to root folder
```
cp -r GBRNetwork/node-example/GBR  /root/
```
3. Create an Account

```
cd /root/GBR
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

    To stake GBR coin, all you should do is sending your GBR coin to the GBR Consensus contract address over the GBR network from the validator address.
    The GBR Consensus contract address: 0x5F3ef71c0deD2A0d354b8Ae9b0BA1fEd6F32aB64
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to GBR and send the GBR coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /GBR/nodes/validator/keys/GBR/UTC--xxxx
    /GBR/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
