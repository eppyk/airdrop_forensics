# 🔎 xattribs
A script facilitating forensic analysis of macOS's extended attributes. Returns extended attributes extracted from both `xattr` and `LSQuarantiveEventsV2` database of files received via AirDrop or downloaded using using Chrome, Firefox, Opera, Brave or Safari.  
The data extracted reveals:
   * for AirDropped files: file path, time received, sender name
   * for files downloaded using internet browsers: file path, browser name, time downloaded, origin URL, specific data URL.

## 🛠️ Setup
Install dependencies by running `pip install -r requirements.txt`.

## 👩‍💻 Usage 
Run `python3 xattribs.py /path/to/directory/ [--db /path/to/db] [--json]`

Use `--db` to specify the QuarantineEvents database location, if different than the default (`/Users/<current logged in user name>/Library/Preferences/com.apple.LaunchServices.QuarantineEventsV2`).  
Use `--json` to print output in JSON format.

### Example 1
<ins>Directory containing files to be checked</ins>: `/Users/George/Desktop`  
<ins>Directory containing the QuarantineEvents database</ins>: I don't know, help! (_so - default_)  
<ins>Output format</ins>: easy to read please (_so - default_)  
  
👉  Command to use:
`python3 xattribs.py /Users/George/Desktop`

### Example 2
<ins>Directory containing files to be checked</ins>: `/Users/Nina/Desktop/forensic_evidence/files`  
<ins>Directory containing the QuarantineEvents database</ins>: `/Users/Nina/Desktop/forensic_evidence/db/quarantine`  
<ins>Name of the database file</ins>: `QuarantineEventsV2`  
<ins>Output format</ins>: JSON  

👉  Command to use:
`python3 xattribs.py /Users/Nina/Desktop/forensic_evidence/files /Users/Nina/Desktop/forensic_evidence/db/quarantine/QuarantineEventsV2 --json`


