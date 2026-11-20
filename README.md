# Gigabyte GA-B85-HD3 (Rev. 2.0) — BIOS FH with Resizable BAR (`reBART` v0.2c)

Modded **FH** BIOS for the **Gigabyte GA-B85-HD3 (Rev. 2.0)** motherboard with full **Resizable BAR** and **Above 4G Decoding** support enabled via **reBART**.

## Tested Hardware & Results
- **Motherboard:** Gigabyte GA-B85-HD3 (Rev. 2.0) — Base BIOS `FH`
- **CPU:** Intel Xeon E3-1246 v3 (Haswell / Intel 8 Series B85 chipset)
- **RAM:** 32 GB DDR3
- **GPU:** NVIDIA GeForce RTX 5070 (12 GB VRAM, Blackwell)
- **Status:** Confirmed working (`Resizable BAR: Enabled`, `Above 4G Decode: Yes`, `BAR0: 16384 MB`) in Windows 10 UEFI mode without ACPI errors.

## What Was Modified
1. Patched the DSDT table extracted from `AmiBoardInfo` using `rebart_dsdt_patch.exe`.
2. Injected `reBART.ffs` (v0.2c) right after `PciBus` (`3C1DE39F-D207-408A-AACC-731CFB7F1DD7`).

## How to Flash & Configure
> **⚠️ WARNING:** Only flash this ROM on **Gigabyte GA-B85-HD3 Rev. 2.0**! Do **not** flash it on Rev. 1.x or Rev. 2.1 boards. Flash at your own risk.

1. Flash `B85HD3_reBART.FH` using **Q-Flash (F8)**.
2. Power off the PC and perform a **Clear CMOS** (jumper or battery) to clear old NVRAM variables.
3. Enter BIOS Setup (`Del`) and under **BIOS Features**, set:
   - **Windows 8 Features:** `Windows 8 WHQL`
   - **CSM Support:** `Never` (requires UEFI/GPT OS installation)
4. Boot into Windows (UEFI mode), run **`ReBarState.exe`** as Administrator, enter **`32`** (Auto/Max) or your desired BAR size, and reboot.

## Credits
- Huge thanks to [roschank](https://github.com/roschank/reBART) for creating the `reBART` module and `rebart_dsdt_patch` tool for Intel 8-Series motherboards.
- Thanks to [xCuri0](https://github.com/xCuri0/ReBarUEFI) for `ReBarState.exe` and [LongSoft](https://github.com/LongSoft) for `UEFITool` & `AmiBoardInfoTool`.
<img width="2559" height="1439" alt="jpg" src="https://github.com/user-attachments/assets/fa0a6772-1227-426b-a040-a37fb35f054b" />
