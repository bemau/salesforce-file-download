# salesforce-files-download-copy
- This repo was forked from the [original](https://github.com/snorf/salesforce-files-download) and changed.
- Python script to download Salesforce Files from a list of ContentDocumentId

# how to configure it
``` sh
$ python3 -m venv env
$ source env/bin/activate
$ pip install -r requirements.txt # (pip install [package_name] -U)
$ python download.py
```
# before run it
- create a file download.ini from the download.ini.template and configure it
- run the following SOQL from Salesforce to get the IDs from the ContentDocumentId 
- add the ContentDocumentId in the file content_document_ids.csv
# how to run it
``` sh
$ python download.py
```
## Examples of SOQL
> SELECT Id, ContentDocumentId, LinkedEntityId,ContentDocument.title FROM ContentDocumentLink WHERE LinkedEntityId in (SELECT Id FROM User where UserType = 'Standard')

> SELECT Id, ContentDocumentId, LinkedEntityId,ContentDocument.title FROM ContentDocumentLink WHERE LinkedEntityId in (SELECT Id FROM Account) and ContentDocument.title like '%example%'