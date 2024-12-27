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
