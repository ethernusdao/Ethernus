Ethernus-Ecosystem/
├── contracts/
│   ├── core/
│   │   ├── ETUS.sol
│   │   ├── ETUSManager.sol
│   │   ├── sETUS.sol
│   │   ├── SLAR.sol
│   │   ├── PriceBalancer.sol
│   │   ├── InsuranceFund.sol
│   │   └── governance/
│   │       ├── MultisigContract.sol
│   │       ├── DAOContract.sol
│   │       └── ...
│   ├── pools/
│   │   ├── DonationPool.sol
│   │   ├── AlliancePool.sol
│   │   ├── StakingPool.sol
│   │   └── ...
│   ├── vesting/
│   │   ├── VestingContractTeam.sol
│   │   └── ...
│   ├── libraries/
│   │   ├── SafeMath.sol
│   │   ├── HtVtCalculations.sol
│   │   └── ...
│   └── interfaces/
│       ├── IETUSManager.sol
│       ├── IPools.sol
│       └── ...
├── scripts/
│   ├── deploy/
│   │   ├── deploy-ETUSManager.js
│   │   ├── deploy-Pools.js
│   │   └── ...
│   ├── automation/
│   │   ├── priceBalancerBot.js
│   │   └── ...
│   └── ...
├── test/
│   ├── core/
│   │   ├── ETUS.test.js
│   │   ├── PriceBalancer.test.js
│   │   └── ...
│   ├── pools/
│   │   ├── DonationPool.test.js
│   │   └── ...
│   ├── vesting/
│   │   ├── VestingContractTeam.test.js
│   │   └── ...
│   └── ...
├── docs/
│   ├── whitepaper/
│   │   ├── whitepaper.md
│   │   └── images/
│   ├── tokenomics/
│   │   ├── etus-tokenomics.md
│   │   └── ...
│   ├── architecture/
│   │   ├── diagrams/
│   │   │   ├── Ethernus_Ecosystem.png
│   │   │   └── ...
│   │   └── architecture-overview.md
│   └── readme-images/
├── .github/
│   ├── workflows/
│   │   ├── ci.yml
│   │   ├── test.yml
│   │   └── ...
│   └── ISSUE_TEMPLATE.md
├── README.md
├── LICENSE
└── package.json
