# SheetsAttack!

SheetsAttack! is a Python post-exploitation script that enables red teamers to pillage Google Sheets if you uncover a Google Workspaces (G-Suite) credential file. With this script, you can easily discover worksheet files, list sheets within those files, and retrieve the contents of specific sheets. 

## Installation

1. Clone this repository or download the `sheetsattack.py` script to your local machine.

2. Make sure you have Python 3 installed. If not, you can download it from [Python's official website](https://www.python.org/downloads/).

3. Install the required Python packages using pip:
   ```bash
   pip3 install google-auth google-auth-oauthlib google-auth-httplib2 google-api-python-client gspread
   ```

4. Obtain a Google Service Account JSON key file and save it as `key.json`. Follow Google's instructions on how to create a service account and get the JSON key file.

5. Set the `GOOGLE_APPLICATION_CREDENTIALS` environment variable to point to your `key.json` file:
   ```bash
   export GOOGLE_APPLICATION_CREDENTIALS=/path/to/key.json
   ```

## Usage

SheetsAttack! provides several commands to manage your Google Sheets:

### 1. List Worksheet Files

To list the names of all accessible worksheet files, use the following command:
```bash
python3 sheetsattack.py --list-worksheet-files
```

### 2. List Sheets

To list the sheets contained in a specific worksheet file, provide the `--spreadsheet-name` flag with the desired spreadsheet's name:
```bash
python3 sheetsattack.py --list-sheets --spreadsheet-name SPREADSHEET_NAME
```

### 3. Retrieve Sheet Contents

To retrieve the contents of a specified worksheet, provide the `--spreadsheet-name` flag with the desired spreadsheet's name and the `--worksheet-name` flag with the name of the worksheet:
```bash
python3 sheetsattack.py --get-content --spreadsheet-name SPREADSHEET_NAME --worksheet-name WORKSHEET_NAME
```

**Example**:
```bash
python3 sheetsattack.py --get-content --spreadsheet-name MyData --worksheet-name Sheet1
```



## To Do

- [ ] Add functionality to enumerate gdrive or other services, might branch to another project altogether

