# Pump.Fun Bundler - Advanced Solana Token Launch & Trading Bot

**Pump.Fun Bundler** is a sophisticated TypeScript-based tool for creating, launching, and trading tokens on the Solana blockchain with advanced bundling capabilities, Pumpswap integration, and automated trading strategies.

## 🚀 Features

### Core Functionality
- **Token Creation & Launch**: Automated token creation with metadata upload to IPFS
- **Advanced Bundling**: Bundle multiple transactions for optimal execution
- **Pumpswap Integration**: Seamless integration with Pumpswap for enhanced trading
- **Jito MEV Protection**: Integration with Jito for MEV protection and optimal execution
- **Lookup Table Management**: Custom LUT program for optimized transaction strategies

### Trading Capabilities
- **Multi-Wallet Trading**: Support for up to 28 different keypair buyers
- **Automated Buy/Sell**: Complex percentage-based sell strategies across all keypairs
- **Anti-Bubble Maps**: Advanced strategies to prevent bubble formations
- **Supply Management**: Automatic supply deviation management for smooth launches

### User Experience
- **Intuitive CLI Interface**: User-friendly command-line interface with prompts
- **Profile Generation**: Automatic random profile creation for wallet authenticity
- **Real-time Monitoring**: Transaction simulation and monitoring capabilities
- **Error Handling**: Comprehensive error handling and recovery mechanisms

## 📋 Prerequisites

- Node.js (v16 or higher)
- TypeScript
- Solana CLI tools
- Access to Solana RPC endpoint
- Jito access for MEV protection

## 🛠️ Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/michalstefanow/solana-pumpFun-bundler.git
   cd solana-pumpFun-bundler
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Configure the project**
   - Update `config.ts` with your RPC endpoint and wallet keys
   - Place your token image in the `img/` directory
   - Ensure you have sufficient SOL for transactions

## ⚙️ Configuration

### Required Configuration (`config.ts`)
```typescript
// Wallet Configuration
export const wallet = Keypair.fromSecretKey(bs58.decode("YOUR_PRIVATE_KEY"));
export const payer = Keypair.fromSecretKey(bs58.decode("YOUR_PAYER_KEY"));

// RPC Configuration
export const rpc = "YOUR_RPC_ENDPOINT";

// Program IDs (Do not modify)
export const PUMP_PROGRAM = new PublicKey("6EF8rrecthR5Dkzon8Nwu78hRvfCKubJ14M5uBEwF6P");
export const RayLiqPoolv4 = new PublicKey('675kPX9MHTjS2zt1qfr1NYHuzeLXfQM9H24wFSUt1Mp8');
```

### Environment Setup
- Ensure your wallet has sufficient SOL for:
  - Token creation fees
  - Transaction fees
  - Jito tips
  - Associated token account creation

## 🎯 Usage

### 1. Token Creation and Launch
```bash
npm start
```
This will initiate the interactive token creation process:
- Token name, symbol, and description
- Social media links (Twitter, Telegram, Website)
- Jito tip amount
- Automatic metadata upload to IPFS

### 2. Advanced Features

#### Bundle Trading
The tool automatically creates bundles containing:
- Pool creation transaction
- Token metadata transaction
- Multiple buy transactions from 28 wallets
- Optimized for maximum efficiency

#### Sell Strategies
```typescript
// Percentage-based selling across all wallets
const supplyPercent = 1; // 1% of total supply
```

#### Lookup Table Management
- Automatic LUT creation and extension
- Optimized address resolution
- Reduced transaction sizes

## 📁 Project Structure

```
PumpFun-bundler/
├── src/
│   ├── clients/           # Client configurations
│   │   ├── jito.ts       # Jito MEV client
│   │   ├── config.ts     # Client configuration
│   │   └── LookupTableProvider.ts
│   ├── keypairs/         # Wallet keypairs
│   ├── jitoPool.ts       # Main bundling logic
│   ├── sellFunc.ts       # Selling functionality
│   ├── createLUT.ts      # Lookup table creation
│   ├── createKeys.ts     # Keypair generation
│   └── senderUI.ts       # User interface
├── img/                  # Token images
├── config.ts            # Main configuration
├── main.ts              # Entry point
├── package.json         # Dependencies
└── tsconfig.json        # TypeScript config
```

## 🔧 Key Components

### Core Modules
- **`jitoPool.ts`**: Main bundling and trading logic
- **`sellFunc.ts`**: Advanced selling strategies
- **`createLUT.ts`**: Lookup table management
- **`senderUI.ts`**: User interface and prompts

### Dependencies
- **@solana/web3.js**: Solana blockchain interaction
- **@coral-xyz/anchor**: Anchor framework integration
- **jito-ts**: MEV protection and bundling
- **@raydium-io/raydium-sdk**: Raydium DEX integration

## 🚨 Important Notes

### Security
- **Never share private keys**: Keep your private keys secure
- **Test on devnet first**: Always test with small amounts
- **Monitor transactions**: Use Solscan for transaction monitoring

### Limitations
- Maximum 25% supply sell per transaction (fraud protection)
- Transaction size limits (1232 bytes)
- RPC rate limiting considerations

### Best Practices
- Use reliable RPC endpoints
- Monitor gas fees and Jito tips
- Test thoroughly before mainnet deployment
- Keep sufficient SOL for all operations

## 📞 Support & Contact

For technical support, questions, or collaboration:
- **Telegram**: [@mooneagle1_1](https://t.me/mooneagle1_1)
- **Twitter**: [@michalstfanow](https://x.com/michalstefanow)

## 📄 License

This project is licensed under the ISC License.

## ⚠️ Disclaimer

This tool is for educational and development purposes. Users are responsible for:
- Understanding the risks of cryptocurrency trading
- Compliance with local regulations
- Proper testing before mainnet use
- Managing their own private keys and funds

## 🔄 Recent Updates

- **Pumpswap Integration**: Added seamless Pumpswap trading capabilities
- **Enhanced Bundling**: Improved transaction bundling efficiency
- **Better Error Handling**: Comprehensive error recovery mechanisms
- **UI Improvements**: Enhanced user interface and prompts

---

**Built with ❤️ for the Solana ecosystem**


