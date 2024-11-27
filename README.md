# 3GPP_Spec_Downloader
Python script to download 3GPP specs from https://www.3gpp.org/ftp/Specs/archive

### Requirements
- for pdf conversion Libre Office must be installed

### Usage
```
usage: spec_downloader.py [-h] (-d DOCUMENT | -s SERIES | -l LIST) [-v MAJOR_VERSION] [-e] [--pdf] [--latest]
                          [--purge]

Downloads 3GPP specs. If no version parameter is given all versions are downloaded.

options:
  -h, --help            show this help message and exit
  -d DOCUMENT, --document DOCUMENT
                        comma separated list of documents to download with format
                        <series>.<document_number>.g. 33.117
  -s SERIES, --series SERIES
                        comma separated list of numbers representing a 3GPP spec series
  -l LIST, --list LIST  textfile including document list (line based) - document format e.g. 33.117
  -v MAJOR_VERSION, --major-version MAJOR_VERSION
                        comma separated list of numbers or characters representing 3GPP spec major version(s)
  -e, --extract         extracts the downloaded zip archives
  --pdf                 tries to convert doc files to pdf
  --latest              only latest (or latest major version if given) document version is downloaded
  --purge               delete all byproducts of result e.g. delete zip file after extracting
  -o OUTPUT_DIR, --output-dir OUTPUT_DIR
                        directory to download files to (default: current directory)
```
### Examples

Downloads all versions of this spec as zip files:
```
./spec_downloader.py -d 33.117
```

Downloads all specs listed in doc_list.txt with the latest version of the major versions g and h. Afterwards the zip files get extracted and converted to pdf. All artifacts (zip files, doc files) get purged:
```
./spec_downloader.py -l doc_list.txt -v g,h --latest --pdf --purge
```