# School Supply Donations DApp

A decentralized application (DApp) for tracking and managing school supply donations, connecting donors with schools in need.

## Features

- School registration with location and needed supplies
- Donation tracking system
- Delivery status monitoring
- Donor history tracking
- Message system for donors
- Real-time updates
- Web3 wallet integration

## Tech Stack

- Solidity (Smart Contract)
- Web3.js
- HTML/JavaScript
- Tailwind CSS
- MetaMask (Web3 Provider)

## Prerequisites

- Node.js and npm installed
- MetaMask browser extension
- Web3-compatible browser
- Access to an Ethereum network (testnet or mainnet)

## Installation

1. Clone the repository:
```bash
git clone https://github.com/yourusername/school-supply-donations
cd school-supply-donations
```

2. Install dependencies:
```bash
npm install
```

3. Deploy the smart contract:
   - Compile the Solidity contract using Remix, Truffle, or Hardhat
   - Deploy to your chosen network
   - Save the deployed contract address

4. Configure the frontend:
   - Open `index.html`
   - Replace `YOUR_CONTRACT_ADDRESS` with your deployed contract address
   - Replace the `contractABI` array with your contract's ABI

## Smart Contract Structure

### Key Data Structures

```solidity
struct Donation {
    address donor;
    string itemName;
    uint256 quantity;
    string schoolName;
    string message;
    uint256 timestamp;
    bool isDelivered;
}

struct School {
    string name;
    string location;
    string[] needs;
    bool isRegistered;
}
```

### Main Functions

```solidity
function registerSchool(string memory name, string memory location, string[] memory initialNeeds) public
function makeDonation(string memory itemName, uint256 quantity, string memory schoolName, string memory message) public
function markDonationDelivered(uint256 donationId) public
function updateSchoolNeeds(string memory schoolName, string[] memory newNeeds) public
function getSchoolNeeds(string memory schoolName) public view returns (string[] memory)
function getDonorHistory(address donor) public view returns (uint256[] memory)
function getAllSchools() public view returns (string[] memory)
function getDonationDetails(uint256 donationId) public view returns (...)
```

## Usage

### Starting the Application

1. Start a local server:
```bash
npx http-server
```

2. Open your browser and navigate to `http://localhost:8080`

### Using the DApp

1. Connect Wallet:
   - Click "Connect Wallet" button
   - Approve MetaMask connection
   - Ensure correct network selection

2. Register a School:
   - Fill in school name and location
   - List needed supplies (comma-separated)
   - Click "Register School"
   - Confirm transaction in MetaMask

3. Make Donations:
   - Select a school from dropdown
   - Enter item name and quantity
   - Add optional message
   - Click "Make Donation"
   - Approve transaction

4. View Donations:
   - Recent donations appear in history section
   - Track delivery status
   - View donor information

## Frontend Components

1. Wallet Connection Section:
   - Connect/disconnect functionality
   - Address display
   - Network status

2. School Registration Form:
   - Name input
   - Location input
   - Needs list input
   - Submit button

3. Donation Form:
   - School selection
   - Item details
   - Quantity input
   - Message field
   - Submit button

4. Donation History Display:
   - Recent donations list
   - Delivery status
   - Donor information
   - Transaction details

## Security Features

1. School Registration:
   - Duplicate prevention
   - Validation checks

2. Donations:
   - School existence verification
   - Quantity validation
   - Delivery status tracking

3. Access Control:
   - Modifier for school verification
   - Transaction validation

## Testing

### Smart Contract Testing

1. Deploy to testnet:
```bash
truffle migrate --network ropsten
```

2. Test main functions:
```bash
truffle test
```

### Frontend Testing

1. Test wallet connection
2. Verify form submissions
3. Check transaction processing
4. Test data display
5. Verify error handling

## Troubleshooting

Common Issues:

1. MetaMask Connection:
   - Ensure MetaMask is installed
   - Check network selection
   - Verify account is unlocked

2. Transaction Failures:
   - Check gas price
   - Verify ETH balance
   - Confirm correct network

3. Data Loading Issues:
   - Check console for errors
   - Verify contract address
   - Confirm Web3 connection

## Contributing

1. Fork the repository
2. Create feature branch
3. Commit changes
4. Push to branch
5. Create Pull Request

## Development Roadmap

Future Features:
- School verification system
- Donation request system
- Supply matching algorithm
- Donor reputation system
- Automated delivery tracking
- Community feedback system

## License

This project is licensed under the MIT License.

## Support

For support:
- Open an issue on GitHub
- Join our Discord community
- Email: support@schoolsupplydonations.com

## Acknowledgments

- OpenZeppelin for security patterns
- Web3 community
- Contributing developers
- Educational institutions
