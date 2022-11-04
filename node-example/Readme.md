# Run a FAKT Validator
## Setting up a node
1. Git clone https://github.com/fkt20/FAKTNetwork.git

2. Copy source form node-example to root folder
```
cp -r FAKTNetwork/node-example/FAKT  /root/
```
3. Create an Account

```
cd /root/FAKT
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

    To stake FAKT coin, all you should do is sending your FAKT coin to the FAKT Consensus contract address over the FAKT network from the validator address.
    The FAKT Consensus contract address: 0x641dCb1B53966084Ca59dc9985a164D414ac1D28
    The easiest way to do so, is to import your private key or key-store file to your favourite wallet (for example Metamask), switch network to FAKT and send the FAKT coin to the Consensus contract address.

    You can find your key-store (containing your private key) and the password for the created account in:
    /FAKT/nodes/validator/keys/FAKT/UTC--xxxx
    /FAKT/nodes/validator/node.pwd

6. Wait for 1 cycle (approximately 48 hours).

    Wait until the next cycle gets started.
