# Fractls-DApp

Fractls is a decentralized application (DApp) designed to create and manage fractionalized NFTs (Non-Fungible Tokens). The platform allows artists to upload images, set prices, and mint an original NFT along with 9 fractionalized NFTs. Users can buy, trade, and assemble these fractional NFTs. The owner of all 9 fractions can claim the original NFT, adding a unique puzzle-like gaming interface to the NFT experience.

Fractls aims to bridge the gap between beginner artists and the current NFT space, providing a platform where everyone gets an equal opportunity.

## Technologies Used

- **Foundry**: For developing, testing, and deploying Solidity smart contracts.
- **Node.js**: JavaScript runtime environment.
- **MongoDB (Using Atlas)**: NoSQL database for storing data.
- **Pinata**: IPFS pinning service for storing NFT metadata.
- **Infura**: Ethereum infrastructure provider for interacting with the blockchain.
- **web3.js**: JavaScript library for interacting with the Ethereum blockchain.
- **MetaMask**: Browser extension for managing Ethereum wallets.
- **OpenZeppelin**: Framework for building secure smart contracts.
- **React.js**: JavaScript library for building user interfaces.
- **Solidity**: Programming language for writing smart contracts.

## Project Structure

```plaintext
Fractls-DApp/
├── client/ # React frontend application
│ ├── public/
│ ├── src/
│ │ ├── App.js # Main React component
│ │ ├── FractlsNFT.json # ABI of the deployed contract
│ │ ├── components/ # React components
│ │ └── ...
│ ├── .env # Environment variables for frontend
│ └── package.json # Frontend dependencies
├── contracts/ # Solidity smart contracts
│ └── FractlsNFT.sol # Main NFT contract
├── script/ # Deployment scripts
│ └── DeployFractls.s.sol # Script to deploy FractlsNFT contract
├── lib/ # Libraries
│ └── openzeppelin-contracts/ # OpenZeppelin contracts
├── server/ # Backend server
│ ├── routes/ # Express routes
│ ├── services/ # Service layer for business logic
│ ├── models/ # Mongoose models
│ └── index.js # Main server file
├── .env # Environment variables for backend
├── foundry.toml # Foundry configuration file
└── README.md # Project documentation

Setting Up the Development Environment

Prerequisites
Node.js and npm
Foundry
MetaMask browser extension
Infura account
Pinata account
MongoDB Atlas account

Installation Steps

Clone the repository:
git clone https://github.com/your-username/Fractls-DApp.git
cd Fractls-DApp

Install frontend dependencies:

cd client
npm install

Configure environment variables:

Create a .env file in the root directory and add the following:

INFURA_PROJECT_ID=your_infura_project_id
INTERMEDIARY_WALLET=your_intermediary_wallet_address
INITIAL_OWNER=your_initial_owner_address
PINATA_JWT=your_pinata_jwt
MONGODB_URI=your_mongodb_uri

Create a .env file in the client directory and add the following:

REACT_APP_INFURA_PROJECT_ID=your_infura_project_id
REACT_APP_CONTRACT_ADDRESS=your_contract_address

Install Foundry dependencies:

forge install OpenZeppelin/openzeppelin-contracts
forge install foundry-rs/forge-std --no-commit

Deploy the smart contract:

source .env && forge script script/DeployFractls.s.sol --rpc-url https://sepolia.infura.io/v3/$INFURA_PROJECT_ID --private-key $YOUR_PRIVATE_KEY --broadcast


Start the backend server:

cd server
node index.js

Start the frontend:

cd client
npm start

Usage
Connect MetaMask to the Sepolia network.
Navigate to the "Mint" page.
Upload an image and set the desired price.
Confirm the transaction in MetaMask.
Monitor the transaction on Etherscan.
Smart Contract
FractlsNFT.sol
The FractlsNFT contract is used to manage the minting and ownership of fractionalized NFTs. The contract allows for the creation of an original NFT and its fractional NFTs. Users can claim the original NFT if they own all the fractional NFTs.

Functions
constructor(address _intermediaryWallet, address initialOwner): Initializes the contract with the intermediary wallet and the initial owner.
createCollectible(string memory originalTokenURI, string[] memory fractionTokenURIs): Creates the original NFT and its fractions.
claimOriginal(uint256[] memory fractionIds): Claims the original NFT if all fractions are owned by the caller.
Contributing
Contributions are welcome! Please create a pull request with your changes.

License
This project is licensed under the MIT License.

