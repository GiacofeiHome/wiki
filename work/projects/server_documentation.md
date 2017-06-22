# Server Documentation 
:DOCUMENTATION:
## Debian Server
:DYNOSERVER:
### Syncthing
:SYNCTHING:
  - Login
    - user: reman
    - pswd: admin

### Dyno Download

Dyno data download works with several scripts.

#### Script Overview
:TESTDATA:
  - */bin/process_dyno*: Runs serveral times per hour to find new tests and
   format them as text to be imported into M1.
    - Calls *find_tests*, *make*
  - */bin/find_tests*: Checks a given directory for test files. Found files are
    stored in a text file that is compared against to avoid duplicates.
  - *make*: Make script determines which files need to be processed. Uses the
    scripts: *process_[FN|FZ|VB].py* to convert raw data files from the dyno into
    parsable text files.

#### process_XX.py

These scripts utilize a settings file *settings.py* that contains all of the
test fields that are to be imported. This file needs to be updated anytime the
dyno test configuration is modified to change the name of a test field or a new
test field is added.

### Detailed file locations

*process_dyno*:  /media/dyno_share/Server Settings/process_dyno
*find_tests*:    /media/dyno_share/Server Settings/find_tests
*process_FN.py*: /media/dyno_share/parser/process_FN.py
*process_FZ.py*: /media/dyno_share/parser/process_FZ.py
*process_VB.py*: /media/dyno_share/parser/process_VB.py
*makefile*:      /media/dyno_share/parser/makefile
*settings.py*:   /media/dyno_share/parser/settings.py
*syncthing*:     /media/HDD/smb_share/Tools/syncthing-linux-386-v0.14.18/syncthing

