# Ethernus Ecosystem

Welcome to the **Ethernus Ecosystem** repository! This project aims to provide a modular and scalable framework for all core smart contracts and supporting scripts related to ETUS, sETUS, SLAR, pools (Donation, Alliance, Staking), the PriceBalancer mechanism, the InsuranceFund, and governance components (multisig or DAO). Below you will find an overview of the folder structure, how each component works, and guidelines on contributing and running tests.

---

## Repository Structure


### Overview of Each Folder

1. **`contracts/`**  
   - **`core/`**: Fundamental contracts for the Ethernus ecosystem:
     - `ETUS.sol`, `ETUSManager.sol`, `sETUS.sol`, `SLAR.sol`: The main tokens and manager logic.
     - `PriceBalancer.sol`, `InsuranceFund.sol`: Mechanisms for stabilizing ETUS and handling reserves.
     - `governance/`: Contracts for multisig or DAO governance (e.g., `MultisigContract.sol`, `DAOContract.sol`).
   - **`pools/`**: Smart contracts for the various Pools (Donation, Alliance, Staking).
   - **`vesting/`**: Contracts handling vesting logic (like `VestingContractTeam.sol`).
   - **`libraries/`**: Shared libraries or utility code (e.g., `SafeMath.sol`, `HtVtCalculations.sol`).
   - **`interfaces/`**: Interface definitions used across the ecosystem (`IETUSManager.sol`, `IPools.sol`).

2. **`scripts/`**  
   - **`deploy/`**: Deployment scripts for each contract category (e.g., `deploy-ETUSManager.js`, `deploy-Pools.js`).  
   - **`automation/`**: Off-chain/automation scripts (like a price balancer bot), or code for chain keepers.

3. **`test/`**  
   - **`core/`**, **`pools/`**, **`vesting/`**: Unit and integration tests aligned with the contract structure.
   - Each subfolder corresponds to contracts in `contracts/core`, `contracts/pools`, `contracts/vesting`, etc.

4. **`docs/`**  
   - **`whitepaper/`**: The main whitepaper (`whitepaper.md` or PDF) plus any images.
   - **`tokenomics/`**: Detailed ETUS tokenomics documentation (`etus-tokenomics.md`) and related details.
   - **`architecture/`**: System architecture, diagrams, and overviews, e.g., `architecture-overview.md`.
   - **`readme-images/`**: Reference images for this `README.md` or other docs.

5. **`.github/`**  
   - **`workflows/`**: Files for continuous integration (CI) and testing pipelines, e.g., `ci.yml`, `test.yml`.
   - **`ISSUE_TEMPLATE.md`**: Template for bug reports, feature requests, etc.

6. **`README.md` (root)**  
   - Contains a quick summary of the Ethernus Ecosystem, plus usage instructions, how to run tests, disclaimers, etc.

7. **`LICENSE`**  
   - Defines the project’s open-source license (e.g., MIT).

8. **`package.json`**  
   - Dependencies for Node.js-based tooling (Hardhat, Truffle, or other).

---

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your-org>/Ethernus-Ecosystem.git
   cd Ethernus-Ecosystem

Install dependencies (example with Node + Hardhat):
npm install
# or
yarn install

Compile contracts:
npx hardhat compile

Run tests:
npx hardhat test
Test files are located in test/ with subdirectories matching the contracts folder structure.

Deployment:

Inside scripts/deploy/, you will find scripts like deploy-ETUSManager.js.
Example usage:
npx hardhat run scripts/deploy/deploy-ETUSManager.js --network mumbai

Adjust for your chosen network (mainnet, testnet, etc.).

Contributing
Issues: Feel free to open an issue for bugs or feature requests.
Pull Requests: Fork this repo, create a feature branch, and submit a PR to dev or main (depending on the workflow).
Testing: Please ensure new and modified contracts have test coverage in the test/ directory.
License
This repository is licensed under the MIT License. Please review the LICENSE file for details.
All contributions to this repo are assumed to be under the same license.

Roadmap and Documentation
Whitepaper: Detailed explanation of the Ethernus Ecosystem is in docs/whitepaper/whitepaper.md.
Tokenomics: For ETUS and the entire token distribution logic, see docs/tokenomics/etus-tokenomics.md.
Architecture: Diagrams and overviews in docs/architecture.
Security and Audits
Ethernus Ecosystem contracts are intended to undergo continuous audits and security reviews. All audit reports and community findings will be listed under docs/audits/ (if applicable). We encourage responsible disclosure and community feedback to keep the ecosystem robust.

Thank You!
Thank you for your interest in the Ethernus Ecosystem. We look forward to building a transparent, secure, and community-driven platform to ensure the stability and evolution of ETUS, sETUS, SLAR, and the entire DeFi environment surrounding them. If you have any questions or suggestions, please open an issue or start a discussion.

Ethernus Ecosystem – Empowering a stable, meritocratic, and antifragile community.
