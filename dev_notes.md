Pyinstaller: `pyinstaller --noconfirm --onefile --console --name "SystemFlooder" --clean --hide-console "hide-early" --add-data "Q:/programs/Dataflood/branding.json;."  "Q:/programs/Dataflood/main.py"`

## Create a new executable
1. Create a file called branding.json
  * It gets embedded into the exe
  * Template below
2. Add the exe to the whitelist
3. Create the exe using  the above pyinstaller command


### branding.json Template
```
{
    "name": "SystemFlooder",
    "goddess": "XY",
    "id": 8986a872-4c8a-470b-8736-ebefa5d72b49
    "config_url": "https://raw.githubusercontent.com/vanishedbydefa/SystemFlooder/main/config.json" 
}
```
