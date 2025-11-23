
# 🧱Simple Python Blockchain + Custom Cryptocurrency (Hadcoin)

A minimal blockchain implementation in Python using Flask, SHA-256, Proof of Work (PoW), and multiple decentralized nodes.
This project now includes Hadcoin, your own custom cryptocurrency running on a lightweight blockchain network with 3 interconnected nodes.



## ✨ FeaturesCreate a new blockchain with a genesis block

- Mine new blocks using Proof of Work (PoW)
- Validate the entire blockchain
- Expose blockchain functionality through REST API endpoints
- View the full chain in JSON format
- Decentralized node-to-node communication
- Register nodes & maintain a shared peer network
- Add & broadcast transactions
- Store nodes and transactions in JSON files
- Expose functionality through REST API endpoints

## 🪙 Hadcoin — Your Own Cryptocurrency
This project introduces Hadcoin, a basic cryptocurrency built on top of your Python blockchain.

##🔐 Smart Contract for Hadcoin (Solidity)
Hadcoin has also been implemented as a smart contract using Solidity — enabling deployment on Ethereum-based networks.

Contract Capabilities
- Mint initial token supply
- Record ownership balances
- Transfer tokens between accounts
- Emit events on each transaction

## 🛠️ Tech Stack 
- Python 3
- Flask
- Hashlib
- Datetime
- JSON
- Solidity

## Folder Structure
```
Blockchain/
│── blockchain
     |──blockchain.py  
│── README.md
|──Cryptocurrency          
     |──hadecoin.py
     |──hadecoin_node_5001.py
     |──hadecoin_node_5002.py
     |──hadecoin_node_5003.py
     |──nodes.json
     |──transaction.json
|──Smart Contract
     |──hadcoins_ico.sol


```
## 🧠 How It Works
1. Genesis Block

When the app starts, a first block ("genesis block") is created with:

- proof = 1
- previous_hash = "0"

2. Mining a Block

Mining uses a Proof-of-Work algorithm:
```
SHA256(new_proof² + previous_proof²)
```
A block is valid only if the hash begins with:
```
"0000"
```
3. Blockchain Validation

The chain is valid if:
- Each block's previous_hash matches the hash of the previous block
- The proof of each block satisfies the PoW rule

4.Transaction Handling
Transactions are added to transaction.json until a block is mined.

5.Node Decentralization
Each node:
- Registers other nodes
- Syncs blockchain through consensus
- Mines & broadcasts new blocks


## 📡 API Endpoints
➤ Mine a Block

GET /mine_block
Returns details of the newly mined block.

Example:
```
{
  "message": "Congratulations you just mined a Block!",
  "index": 2,
  "timestamp": "2025-11-18 12:00:00",
  "proof": 53321,
  "previous_hash": "abcd1234..."
}
```
➤ Get the Full Blockchain

GET /get_chain

Example:
```
{
  "chain": [...],
  "length": 2
}
```

🔸 1. Add a Transaction
POST /add_transaction

🔸 2. Mine a Block
GET /mine_block

🔸 3. Get the Full Chain
GET /get_chain

🔸 4. Connect Nodes
POST /connect_node

🔸 5. Replace Chain (Consensus)
GET /replace_chain

## ▶️ Running the Project
1. Install dependencies
```
pip install flask
pip install requests
```
2. Run the blockchain
```
python blockchain.py

```
3.Running all the nodes
```
python hadcoin_node_5001.py
python hadcoin_node_5002.py
python hadcoin_node_5003.py

```
## 🚀 Future Enhancements
- Digital wallet system
- Wallet address & private key generation
- Merkle trees for transactions
- Dynamic mining difficulty
- Web dashboard for real-time chain visualization
