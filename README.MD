# Burger Packaging Tool - Core Utility

## Overview

The **Burger Packaging Tool** is a C++ utility designed for packaging and unpackaging directories. The current version focuses on the **wrapping** and **unwrapping** processes, allowing directories to be wrapped into a packaged binary and then unwrapped back to their original structure. The tool is developed using **Visual Studio 2022** with the **MSVC** compiler for Windows, but it is also available as precompiled binaries for Linux.

**Note:** This is an **experimental version** of the tool, and it may be prone to crashes or other instability issues. Please use it with caution, especially in production environments.

The project currently only supports the wrapping and unwrapping functionality. Future versions will include additional features such as compression, obfuscation, and packaging.

## Features

- **Wrap a Directory**: Package a directory into a binary file.
- **Unwrap a Binary**: Extract a previously packaged binary back to its original directory structure.

## Usage

### How to Use on Windows?

The project has been compiled as standalone Windows binaries.You can simply download the binaries from the latest releases.

#### Downloading the Latest Release

1. **Go to the Latest Releases**:
   - Visit the [releases page](https://github.com/burger-packaging-core-utility/releases) of the project.
   
2. **Download the Binaries**:
   - Download the precompiled Windows binaries for your system from the latest release.

#### Command-Line Usage

To use the tool, simply invoke the appropriate binary from the command line. The syntax for each mode is as follows:

- **To wrap a directory** into a binary:
    ```sh
    <program> --wrap <wrapper_name> <directory>
    ```
    Where:
    - `<program>` is the name of the program (`burger.exe`).
    - `<wrapper_name>` is the name for the resulting packaged binary.
    - `<directory>` is the path to the directory you want to wrap.

- **To unwrap a binary** and extract its contents:
    ```sh
    <program> --unwrap <wrapper_name>
    ```
    Where:
    - `<program>` is the name of the program (`burger.exe`).
    - `<wrapper_name>` is the name of the packaged binary file you want to extract.

#### Example

1. **Wrapping a directory**:
    ```sh
    wrapper.exe --wrap my_archive C:\path\to\my_directory
    ```
    This command will create a binary file `my_archive` containing all the contents of `C:\path\to\my_directory`.

2. **Unwrapping a binary**:
    ```sh
    unwrapper.exe --unwrap my_archive
    ```
    This command will extract the contents of `my_archive` back into the original directory structure.

### Setting up Environmental PATH (Windows)

To use the `burger.exe` command globally from the Command Prompt (CMD) or PowerShell, you can add the directory containing the binaries to your system's `PATH` environment variable.

#### Steps to Add the Binaries to the PATH:

1. **Locate the Binaries**:
   Ensure you have the `burger.exe`, `wrapper.exe` and `unwrapper.exe` binaries in a directory on your system, e.g., `C:\Tools\BurgerPackagingTool\`.

2. **Open the System Properties**:
   - Press `Win + X` and select **System**.
   - In the System window, click **Advanced system settings** on the left.
   - Click the **Environment Variables** button at the bottom of the System Properties window.

3. **Edit the PATH Environment Variable**:
   - In the **Environment Variables** window, under the **System variables** section, scroll down and select **Path**, then click **Edit**.
   - In the **Edit Environment Variable** window, click **New** and enter the path to the directory containing your binaries, e.g., `C:\Tools\BurgerPackagingTool\`.
   - Click **OK** to close all windows.

4. **Verify the PATH Update**:
   - Open a new Command Prompt or PowerShell window (you may need to restart the terminal if it was already open).
   - Type `burger.exe` and press **Enter**. If the binaries are successfully added to the `PATH`, they should run from any directory.

Now, you can run the following commands from **any** directory in CMD or PowerShell:

```sh
burger.exe --wrap my_archive C:\path\to\my_directory
burger.exe --unwrap my_archive
```

### How to Use on Linux?

The Burger Packaging Tool is also available as precompiled binaries for Linux. You can use the provided `Makefile` to install, uninstall, or clean the binaries.

#### Downloading the Latest Release

1. **Go to the Latest Releases**:
   - Visit the [releases page](https://github.com/burger-packaging-core-utility/releases) of the project.
   
2. **Download the Binaries**:
   - Download the precompiled Linux binaries for your system from the latest release.

#### Installation Steps for Linux

1. **Install the Tool**:
    After downloading the binaries, you can install them to a directory of your choice using the `Makefile`. The default installation path is `/usr/local/bin`, but you can specify a different directory.

    To install the tool, run:
    ```sh
    sudo make install
    ```

2. **Uninstall the Tool**:
    If you need to remove the installed binaries, use the following command:
    ```sh
    sudo make uninstall
    ```

3. **Clean Build Files**:
    To remove temporary build files, you can run:
    ```sh
    make clean
    ```

#### Command-Line Usage on Linux

Once the binaries are installed, you can use the tool as follows:

- **To wrap a directory** into a binary:
    ```sh
    burger --wrap my_archive /path/to/my_directory
    ```
- **To unwrap a binary** and extract its contents:
    ```sh
    burger --unwrap my_archive
    ```

You can run the tool from any location in your terminal after installation.

## License

This project is **not open source**. All rights are reserved under the provided [LICENSE](LICENSE) file.

---

For any bugs or feature requests, please contact the project owner/maintainer.