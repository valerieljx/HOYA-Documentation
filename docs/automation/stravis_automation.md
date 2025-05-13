# STRAVIS Automation

- The four main files to take note of are: `main.py`, `automation.py`, `gui.py`, and `config.py`.

    -  `main.py`: Initializes and centers the main GUI window and launches the STRAVISFrame interface, handling any uncaught errors via logging.

    - `gui.py`: Implements the graphical user interface that collects user inputs (period and folder path), validates them, and triggers the STRAVIS automation in a background thread.

    - `automation.py`: Contains the core automation logic to interact with the STRAVIS GUI using screen coordinates and `pyautogui` for navigating, filtering, and downloading data files.

    - `config.py`: Stores all hardcoded screen coordinates used by `pyautogui` to interact with specific UI elements in the STRAVIS system.

## Overview

- *Purpose*: To automate the report extraction from the STRAVIS interface based on user input.

- Creates a folder for the period indicated, and automatically downloads Excel files.

- Requires STRAVIS to be logged in and accessible on screen. The mouse cannot be moved, as this automation works by automated clicks on the screen.

## User Interface

- The app uses a `Tkinter` GUI with:

    - Input for *Period* ('YYYY.MM')

    - Input for *Base Folder* (where a fiscal year subfolder will be created)

## How to Use

1. Download the `STRAVIS_Automation.zip` folder. Unzip the folder.

2. In Powershell, navigate to your STRAVIS_Automation folder using the code:

    ```PowerShell
    cd relative\path\to\STRAVIS_Automation
    ```

3. Once all the [configurations](#configurations) are done, package it into an app.

    1. Make sure PyInstaller is installed. To do so, use the following code:

        ```PowerShell
        pip install PyInstaller
        ```

    2. Run the following code in Powershell:

        ```PowerShell
        python -m PyInstaller automation_{your_name}.py -n STRAVIS_Automation_{your_name}.exe
        ```

    3. Once the code has run, navigate to the `\dist` folder in STRAVIS_Automation from your Files application. The `.exe` file should be stored there. 

        - Open this file to get the automation app.

## Configurations

1. Create a copy of 4 files: `main.py`, `gui.py`, `automation.py`, and `config.py`.

    - Naming convention for all the files: `{file_name}_{your_name}.py`.

### `config.py`

1. Open your own version of `config_{your_name}.py`.

2. Using `click_test.py`, find all the coordinates to click for each item in the dictionary.

    - To test:

        - Create a new file called `test_config_{your_name}.py`. You will use this file as your workspace to test the automated clicks.

        - Type `from config_{your_name} import *`.

        - In the subsequent lines, copy the lines of automation that you want to test from `automation.py` and paste it into the document.

        - If there are input variables being used, you can change them to any variables that you want to test with.

3. Once all the automated clicks work, save the file, and your `config_{your_name}.py` is working.

### `automation.py`

1. Open your own version of `automation_{your_name}.py`.

2. In Line 12, change the code from `from config import *` to `from config_{your_name} import *`.

3. Save the file.

### `gui.py`

1. Open your own version of `gui_{your_name}.py`.

2. In Line 5, change the code from `from automation import STRAVISAutomation` to `from automation_{your_name} import STRAVISAutomation`.

3. Save the file.

### `main.py`

1. Open your own version of `main_{your_name}.py`.

2. In Line 2, change the code from `from gui import STRAVISFrame` to `from gui_{your_name} import STRAVISFrame`.

3. Save the file.

<div style="display: flex; justify-content: flex-end; gap: 0.5rem;" markdown="1">
[SAP Automation :material-arrow-right:](./sap_automation.md){ .md-button }
</div>