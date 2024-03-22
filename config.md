# Config Creation
In order to use SystemFlooder or however you brand it, you need a config file thats placed on your C2 of choice.

## C2 & Config Hosting

## Example
```
{
  "handle_desktop_content": 1,
  "threads": 20,
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

### threads
Threads decide how much folder are filled with images in parallel.
Keep in mind that there is a point at which thread handling needs more time, than another thread can safe.
