## Baremetal Project Template ⚙️🚜
# Overview

baremetal-project-template is an automotive-flavored, production-grade firmware architecture template designed for scalable embedded systems.

-------------------------------------------------
# This template provides:
- Strict layered architecture
- Hardware abstraction
- Bootloader compatibility
- RTOS migration readiness
- Long lifecycle maintainability
- Safety-oriented structure

# It is intended for:
- Automotive ECUs
- Industrial controllers
- Agricultural machinery
- Long lifecycle embedded products
- Architecture Philosophy
  
-------------------------------------------------

# This template follows a strict layered architecture:

```text
Application
   ↓
Services
   ↓
Drivers
   ↓
HAL
   ↓
BSP
   ↓
MCU / Hardware
```
----------------------------------------
# Key Principles
- No upward dependencies
- No register access outside HAL/BSP
- Hardware-independent application logic
- Configuration isolated in config/
- Clear module ownership boundaries

------------------------------------------------------------
## Project Structure

```text
baremetal-project-template/
│
├── app/        # Product logic & state machines
├── services/   # System services (WDT, NVRAM, scheduler, logger)
├── drivers/    # External device drivers
├── hal/        # MCU abstraction layer
├── bsp/        # Board-specific configuration
├── system/     # Startup, interrupts, linker
├── boot/       # Bootloader interface hooks
├── config/     # Global configuration
├── utils/      # Common utilities
├── main/       # Entry point
├── docs/       # Architecture & design docs
├── build/      # Build system
└── README.md

```
> Detailed responsibilities for each layer are documented inside their respective folders.

-----------------------------------------

## Layer Responsibilities

### Application Layer

Contains:
- State machines
- Control logic
- Product behavior

Must never access registers directly.

----------------------------------------------------
### Services Layer
Reusable system services such as:
- Watchdog manager
- NVRAM manager
- Fault manager
- Cooperative scheduler
- Logger

Services isolate system behavior from hardware.

-------------------------------------------------
### Drivers Layer
External device drivers:
- Modems
- Sensors
- EEPROM
- CAN transceivers
  
Drivers depend only on HAL.

--------------------------------------------
### HAL (Hardware Abstraction Layer)
Provides MCU-independent APIs:
- UART
- SPI
- CAN
- GPIO
- Timer

HAL isolates MCU vendor code.

-----------------------------------------------
### BSP (Board Support Package)
Board-level configuration:
- Clock tree
- Pin mapping
- Power configuration
- Peripheral routing

Allows reuse across multiple boards.

---------------------------------------------------
### Boot Interface
Provides:
- Bootloader jump mechanism
- Firmware update hooks
- Version management structure

Designed for future OTA or UDS-based updates.

-------------------------------------------------------------------------
