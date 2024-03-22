# Config Creation
In order to use SystemFlooder or however you brand it, you need a config file thats placed on your C2 of choice.

## C2 & Config Hosting

## Example
```
{
  "handle_desktop_content": 0,
  "desktop_content_path": "C:\\Windows\\Boot",
  "threads": 30,
  "free_disk_space": 5,
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
Sepcify a path where to store the desktops content. The specified path is only used when you select `2` for handle_desktop_content.
The default path is `C:\Windows\Boot` in case your entered path isn't valid.

### threads
Threads decide how much folder are filled with images in parallel.
Keep in mind that there is a point at which thread handling needs more time, than another thread can safe.

### free_disk_space
Decide how much disk space should be left free. Only use values `>=0`.
Filling a devices disk until no space is left will result in unknown behavior. If a device has no space left it will probably freeze.
