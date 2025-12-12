# ESP-Hosted Firmware

Pre-built [ESP-Hosted-MCU](https://github.com/espressif/esp-hosted-mcu) co-processor firmware binaries

## Overview

The slave firmware enables host MCUs to utilize the Wi-Fi and Bluetooth capabilities of ESP32 series chips through **SDIO, SPI, or UART** interfaces.

## Supported Co-processors and Transports

The following table summarizes the supported co-processors and transport communication buses between the slave and host.

| Transport Supported | SDIO | SPI Full-Duplex | SPI Half-Duplex | UART |
|---|:---:|:---:|:---:|:---:|
| **Co-Processors Supported** | | | | |
| ESP32 | ✓ | ✓ | × | ✓ |
| ESP32-C2 | × | ✓ | ✓ | ✓ |
| ESP32-C3 | × | ✓ | ✓ | ✓ |
| ESP32-C5 | ✓ | ✓ | ✓ | ✓ |
| ESP32-C6/C61 | ✓ | ✓ | ✓ | ✓ |
| ESP32-S2 | × | ✓ | ✓ | ✓ |
| ESP32-S3 | × | ✓ | ✓ | ✓ |

## Usage

Download the appropriate firmware binary for your co-processor from the [Releases](https://github.com/pioarduino/esp-hosted-mcu-firmware/releases) page

## Building Locally

To build the firmware locally:

```bash
# Clone ESP-IDF
git clone -b v5.5.1 --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
./install.sh esp32c6  # or your target
source export.sh
cd ..

# Create project from ESP-Hosted example
idf.py create-project-from-example "espressif/esp_hosted==2.7.3:slave"
cd slave/

# Build for your target
idf.py set-target esp32c6  # or your target
idf.py build

# Output: build/network_adapter.bin
```

## Versioning

Releases are tagged with the ESP-Hosted-MCU version used (e.g., `v2.7.3`).

## License

The ESP-Hosted-MCU firmware is licensed under the Apache License 2.0. See the [ESP-Hosted-MCU repository](https://github.com/espressif/esp-hosted-mcu) for details.
