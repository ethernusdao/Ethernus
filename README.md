# Ethernus - Official Repository

Welcome to **Ethernus**! This `README.md` file consolidates all the information needed for developers to understand the repository structure, naming conventions, GitHub workflow, best practices, contribution guidelines, testing and coverage procedures, deployment steps, environment configuration, integrated tools, as well as license and support details.

---

## Table of Contents

1. [Notes](#notes)  
2. [Folder Structure](#folder-structure)  
3. [Naming Conventions](#naming-conventions)  
4. [Git Workflow](#git-workflow)  
5. [Best Practices](#best-practices)  
6. [Contribution Guide](#contribution-guide)  
7. [Tests and Coverage](#tests-and-coverage)  
8. [Deployment Procedures](#deployment-procedures)  
9. [Environment Setup](#environment-setup)  
10. [Integrated Tools](#integrated-tools)  
11. [License](#license)  
12. [Contact and Support](#contact-and-support)

---

## Notes

This **Ethernus** repository is exclusively focused on developing the ecosystem built around the ETUS token, its price stabilization mechanism (PriceBalancer), engagement pools (DonationPool, AlliancePool, StakingPool), dynamic vesting (Team Founders and Marketing/Development funds), and gradual governance (multisig/DAO).

- **Scope**: All Ethernus-related work is kept here. The “Solares” project will have a separate repository.  
- **Modular Organization**: The approach is divided by contracts and folders to facilitate maintenance, testing, and scalability.  
- **Roadmap Compliance**: Development is prioritized according to essential phases (fundamental contracts, pools, and later, full governance).

---

## Folder Structure

Below is the main directory architecture of the **Ethernus** repository:

```text
Ethernus/
├─ .github/
│   ├─ workflows/
│   │   ├─ test-and-deploy.yml        # CI/CD pipeline for tests and deployment
│   │   └─ lint-check.yml            # Style/lint validation
│   └─ ISSUE_TEMPLATE.md             # Issue template
│
├─ contracts/
│   ├─ core/
│   │   ├─ ETUSManager.sol           # Facade contract for handling ETUS
│   │   ├─ PriceBalancer.sol         # Price stability logic (~US$0.10)
│   │   ├─ InsuranceFund.sol         # Countercyclical fund (optional)
│   │   └─ ...
│   ├─ vesting/
│   │   ├─ VestingContractTeam.sol   # Dynamic vesting for the team
│   │   ├─ AirdropPool.sol           # Evolutionary distribution
│   │   ├─ DevMarketingFund.sol      # Development/Marketing fund
│   │   └─ ...
│   ├─ pools/
│   │   ├─ DonationPool.sol          # ETUS donation pool
│   │   ├─ AlliancePool.sol          # sETUS alliance pool
│   │   └─ StakingPool.sol           # Staking sETUS → SLAR
│   ├─ governance/
│   │   ├─ MultisigHelper.sol        # Multisig integrations
│   │   ├─ GovernanceToken.sol       # Governance token (if applicable)
│   │   └─ GovernorContract.sol      # On-chain governance contract
│   └─ tokens/
│       ├─ ETUS.sol                  # Reference to the ETUS token (immutable)
│       ├─ sETUS.sol                 # Intermediate token
│       └─ SLAR.sol                  # Final token (if part of governance)
│
├─ scripts/
│   ├─ deploy/
│   │   ├─ deployETUSManager.js      # Deployment scripts
│   │   ├─ deployPools.js
│   │   ├─ deployPriceBalancer.js
│   │   └─ ...
│   ├─ maintenance/
│   │   ├─ updatePriceOracle.js
│   │   ├─ pauseContracts.js
│   │   └─ ...
│   └─ utils/
│       ├─ generatePoolConfig.js
│       └─ ...
│
├─ test/
│   ├─ core/
│   │   ├─ ETUSManager.test.js
│   │   ├─ PriceBalancer.test.js
│   │   └─ InsuranceFund.test.js
│   ├─ vesting/
│   │   ├─ VestingContractTeam.test.js
│   │   └─ AirdropPool.test.js
│   ├─ pools/
│   │   ├─ DonationPool.test.js
│   │   ├─ AlliancePool.test.js
│   │   └─ StakingPool.test.js
│   ├─ governance/
│   │   ├─ Multisig.test.js
│   │   └─ GovernorContract.test.js
│   └─ tokens/
│       ├─ sETUS.test.js
│       └─ SLAR.test.js
│
├─ docs/
│   ├─ whitepaper/
│   ├─ tokenomics/
│   ├─ architecture/
│   ├─ roadmap/
│   └─ README.md
│
├─ config/
│   ├─ .solhint.json
│   ├─ .prettierrc
│   ├─ networks.config.js
│   └─ environment.sample
│
├─ .env.example
├─ README.md                         # <--- THIS FILE
├─ CONTRIBUTING.md
└─ LICENSE
```

### Notes:
- `contracts/core/`: Essential contracts like `ETUSManager` and `PriceBalancer`.
- `contracts/vesting/`: Vesting and specific funds (team, airdrop, marketing).
- `contracts/pools/`: Donation, alliance, and staking pools.
- `contracts/governance/`: Multisig scripts and on-chain governance.
- `contracts/tokens/`: Deals with `ETUS`, `sETUS`, `SLAR` (if applicable).
- Deployment scripts: `scripts/deploy/`, maintenance scripts: `scripts/maintenance/`.

---

## Naming Conventions

### Branches

- `main`: Stable version of the project.  
- `dev`: Main development branch.  
- `feature/feature-name`: One branch per feature or significant change.  
- `release/x.x.x`: Branches for release preparation (e.g., `release/1.0.0`).  

### Commits

- **Recommended format**: `type: brief description.`
- **Common types**: `feat` (feature), `fix` (bug fix), `docs` (documentation), `test` (tests), `refactor` (code refactor), `chore` (maintenance tasks).
- **Example**: `feat: implement PriceBalancer logic for buyback`

### Contracts

- PascalCase for Solidity files (e.g., `ETUSManager.sol`, `PriceBalancer.sol`).
- Use camelCase for variables/functions inside Solidity.

### Tests

- File name mirrors the contract name: `ContractName.test.js` (or `.ts`).
- Directory structure matches contracts.

### Scripts

- Use kebab-case describing the purpose, e.g., `deploy-price-balancer.js`.

---

## Git Workflow

### Branch Creation

Start from `dev`:

```bash
git checkout dev
git checkout -b feature/my-feature
```

### Development

- Implement the feature, make atomic commits (`feat: ...`, `fix: ...`).

### Pull Request

1. Open a PR from `feature/my-feature` → `dev`.
2. CI (test + lint) runs automatically.
3. Wait for reviews and approvals (at least 1 or 2, as defined by the team).

### Merge

- After approval, merge to `dev`.
- For releases, merge `dev` into `release/x.x.x`, finalize testing, then merge into `main`.

### Version Tags

At the end of the release process, create version tags like `v1.0.0` on `main`.

---

## Best Practices

### Frequent Testing

- Keep high coverage. Each module/contract should have its own test files.
- Ideally run `npm run test` before each significant commit.

### NatSpec Code Documentation

- For public functions or relevant events, use `@notice`, `@dev`, `@param`, etc., to clarify logic.

### Security

- Check function access with `Ownable` or `AccessControl`.
- Avoid duplicated logic; rely on libraries (OpenZeppelin).
- Use `require` to validate critical parameters.

### Pausable

- Critical contracts may implement a `pause()/unpause()` function via OpenZeppelin’s `Pausable` for emergencies.

### Small Commits

- Multiple smaller, well-described commits are preferred over one massive commit with unclear changes.

---

## Contribution Guide

1. Fork the repository or create a new local branch off `dev`.
2. Implement & Test locally:

```bash
npm install
npm run test
```

3. Lint: Ensure code adheres to `.solhint.json` and `.prettierrc`.
4. Open a PR: Provide a clear description, include test evidence.
5. Review & Discussion: Address feedback, push changes if needed.
6. Finalize: After approval, the team or author merges into `dev`.

Refer to `CONTRIBUTING.md` for more details.

---

## Tests and Coverage

### Frameworks

Typically `Hardhat`, `Truffle`, or `Foundry`. Check `package.json` and `hardhat.config.js` (or `foundry.toml`) to confirm.

### Running Tests

```bash
npm run test
```

or

```bash
yarn test
```

- Ensure all tests pass successfully.

### Coverage

- Use `npm run coverage` if configured.
- Aim for at least ~90% coverage on critical contracts (`ETUSManager`, `PriceBalancer`, etc.).

---

## Deployment Procedures

### Network Configuration

- Edit `config/networks.config.js` (or `.env`) to set credentials (`PRIVATE_KEY`, `RPC_URL`, etc.).

### Run Deploy Scripts

- Located in `scripts/deploy/`. Example:

```bash
node scripts/deploy/deployETUSManager.js --network mumbai
```

### Post-Deploy

- Update address references in `docs/architecture/` or `docs/roadmap/`.
- Configure initial parameters (e.g., calling `setPriceOracle`).

### Note

- Automatic deployments may be configured in `.github/workflows/test-and-deploy.yml`.

---

## Environment Setup

### Initial Installation

- Clone the repo and run `npm install` or `yarn install`.

### Env Variables

- Create a `.env` file from `.env.example`.
- Define: `PRIVATE_KEY`, `RPC_URL`, etc.

### Config

- The `config/` folder includes linting (`.solhint.json`) and network setups (`networks.config.js`).
- Adjust to match your target network or linting preferences.

---

## Integrated Tools

- **CI/CD via GitHub Actions**:
  - `test-and-deploy.yml`: Automatically runs tests and can deploy to staging/testnet.
  - `lint-check.yml`: Checks code formatting and style.
- **Solhint / ESLint**:
  - Linting for Solidity (`.solhint.json`) and JavaScript/TypeScript code (`.eslintrc`).
- **OpenZeppelin**:
  - Base library for tokens, `Ownable`, `Pausable`, etc.
- **Chainlink or Pyth (optional)**:
  - Price oracles for the `PriceBalancer` logic.

---

## License

This Ethernus project is licensed under the terms described in the `LICENSE`. Any usage or contribution must comply with those terms.

---

## Contact and Support

- **GitHub Issues**: For questions (`question` label), bugs (`bug` label), or proposals (`proposal` label).
- **Urgent Matters**: Contact the core team via internal channels (Slack/Discord/Email).
- **Maintenance**: Whenever possible, open an Issue first and discuss before submitting large Pull Requests.

**Ethernus Team – Building a top-tier blockchain ecosystem, one step at a time.**
