Node modules install

$ npm install





Setup Geth

$ geth --datadir="./" account new
$ nano genesisblock.json

{
    "config": {
        "chainID"       : 10,
        "homesteadBlock": 0,
        "eip155Block":    0,
        "eip158Block":    0
    },
    "nonce": "0x01",
    "difficulty": "0x20000",
    "mixhash": "0x00000000000000000000000000000000000000647572616c65787365646c6578",
    "coinbase": "0x0000000000000000000000000000000000000000",
    "timestamp": "0x00",
    "parentHash": "0x0000000000000000000000000000000000000000000000000000000000000000",
    "extraData": "0x00",
    "gasLimit": "0x2FEFD8",
    "alloc": {
    }
}

$ geth --datadir="./" init genesisblock.json
$ geth --datadir="./" --networkid 23422  --rpc --rpccorsdomain="*" --rpcport="8545" --minerthreads="1" --mine --nodiscover --maxpeers=0 --unlock 0 console





Initialize IPFS

$ ipfs init
$ ipfs config --json API.HTTPHeaders.Access-Control-Allow-Origin '["*"]'
$ ipfs config --json Gateway.HTTPHeaders.Access-Control-Allow-Origin '["*"]'
$ ipfs daemon