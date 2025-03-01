<div align="center">
  <img src="/public/images/stakz.png" alt="Stakz" width="180"/>
  
  <h1>Stakz</h1>
  <p>DeFi-Powered Round-Up Investment Platform on Unichain</p>

  [![License: Proprietary](https://img.shields.io/badge/License-Proprietary-red.svg)](https://stakz.co/license)
  [![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue)](https://www.typescriptlang.org/)
  [![Astro](https://img.shields.io/badge/Astro-4.0-FF5D01.svg)](https://astro.build)
  [![TailwindCSS](https://img.shields.io/badge/Tailwind-3.0-38B2AC.svg)](https://tailwindcss.com)
  [![Unichain](https://img.shields.io/badge/Unichain-Powered-purple.svg)](https://unichain.org)
  [![DeFi](https://img.shields.io/badge/DeFi-Enabled-green.svg)](https://stakz.co)
</div>

## Overview

Stakz revolutionizes DeFi investing by leveraging Unichain's infrastructure to enable automated micro-investments through round-ups. Our platform bridges traditional banking with DeFi protocols, making cryptocurrency investment accessible through everyday transactions.

## Hackathon Implementations & Considerations

### Technical Excellence (50%)
- Smart contract architecture for gas-efficient round-up collection
- Integration with Unichain's DeFi protocols for yield optimization
- Automated portfolio rebalancing using Unichain's liquidity pools

### Innovation & Impact (20%)
- Novel approach to DeFi accessibility through micro-investments
- Seamless bridge between traditional banking and DeFi
- Unique yield optimization strategies

### Documentation & Presentation (20%)
- Comprehensive technical documentation
- Clear architecture diagrams
- Thorough testing instructions

### Ecosystem Potential (10%)
- Addresses mass adoption challenges in DeFi
- Scalable infrastructure for future expansion
- Community-driven governance potential

### Smart Contract Deployments

#### Portfolio Factory
- **Address**: `0x97a252079ad511f0d17ef13b0471291c1ccd6ac6` (deployed on Unichain testnet)
- **Features**:
  - Creates and manages portfolio tokens
  - Emergency shutdown capability
  - Pausable functionality
  - Reentrancy protection

#### Portfolio Tokens

1. **Foundation Portfolio (FOUND)**
- **Address**: `0x3268ebaaa4df63d9bcc43ea32aac1fa1a3cb35f2` (deployed on Unichain testnet)
   - Conservative allocation strategy
   - 80% BTC, 15% ETH, 5% SOL
   - Max deposit: 1000 ETH
   - Rate limit: 100 ETH/day

2. **Frontier Portfolio (FRONT)**
- **Address**: `0xf799fd70f16e98fcf0ee9b9efed0c83a7af60935` (deployed on Unichain testnet)
   - Balanced DeFi exposure
   - Equal allocation across LINK, UNI, AAVE, ONDO, VIRTUALS
   - Max deposit: 1000 ETH
   - Rate limit: 100 ETH/day

3. **Moonshots Portfolio (MOON)**
- **Address**: `0xbc43484ec8f80835de127f38bb21212068194535` (deployed on Unichain testnet)
   - High-risk, high-reward strategy
   - Equal allocation across DOGE, SHIB, PEPE, BONK, WIF
   - Max deposit: 1000 ETH
   - Rate limit: 100 ETH/day

### Contract Security Features
- Reentrancy protection
- Rate limiting
- Maximum deposit caps
- Emergency withdrawal mechanism
- Pausable functionality
- Owner-controlled distribution
- Secure withdrawal patterns

## Architecture

<div align="center">
  <img src="/public/images/arch.png" alt="Arch" width="180"/>
</div>

Our architecture combines traditional banking integration with DeFi protocols through a unique round-up system:

1. **Banking Layer**: 
   - Connects to user bank accounts via Plaid
   - Monitors transactions in real-time
   - Calculates round-up amounts

2. **Smart Contract Layer**:
   - Gas-optimized round-up collection contract
   - Automated market maker (AMM) integration
   - Yield farming strategy contracts

3. **Unichain Integration**:
   - Direct protocol interaction for optimal gas usage
   - Automated liquidity provision
   - Yield optimization across multiple protocols

4. **User Interface**:
   - Real-time portfolio tracking
   - Strategy customization
   - Transaction monitoring

The system automatically converts round-ups into DeFi positions, maximizing returns while minimizing gas costs through batched transactions and optimal routing.

## Key Features

- 🏦 **DeFi Integration**: Direct integration with Unichain's DeFi protocols
- 💰 **Smart Round-Ups**: Automated spare change allocation from everyday purchases
- 🔐 **Gas-Efficient**: Optimized transactions using Unichain's infrastructure
- 📊 **DeFi Portfolio Management**: Automated yield farming and liquidity provision
- 🔄 **Real-Time Processing**: Instant transaction monitoring and execution

## Architecture

### System Overview

<div align="center">
  <img src="/public/images/arch.png" alt="Architecture" width="180"/>
</div>
  
## Technical Infrastructure

### Core Components

#### Frontend & Backend Architecture
- **Framework**: Astro with React islands
- **Styling**: TailwindCSS with custom design system
- **State Management**: Wagmi, Viem, Zustand
- **Performance**: 
  - 98+ Lighthouse score
  - <3s Time to Interactive
  - Optimized asset delivery
- **Network**: Unichain
- **Node Providers**: Infura/Alchemy
- **Frontend Hosting**: Vercel
- **Backend Services**: Supabase
- **Database**: PostgreSQL

### Security Architecture

#### Data Protection
- 🔑 **Time-locks**: Upgrades and parameter changes with delay
- 🛡️ **Automated Testing**: Extensive coverage with Foundry and Hardhat

## Development Setup

### Prerequisites
node >= 18.0.0
pnpm >= 8.0.0
foundry >= 0.2.0
hardhat >= 2.19.0

#### Smart Contracts
- **Network**: Unichain Testnet/Mainnet
- **Standards**: ERC20, ERC4626
- **Key Contracts**:
  ```solidity
  // Portfolio Factory manages the creation and oversight of all portfolio tokens
  contract PortfolioFactory is Ownable {
      address[] public portfolios;
      uint256 public constant MAX_PORTFOLIO_TYPE = 2;
      // ... (see full implementation)
  }

  // Individual portfolio tokens with specific investment strategies
  contract PortfolioToken is ERC20, Ownable, ReentrancyGuard {
      enum PortfolioType { FOUNDATION, FRONTIER, MOONSHOTS }
      uint256 public constant MAX_DEPOSIT = 1000 ether;
      uint256 public constant RATE_LIMIT_DURATION = 1 days;
      // ... (see full implementation)
  }
  ```
- **Features**:
  - Gas-optimized round-up collection
  - Automated yield farming
  - Liquidity provision
  - Portfolio rebalancing

## Deployment

### Infrastructure as Code
- Smart Contract configurations in `/contracts`
- Deployment scripts in `/script`
- Contract verification in `/verify`

## Monitoring & Observability

### Metrics
- Smart contract monitoring via Tenderly
- Custom business metrics dashboard
- Real-time alerting via Defender
- Error tracking via Sentry

### Logging
- On-chain event indexing with The Graph
- Log retention and analysis
- Audit trail for all operations
- Performance profiling

### Code Quality
- ESLint configuration
- Prettier formatting
- Jest test suite
- GitHub Actions CI/CD

## Support & Community

### Documentation
- 📚 [Technical Documentation](https://docs.stakz.co)
- 🎓 [Smart Contract References](https://docs.stakz.co/contracts)
- 📖 [User Guides](https://docs.stakz.co/guides)

### Community
- 💬 [Discord Server](https://discord.gg/)
- 🐦 [Twitter Updates](https://twitter.com/)
- 📧 [Email Support](mailto:support@stakz.co)

## Roadmap

### Q2 2025
- [ ] Enhanced Round-Ups customization
- [ ] Additional DeFi protocol integrations
- [ ] Mobile app beta release

### Q3 2025
- [ ] Advanced portfolio analytics
- [ ] Cross-chain expansion
- [ ] Fiat on/off ramp improvements
- [ ] DAO governance implementation

## License

This software is proprietary and confidential. Unauthorized copying, modification, distribution, or use of this software, via any medium, is strictly prohibited. All rights reserved.

Copyright © 2025 Stakz. All rights reserved.

This software is the intellectual property of Stakz and is protected by applicable copyright laws. The software is provided under a proprietary license agreement and may only be used in accordance with the terms of that agreement.

For licensing inquiries, please contact licensing@stakz.co

---

<div align="center">
  <p>Built with ❤️ by the Stakz team</p>
  
  [![Follow on Twitter](https://img.shields.io/twitter/follow/stakzHQ?style=social)](https://twitter.com/stakzHQ)
  [![Join our Discord](https://img.shields.io/discord/1234567890?color=7289da&label=discord)](https://discord.gg/stakz)
</div>
