# Charli3 Pull Oracle ODV Node Operator Backend (Enhanced Fork)

> [!NOTE]
> This repository is a specialized fork of the [Charli3-Official/charli3-pull-oracle-node](https://github.com/Charli3-Official/charli3-pull-oracle-node).

## 🚀 Quick Start

Please follow every steps to get the oracle nodes running in minutes, follow these exact steps:

1. **Install Dependencies**:
   ```bash
   poetry install
   ```

2. **Add Blockfrost Key**:
   Open `./configs/config-gold.yml` and `./configs/config-silver.yml`.
   Find the `ChainQuery.blockfrost.project_id` field and paste your [Blockfrost Preprod Project ID](https://blockfrost.io/):
   ```yaml
   ChainQuery:
     blockfrost:
       project_id: "your_preprod_project_id_here"
   ```
   *(Note: Price API keys and mnemonics are pre-filled for your convenience!)*

3. **Start the Nodes**:
   Open two separate terminals and run the following commands:

   **Terminal 1 (Gold Node):**
   ```bash
   poetry run python node/main.py run -c configs/config-gold.yml --port 8000
   ```

   **Terminal 2 (Silver Node):**
   ```bash
   poetry run python node/main.py run -c configs/config-silver.yml --port 8001
   ```

4. **Monitor Progress**:
   Check the terminal output to monitor price aggregation and transaction submission status.

---

## Key Changes in this Fork

- **Blockfrost Integration**: Eliminates the need for a local Ogmios/Kupo stack, making it easy to run anywhere with just an API key.
- **Aiken v3 Compliance**: Fully compatible with the latest Charli3 on-chain validators.
- **Dual-Asset Setup**: Pre-configured for simultaneous XAU/USD and XAG/USD aggregation.
- **Improved Stability**: Fixed key derivation issues and added diagnostic logging for smoother operations.

## Documentation
- [Original Project Documentation](https://charli3.io/)
- [Governance](./GOVERNANCE.md)
- [Maintainers](./MAINTAINERS.md)
- [Changelog](./CHANGELOG.md)

## License
MIT License. See [LICENSE](LICENSE) for details.
