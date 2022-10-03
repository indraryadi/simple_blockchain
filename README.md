# simple_blockchain

### run the service
#### node 1
python blockchain.py 5000

#### node 2
python blockchain.py 5001

### endpoint
- [GET]/blockchain        : to check all block on node

- [POST]/transaction/new  : to add new transaction that need to mine
format data in json     : {
    "amount": 10,
    "recipient": "8460674bba154801b5be179b533640a9",
    "sender": "0"
}

- [GET]/mine              : to mine the new transaction

- [POST]/nodes/add_nodes  : to add nodes to another nodes
format data in json     : {
        "nodes":[
            "http://127.0.0.1:5000"
        ]
}

- [GET]/nodes/sync        : to sync the node or update the node


#### simulation
node 1: add new transaction -> mine -> view the blockchain
node 2: view the blockchain

there will be different block between them 
    node 1: 2 blocks
    node 2: 1 block

to sync them:
node 1: add node 2 using /nodes/add_nodes
node 2: add node 1 using /nodes/add_nodes

node 1: sync the node 1 using /nodes/sync
node 2: sync the node 2 using /nodes/sync

result:
    node 1: 2 blocks
    node 2: 2 blocks

