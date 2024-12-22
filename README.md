# Blockchain Library System

This is a **Blockchain-based Library Management System** built using Go (Golang). The project uses a **Proof of Work** mechanism to manage and verify book checkouts securely.

## Features

1. 📚 **Blockchain Implementation**:
   - Each book checkout is recorded as a block on the blockchain.
   - Ensures integrity and immutability of records.

2. 🛠️ **Genesis Block**:
   - The first block in the blockchain, marking the beginning of the chain.

3. 📖 **Book Management**:
   - Add new books to the system with details like title, author, ISBN, and publication date.

4. 🔒 **Checkout System**:
   - Users can checkout books, creating a block for each transaction.

5. ✅ **Blockchain Validation**:
   - Ensures the validity of each block based on hash verification and positional checks.

## Technologies Used

- 🐹 **Go (Golang)**: Core programming language.
- 🌐 **Mux Router**: HTTP request handling.
- 🔐 **SHA-256**: Hashing algorithm for block creation.
- 🆔 **MD5**: Used for generating unique book IDs.
- 📦 **JSON**: Data serialization for API requests and responses.

## Endpoints

### 1. 📂 Get the Blockchain
**URL**: `/`  
**Method**: `GET`

Retrieves the current state of the blockchain.

### 2. ➕ Add a New Block
**URL**: `/`  
**Method**: `POST`

Adds a new block to the blockchain for a book checkout. The request body must include:

```json
{
  "book_id": "string",
  "user": "string",
  "checkout_date": "string"
}
```

### 3. 📘 Add a New Book
**URL**: `/new`  
**Method**: `POST`

Adds a new book to the system. The request body must include:

```json
{
  "title": "string",
  "author": "string",
  "publish_date": "string",
  "isbn": "string"
}
```

## How to Run

### Prerequisites
- 🛠️ Go installed on your system.
- 🌍 Git for version control.

### Steps
1. 📥 Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-name>
   ```

2. ▶️ Run the application:
   ```bash
   go run main.go
   ```

3. 🌐 Access the API at `http://localhost:3000` using Postman or any HTTP client.

## How It Works

1. 🟢 **Genesis Block**:
   - The blockchain starts with a genesis block that contains no previous hash.

2. 🧱 **Block Creation**:
   - Each block contains the following:
     - `Pos`: Position of the block.
     - `Data`: Book checkout information.
     - `TimeStamp`: Time of block creation.
     - `Hash`: SHA-256 hash of the block data.
     - `PrevHash`: Hash of the previous block.

3. 🔍 **Block Validation**:
   - Each block is validated before being added to the chain, ensuring:
     - Hash integrity.
     - Correct positional order.
     - Matching previous hash.

## Example Request

### ➕ Add a New Block (Checkout Book)
**Request**:
```bash
POST / HTTP/1.1
Content-Type: application/json
{
  "book_id": "1234",
  "user": "John Doe",
  "checkout_date": "2024-12-22"
}
```

**Response**:
```json
{
  "message": "Block added successfully."
}
```

## Future Enhancements

1. 🔨 Implement Proof of Work (PoW) for mining blocks.
2. 👤 Add a user authentication system.
3. ⚠️ Introduce more robust error handling.
4. 💾 Enable persistent storage for the blockchain.

## License

This project is licensed under the MIT License.

---
Feel free to contribute to this project by creating pull requests or submitting issues!

