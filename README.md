# Google-drive-api-setup-with-python
Setup google drive API with python project for CRUD operations of Google Spreadsheet.
1. Create a new project to use Google Drive Api's

	go to: https://console.developers.google.com/
	![](create%20new%20project.png)

   
2. Search for **Google Drive API** and Click **Enable API**.
	![](Enable%20api.png)


3. Create credentials for a Web Server to access Application Data.
	![](create%20Credential.png)

4. create the service account and grant it a Project Role of Editor.
	![](Create%20service%20account.png)

5. Download the JSON file by clicking Continue.

6. Copy the JSON file to your code directory and rename it to client_secret.json

7. Now Open the client_secret.json file and copy **client_email** and share spreadsheet with this email.


Lets start with Python.

1. Prerequisite:
	1. gspread
	2. oauth2client
	
	Install these packages using pip:
   
	   ```pip install gspread oauth2client```


2. Add these line of code to authenticate google client with API

```
import gspread
from oauth2client.service_account import ServiceAccountCredentials
# use creds to create a client to interact with the Google Drive API
scope = ['https://www.googleapis.com/auth/spreadsheets']
creds = ServiceAccountCredentials.from_json_keyfile_name('client_secret.json', scope)
client = gspread.authorize(creds)
```

for more operation please check script.py File.
