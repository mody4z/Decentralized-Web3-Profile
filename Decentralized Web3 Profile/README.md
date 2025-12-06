# Decentralized Web3 Profile

A decentralized identity registry on Celo blockchain that allows users to create and manage their professional profiles on-chain.

## 🌟 Overview

This DApp enables users to create, update, and view professional profiles stored permanently on the Celo blockchain. Each profile contains a name, bio, and portfolio URL, creating a decentralized professional identity system.

## ✨ Features

- **Connect Wallet**: Seamless MetaMask integration with automatic Celo Mainnet switching
- **Create/Edit Profile**: Store your professional information on-chain
- **View Profile**: Display your blockchain-based profile
- **Search Profiles**: Look up other users' profiles by their wallet address
- **Decentralized Storage**: All data stored permanently on Celo blockchain
- **Modern UI**: Clean, responsive design with Tailwind CSS

## 🚀 Getting Started

### Prerequisites

- MetaMask browser extension installed
- Some CELO tokens for gas fees (available on Celo Mainnet)
- Modern web browser (Chrome, Firefox, Brave, Edge)

### Installation

1. **Deploy the Smart Contract**
   - Compile `ProfileChain.sol` using Remix IDE or Hardhat
   - Deploy to Celo Mainnet (Chain ID: 42220)
   - Copy the deployed contract address

2. **Configure the Frontend**
   - Open `index.html`
   - Replace `CONTRACT_ADDRESS` with your deployed contract address:
     ```javascript
     const CONTRACT_ADDRESS = "0xYourContractAddressHere";
     ```

3. **Launch the DApp**
   - Open `index.html` in your web browser
   - Click "Connect Wallet" to connect MetaMask
   - The app will automatically switch to Celo Mainnet

## 📖 Usage

### Connecting Your Wallet

1. Click the **"Connect Wallet"** button in the navbar
2. MetaMask will prompt you to connect
3. The app will automatically switch to Celo Mainnet (Chain ID: 42220)
4. Your address will appear in the navbar once connected

### Creating/Editing Your Profile

1. Navigate to **"Edit Profile"** from the navbar
2. Fill in your information:
   - **Name**: Your full name
   - **Bio**: A description about yourself
   - **Portfolio URL**: Link to your portfolio or website
3. Click **"Save Profile to Blockchain"**
4. Confirm the transaction in MetaMask
5. Wait for confirmation

### Viewing Your Profile

1. Navigate to **"View Profile"** from the navbar
2. Your profile will be loaded from the blockchain
3. If you haven't created a profile yet, you'll see a prompt to create one

### Searching for Other Profiles

1. Go to the **"Home"** section
2. Enter any Ethereum address in the search bar
3. Click **"Search"**
4. The profile will be displayed if it exists

## 🔧 Smart Contract

### ProfileChain.sol

**Main Functions:**

- `setProfile(string _name, string _bio, string _portfolioUrl)`: Create or update your profile
- `getProfile(address user)`: Retrieve a user's profile by address
- `getMyProfile()`: Get your own profile
- `hasProfile(address user)`: Check if a user has a profile

**Events:**

- `ProfileUpdated`: Emitted when a profile is created or updated

## 🛠️ Technology Stack

- **Frontend**: HTML5, Tailwind CSS, JavaScript
- **Blockchain**: Celo Mainnet (Chain ID: 42220)
- **Smart Contract**: Solidity ^0.8.0
- **Web3 Library**: Ethers.js v5.2
- **Wallet**: MetaMask

## 🌐 Celo Network Details

- **Network Name**: Celo Mainnet
- **Chain ID**: 42220 (0xA4EC)
- **RPC URL**: https://forno.celo.org
- **Block Explorer**: https://explorer.celo.org
- **Currency**: CELO

## 📝 Smart Contract Deployment

### Using Remix IDE

1. Open [Remix IDE](https://remix.ethereum.org/)
2. Create a new file `ProfileChain.sol` and paste the contract code
3. Compile with Solidity ^0.8.0
4. In the Deploy tab:
   - Select "Injected Provider - MetaMask"
   - Ensure MetaMask is connected to Celo Mainnet
   - Click "Deploy"
   - Confirm the transaction in MetaMask
5. Copy the deployed contract address

### Using Hardhat

```bash
# Install dependencies
npm install --save-dev hardhat @nomiclabs/hardhat-ethers ethers

# Create deployment script
npx hardhat run scripts/deploy.js --network celo
```

## 🔐 Security Considerations

- Always verify the contract address before interacting
- Keep your private keys secure
- Be cautious when connecting your wallet
- Review all transactions before confirming in MetaMask

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

## 📄 License

This project is licensed under the MIT License.

## 🔗 Resources

- [Celo Documentation](https://docs.celo.org/)
- [Ethers.js Documentation](https://docs.ethers.io/)
- [MetaMask Documentation](https://docs.metamask.io/)
- [Solidity Documentation](https://docs.soliditylang.org/)

## 📧 Support

For questions or support, please open an issue in the repository.

---

**Built with ❤️ on Celo Blockchain**
