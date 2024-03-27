Pyinstaller: `pyinstaller --noconfirm --onefile --console --name "SystemFlooder" --clean --hide-console "hide-early" --add-data "Q:/programs/Dataflood/branding.json;."  "Q:/programs/Dataflood/main.py"`

## Create a new executable
### Manuel
1. Create a file called branding.json
  * It gets embedded into the exe
  * Template below
2. Add the exe to the whitelist
3. Create the exe using  the above pyinstaller command
### Using `build.py`
Run build.py to do the following thing automatically:
1. Create a branding.json
2. Try to create a new exe based on the new branding.json
==> You still need to add the id to the whitelist

### branding.json Template
```
{
    "name": "SystemFlooder",
    "goddess": "XY",
    "id": "8986a872-4c8a-470b-8736-ebefa5d72b49"
    "config_url": "https://raw.githubusercontent.com/vanishedbydefa/SystemFlooder/main/config.json" 
}
```
