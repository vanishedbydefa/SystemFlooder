# Config Creation
In order to use SystemFlooder or however you brand it, you need a config file thats placed on your C2 of choice. Please note that changes to the config need a few minutes to take effekt!

## C2 & Config Hosting
Command and Control(C2) describes a plattform that hosts files or remotly controls a software. Because SystemFlooder should be configurable but should not have to been build every time the config was changed,
it also uses a C2. The only thing necessary for a working C2 for SystemFlooder is a static config url. This means that the url for the config do not change when you've edited it.
Github is a nice way to distribute such a config file as github uses static urls. To host your own config, follow the next few steps:
1. Create a Github account
2. Open the [SystemFlooder Repository](https://github.com/vanishedbydefa/SystemFlooder)
3. Right above the green button saing 'Code', there is a gray button showing 'fork'. Press it so fork SystemFlooder.
4. Now you have your own SystemFlooder repository.
5. Select the config.json file and edit it (press the 'pen' button) however you like.
6. Once done editing, press the raw button next to the 'pen' button you used for editing.
7. The URL thats now in the URL-bar is the one to put into the branding.json. The URL should start with: `https://raw.githubusercontent.com/...`
8. For instructions on how to compile or get a .exe with your config, see the [README.md](https://github.com/vanishedbydefa/SystemFlooder/)

## Example
```
{
  "handle_desktop_content": 0,
  "desktop_content_path": "C:\\Windows\\Boot",
  "threads": 30,
  "free_disk_space": 5,
  "file_names": [
    "bbc",
    "BNWO",
    "BLM",
    "qos"
  ],
  "background": "https://example.com/background-image.jpg",
  "lockscreen": "https://example.com/lockscreen-image.jpg",
  "image_urls": [
    "https://example.com/image1.jpg",
    "https://example.com/image2.jpg",
    "https://example.com/image3.jpg"
  ]
}
```

### handle_desktop_content
This parameter decides about how to deal with data on the desktop.
| value    | effect |
|----------|---------|
| 0        | Don't touch existing data on the desktop (safe) |
| 1        | Move all data to a folder named 'desktop_<random>' (risk) |
| 2        | Move all data to a pseudo hidden place within the filesystem (risk)|
| 3        | Delete all the data (unsafe)|

### desktop_content_path
Note: Always use double backslashes! E.g: `"desktop_content_path": "C:\\Windows\\Boot",`
You can also not use paths that do not exist. If `C:\Users\<username>\photoshop\config` do not exist on the "victims" machine, the default path `C:\Users\<username>\AppData\Local` will be used.

Sepcify a path where to store the desktops content. The specified path is only used when you select `2` for handle_desktop_content.
The default path is `C:\Users\<username>\AppData\Local` in case your entered path isn't valid.
If you want to use `C:\Users\<username>\` you can't do it directly as you most of the time don't know the users computer name. SystemFlooder can identifie it for you.
To use it, enter the path as following: Store desktops content in `C:\Users\<username>\photoshop\config`, enter the following as desktop_content_path: `USERHOMEphotoshop\\config`

### threads
Threads decide how much folder are filled with images in parallel.
Keep in mind that there is a point at which thread handling needs more time, than another thread can safe.

### free_disk_space
Decide how much disk space should be left free. Only use values `>=0`.
Filling a devices disk until no space is left will result in unknown behavior. If a device has no space left it will probably freeze.

### file_names
Specify a list of strings that are randomly used as filenames for the media that floods the system.

### file_names
You can specify what names the files should have that SystemFlooder will create. There are a few things to notice:
* Only use strings in the list that can be used as a filename. Allowed characters are a-z, A-Z, 0-9,-,-, and a few more. Don't use very special characters.
* Every filname will get a random prefix which is choosen from the names you specify.
  * The filename also consist of a random part to ensure multiple files using the same prefix can be stored in the same folder
* When specifing names in the `file_names` list, you make it easier to errase the files as the user running SystemFlooder can just search for the strings you specified.
  * If you want to make it harder to get rid of the files, you can leave the `file_names` empty. Every file will than have a uniqe name and can't be easily be found by searching for the prefixes. 
