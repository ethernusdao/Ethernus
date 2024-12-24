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
