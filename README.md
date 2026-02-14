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

----------------------------------------
# Key Principles
- No upward dependencies
- No register access outside HAL/BSP
- Hardware-independent application logic
- Configuration isolated in config/
- Clear module ownership boundaries
