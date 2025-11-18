
# 🧱Simple Python Blockchain

A minimal blockchain implementation in Python using Flask, SHA-256, and Proof of Work (PoW).
This project demonstrates the core concepts behind blockchain technology in the simplest possible way.




## ✨ FeaturesCreate a new blockchain with a genesis block

- Mine new blocks using Proof of Work (PoW)
- Validate the entire blockchain
- Expose blockchain functionality through REST API endpoints
- View the full chain in JSON format
## 🛠️ Tech Stack 
- Python 3
- Flask
- Hashlib
- Datetime
- JSON
## Folder Structure
```
Blockchain/
│── blockchain.py      # Main blockchain + Flask API
│── README.md          # Project documentation
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
## ▶️ Running the Project
1. Install dependencies
```
pip install flask
```
2. Run the blockchain
```
python blockchain.py
```
## 🚀 Future Enhancements
- Add transactions
- Add wallets & public/private keys
- Add decentralized nodes
- Add a consensus algorithm
- Add dynamic mining difficulty
