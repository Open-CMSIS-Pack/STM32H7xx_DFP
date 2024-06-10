[![Version](https://img.shields.io/github/v/release/Open-CMSIS-Pack/STM32H7xx_DFP)](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/releases/latest)

# STM32H7xx_DFP

This is the development repository for the **STMicroelectronics STM32H7 Series Device Family Pack (DFP)** - a CMSIS software pack that is designed to work with all compiler toolchains (Arm Compiler, GCC, IAR, LLVM). It is released as [CMSIS software pack](https://www.keil.arm.com/packs/stm32h7xx_dfp-keil) and therefore accessible by CMSIS-Pack enabled software development tools.

This DFP uses the generator integration of the [CMSIS-Toolbox to Configure STM32 Devices with CubeMX](https://github.com/Open-CMSIS-Pack/cmsis-toolbox/blob/main/docs/CubeMX.md) that is also supported in µVision 5.40 an higher.

> **Note:** This is currently Work in Progress. Final release is expected in Q3'2024.

## Repository top-level structure

Directory                   | Description
:---------------------------|:--------------
[.github/workflows](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/tree/main/.github/workflows)  | [GitHub Actions](#github-actions) for creating the software pack.
[CMSIS/Debug](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/tree/main/CMSIS/Debug)              | Contains debug configuration scripts.
[CMSIS/Flash](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/tree/main/CMSIS/Flash)              | Contains flash algorithms.
[CMSIS/SVD](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/tree/main/CMSIS/SVD)                  | Contains SVD files for the devices.
[Templates](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/tree/main/Templates)                  | Device specific project templates to start new *csolution projects*.

## Usage

The device is configured using [STM32CubeMX](https://www.st.com/en/development-tools/stm32cubemx.html) (CubeMX). Refer to [CMSIS-Toolbox - Configure STM32 Devices with CubeMX](https://github.com/Open-CMSIS-Pack/cmsis-toolbox/blob/main/docs/CubeMX.md) for usage information with *csolution projects*.

Add this component to your *csolution project* to connect to CubeMX.

    - component: Device:CubeMX                # Component that connects to CubeMX

> **Important Note:**
>
> The DFP **does not** contain [Startup and System Configuration files](https://arm-software.github.io/CMSIS_6/latest/Core/using_pg.html) and **does not** provide the [`CMSIS_device_header`](https://arm-software.github.io/CMSIS_6/latest/Core/using_pg.html#using_packs) provided
> by the CMSIS-Core that defines the registers and interrupt mapping. This files are provided by the CubeMX firmware pack. It is therefore mandatory to use CubeMX when using this DFP as it will pull-in these files and make it accessible.

## Using the development repository

This development repository can be used in a local directory and [mapped as software pack](https://github.com/Open-CMSIS-Pack/cmsis-toolbox/blob/main/docs/build-tools.md#install-a-repository) using for example `cpackget` with:

    cpackget add <path>/Keil.STM32H7xx_DFP.pdsc

## Generate software pack

The software pack is generated using bash shell scripts.

- `./gen_pack.sh` based on [Open-CMSIS-Pack/gen-pack](
https://github.com/Open-CMSIS-Pack/gen-pack)) generates the software pack. Run this script locally with:

      STM32H7xx_DFP $ ./gen_pack.sh

### GitHub Actions

The repository uses GitHub Actions to generate the pack:

- `.github/workflows/pack.yml` based on [Open-CMSIS-Pack/gen-pack-action](https://github.com/Open-CMSIS-Pack/gen-pack-action) generates pack using the [Generate software pack](#generate-software-pack) scripts.

## License

The DFP is licensed under [![License](https://img.shields.io/github/license/Open-CMSIS-Pack/STM32H7xx_DFP?label)](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/blob/main/LICENSE).

## Issues

Please feel free to raise an [issue on GitHub](https://github.com/Open-CMSIS-Pack/STM32H7xx_DFP/issues)
to report misbehavior (i.e. bugs) or start discussions about enhancements. This
is your best way to interact directly with the maintenance team and the community.
We encourage you to append implementation suggestions as this helps to decrease the
workload of the maintenance team.

