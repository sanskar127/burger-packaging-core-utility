# Burger Packaging Tool - Core Utility (Alpha Version)  
*Bare Machine Project core utility*

## Overview

The **Burger Packaging Tool** is an C++ utility designed to package (create) and install (unpack) tools or software into a binary format. This single executable handles both packaging and unpacking via simple command-line arguments. The packaged binary files use the `.burg` extension.

The tool is part of the **Bare Machine** project and is developed using **Visual Studio 2022** with the **MSVC** compiler for Windows. Precompiled binaries for Linux are also available.

**Note**: This version is in **alpha** and may be limited in functionality. Future updates will include features like compression, obfuscation, and enhanced packaging.

## Features

- **Create (Package) a Tool or Software**: Convert a tool or software into a packaged binary with a `.burg` extension.
- **Install (Unpack) a Binary**: Extract the contents of a `.burg` file back into its original form.

## Usage

### How to Use on Windows?

The tool is compiled as a standalone Windows binary. You can download the latest precompiled binaries from the releases page.

#### Downloading the Latest Release

1. **Go to the Latest Releases**:
   - Visit the [releases page](https://github.com/sanskar127/burger-packaging-core-utility/releases).

2. **Download the Binaries**:
   - Download the precompiled Windows binary for your system from the latest release.

#### Command-Line Usage

To use the tool, simply run the `burger.exe` binary with the appropriate command.

- **To create (package) a tool or software** into a `.burg` binary:
    ```sh
    burger.exe create <tool_or_software_directory>
    ```
    Where:
    - `<tool_or_software_directory>` is the path to the directory containing the tool or software you want to package.

- **To install (unpack) a `.burg` binary** and extract its contents:
    ```sh
    burger.exe install <package_file.burg>
    ```
    Where:
    - `<package_file.burg>` is the packaged binary file you want to unpack.

#### Example

1. **Creating a packaged `.burg` binary**:
    ```sh
    burger.exe create C:\path\to\my_tool
    ```
    This command will package the contents of `C:\path\to\my_tool` (which represents a tool or software) into a binary named `packager.burg`.

2. **Installing (unpacking) a `.burg` binary**:
    ```sh
    burger.exe install my_tool.burg
    ```
    This command will extract the contents of `my_tool.burg` back into its original tool or software directory structure.

### Setting up Environmental PATH (Windows)

To use `burger.exe` globally from the Command Prompt (CMD) or PowerShell, you can add its directory to the system's `PATH` environment variable.

#### Steps to Add the Binaries to the PATH:

1. **Locate the Binaries**:
   Ensure the `burger.exe` binary is in a directory, e.g., `C:\Tools\BurgerPackagingTool\`.

2. **Open the System Properties**:
   - Press `Win + X` and select **System**.
   - Click **Advanced system settings** on the left.
   - Click **Environment Variables** at the bottom of the System Properties window.

3. **Edit the PATH Environment Variable**:
   - In the **Environment Variables** window, under the **System variables** section, scroll down and select **Path**, then click **Edit**.
   - In the **Edit Environment Variable** window, click **New** and add the directory path, e.g., `C:\Tools\BurgerPackagingTool\`.
   - Click **OK** to close all windows.

4. **Verify the PATH Update**:
   - Open a new Command Prompt or PowerShell window.
   - Type `burger.exe` and press **Enter**. If successful, the `burger.exe` command will work globally.

You can now run the following commands from **any** directory in CMD or PowerShell:

```sh
burger.exe create C:\path\to\my_tool
burger.exe install my_tool.burg
```

### How to Use on Linux?

Precompiled binaries for Linux are available. You can install them using the provided `Makefile`.

#### Downloading the Latest Release

1. **Go to the Latest Releases**:
   - Visit the [releases page](https://github.com/sanskar127/burger-packaging-core-utility/releases).

2. **Download the Binaries**:
   - Download the precompiled Linux binary from the latest release.

#### Installation Steps for Linux

1. **Install the Tool**:
   After downloading the binaries, install them to a directory of your choice using the `Makefile`. The default installation path is `/usr/local/bin`.

    To install the tool, run:
    ```sh
    sudo make install
    ```

2. **Uninstall the Tool**:
    If you want to remove the binaries, run:
    ```sh
    sudo make uninstall
    ```

3. **Clean Build Files**:
    To remove temporary build files, use:
    ```sh
    make clean
    ```

#### Command-Line Usage on Linux

Once installed, use the tool as follows:

- **To create (package) a tool or software** into a `.burg` binary:
    ```sh
    burger create /path/to/my_tool
    ```

- **To install (unpack) a `.burg` binary** and extract its contents:
    ```sh
    burger install my_tool.burg
    ```

You can run the tool from any location after installation.

## License

This project is **not open source**. All rights are reserved under the provided [LICENSE](LICENSE) file.

---

For any bugs or feature requests, please contact the project owner/maintainer.
