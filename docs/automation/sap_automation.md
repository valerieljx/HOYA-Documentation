# SAP Automation

## Overview

- The three main files to take note of are: `main.py`, `automation.py`, and `gui.py`. 

    - `main.py`: Initializes and centers the main GUI window and launches the SAP Frame interface, handling any uncaught errors via logging.

    - `automation.py`: COntains the core automation logic to interact with SAP GUI using SAP Scripting tool.

    - `gui.py`: Implements the graphical user interface that collects user inputs, validates them, and triggers the SAP automation in a background thread.

## Overview

- *Purpose*: To automate the report extraction from the SAP interface based on user input.

- Users can choose between downloading ZFD107 or FBL3N using the GUI window.

- Requires SAP to already be logged in. Since it is using a scripting tool, the automation can run in the background, and is also much faster than manually downloading.

## User Interface

- On the start page, the user can choose whether they want to download FBL3N or ZFD107. 

### FBL3N

- Users can choose a start date and end date, and can input the path that they want to download the file to.

- The file will be downloaded with the name: `FBL3N_{current_date}.xlsx`. 

- The download path should not have "", and should be the absolute path to the folder to download the file.

### ZFD107

- Users can input the period that they want to download, as well as the absolute path to download the file to.

- The same rules as FBL3N apply for inputting the download path.

- The period should be in the format: YYYYMM.

- The file will be downloaded as `ZFD107_YYYY_MM.xlsx`.

## How to Use

1. Download the `SAP_Automation.zip` folder. Unzip the folder.

2. In Powershell, navigate to your SAP_Automation folder using the code:

    ```Powershell
    cd relative\path\to\SAP_Automation
    ```

3. Download all the requirements in the `requirements.txt` folder using the following code:

    ```Powershell
    pip install -r requirements.txt
    ```

4. Run `main.py` either using VSCode, or run the code below in Powershell:

    ```Powershell
    python main.py`
    ```

5. Use the GUI to download the required files.

<div style="display: flex; justify-content: space-between;" markdown="1">

[:material-arrow-left: STRAVIS Automation](./stravis_automation.md){ .md-button }

</div>