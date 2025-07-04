# LiteEth Cores

## Quick Start

### Prerequisites
- WSL Ubuntu on Windows 11 (tested)
- Python 3.6+
- Git

### Setup & Generate Cores
```bash
# Run setup (installs dependencies + generates all cores + setup SRAM instances)
source setup.sh
```

This automatically:
1. Creates Python virtual environment
2. Installs LiteX/LiteEth dependencies
3. Generates 5 Ethernet cores with SRAM macros
4. Prepares cores for ASIC synthesis

### Run ASIC Flow
```bash
make DESIGN_CONFIG=designs/nangate45/liteeth/mac_axi_nangate45_config.mk
```

## Generated Cores

- liteeth_mac_axi_mii
- liteeth_mac_wb_mii
- liteeth_udp_stream_sgmii
- liteeth_udp_stream_rgmii
- liteeth_udp_raw_rgmii

## What the Setup Does

1. **Environment Setup**: Creates Python venv, installs LiteX/LiteEth
2. **Core Generation**: Uses LiteEth's `gen.py` with predefined YAML configs
3. **ASIC Conversion**: Replaces inferred memory with SRAM macro instances
4. **File Organization**: Places cores in OpenROAD-compatible structure

## Platform Support

Tested on WSL Ubuntu/Windows 11. Should work on any Linux system with Python 3.6+ and standard build tools.
