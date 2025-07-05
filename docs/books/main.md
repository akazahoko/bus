# Book Library 

Guide for managing e-book library.

# Book Sources

Manga:
- [Kmoe](https://kox.moe/)

(NSFW) Manga:
- [Hanime1.me](https://hanime1.me/comics) - nHentai map 
- [nHentai](https://nhentai.net/)
- [Sukebei](https://sukebei.nyaa.si/?f=0&c=1_4&q=) - Japanese mostly
- [未來數位](https://future-digi.com/) - Chinese Publisher

(NSFW) Photo Book:
- [Sukebei](https://sukebei.nyaa.si/?f=0&c=2_1&q=)
 
# Calibre

## Setup

1. Install [Calibre](https://calibre-ebook.com/download) and [No Trans Plugin](https://github.com/Cirn09/calibre-do-not-translate-my-path) to stop Calibre auto translate directory to ASCII 
2. Use existing library or make a new one
3. Disable unwanted processing in `Setting->Import`

## Import books to library 

1. Compress the downloaded folder to `.zip` file 
2. Rename the extension to `.cbz` 
3. Import the file to Calibre
4. Convert to `.epub` file in Calibre
5. Edit metadata and table of content

# KOReader

## Setup

1. Install KOReader from F-Droid or with `.apk`
2. Change default home directory 

## Sync with Calibre

Calibre plugin should be installed by default. 

1. Set default receive folder in `Menu->Tools(wrench icon)->Calibre->Wireless Setting` before sync.
2. In `Calibre->Connection & Sharing`, start Wireless Connection (Leave everything blank)
3. In `Calibre->Devices->Set This Device`, Set the default name for files that sent to device (Remove ID) and set cover compression rate (maybe >= 90)
4. To send books to device, select books in Calibre then choose `right click menu->Send to device->Send to Main Device`

## Calibrating device

1. Goto `Menu->Tools(wrench icon)->More Tools->Developer Options->Start Compatibility Test`  
2. For Boox device:
   - `LIGHTS` = `Onyx ADB (lights)` 
   - `E-INK` = `Onyx/Qualcomm`
3. Connect device in debug mode
4. In ADB, set the permission to true: 
   ```shell
    adb shell settings put global hidden_api_policy 1
   ```

## Set Book cover as lockscreen

1. Open a random book in KOReader
2. In `Menu->Settings(gear icon)->Screen->Cover Picture`, set photo path.
3. Set the lockscreen to that `cover.png`

# Reference
[KOReader: Android tips and tricks](https://github.com/koreader/koreader/wiki/android-tips-and-tricks)