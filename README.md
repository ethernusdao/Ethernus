# Ethernus Ecosystem

Welcome to the **Ethernus Ecosystem** repository! This project aims to provide a modular and scalable framework for all core smart contracts and supporting scripts related to ETUS, sETUS, SLAR, pools (Donation, Alliance, Staking), the PriceBalancer mechanism, the InsuranceFund, and governance components (multisig or DAO). Below you will find an overview of the folder structure, how each component works, and guidelines on contributing and running tests.

---

## Repository Structure


### Overview of Each Folder

1. **`contracts/`**  
   - **`core/`**  
     - Holds the fundamental contracts such as `ETUS.sol`, `ETUSManager.sol`, `sETUS.sol`, `SLAR.sol`, `PriceBalancer.sol`, and `InsuranceFund.sol`.  
     - The `governance/` subdirectory contains contracts related to multisig or DAO governance (e.g., `MultisigContract.sol`, `DAOContract.sol`).  
   - **`pools/`**  
     - Contains the different pool contracts for Donation, Alliance, and Staking: `DonationPool.sol`, `AlliancePool.sol`, `StakingPool.sol`.  
   - **`vesting/`**  
     - Stores contracts for vesting logic, specifically `VestingContractTeam.sol` for the dynamic monthly release.  
   - **`libraries/`**  
     - Shared libraries (like `SafeMath.sol`, `HtVtCalculations.sol`, etc.).  
   - **`interfaces/`**  
     - Interface definitions (`IETUSManager.sol`, `IPools.sol`) to standardize contract interactions.

2. **`scripts/`**  
   - **`deploy/`**  
     - Deployment scripts (e.g., `deploy-ETUSManager.js`, `deploy-Pools.js`) using Hardhat or Truffle.  
   - **`automation/`**  
     - Contains off-chain automation or keeper scripts (e.g., `priceBalancerBot.js`) that monitor price or orchestrate routine tasks.  

3. **`test/`**  
   - **`core/`**, **`pools/`**, **`vesting/`**  
     - Unit/integration tests organized by contract category. For example, `ETUS.test.js`, `DonationPool.test.js`, `VestingContractTeam.test.js`.  

4. **`docs/`**  
   - **`whitepaper/`**  
     - The main whitepaper (`whitepaper.md` or PDF) plus images if needed.  
   - **`tokenomics/`**  
     - Documentation about ETUS tokenomics, distribution, vesting, etc.  
   - **`architecture/`**  
     - System architecture, diagrams, and overviews (`architecture-overview.md`, diagrams in `Ethernus_Ecosystem.png`).  
   - **`readme-images/`**  
     - Images used in the main `README.md` or other docs.  

5. **`.github/`**  
   - **`workflows/`**  
     - Continuous Integration (CI) files, for example `ci.yml` or `test.yml`.  
   - **`ISSUE_TEMPLATE.md`**  
     - Template for GitHub issues.  

6. **`README.md`** (root)  
   - An overview of the Ethernus Ecosystem, plus usage instructions, how to run tests, disclaimers, etc.

7. **`LICENSE`**  
   - Defines the project’s open-source license (e.g., MIT).

8. **`package.json`**  
   - Node.js dependencies if using Hardhat or Truffle.

---

## Getting Started

1. **Clone the repository**:
   ```bash
   git clone https://github.com/<your-org>/Ethernus-Ecosystem.git
   cd Ethernus-Ecosystem
