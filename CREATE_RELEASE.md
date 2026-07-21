# 📦 How to Create GitHub Release with MT_MANAGER.ex5

## ✅ Step-by-Step Instructions

### 1. Go to Releases Page
👉 https://github.com/nawf-dev/MT_MANAGER/releases/new

### 2. Fill in Release Information

**Choose a tag:** `v1.0.0`  
(Click "Create new tag: v1.0.0 on publish")

**Release title:**
```
MT_MANAGER v1.0.0 - Professional Position Management EA
```

**Description:**
```markdown
# 🎯 MT_MANAGER v1.0.0 - Initial Release

Professional position management tool for MetaTrader 5 traders.

## ✨ Features

### Core Position Management
- ✅ **Unified TP/SL** - Set Take Profit and Stop Loss for all positions with ONE click
- ✅ **Interactive UI** - Quick input boxes with Enter key support
- ✅ **Auto-Detection** - Automatically detects existing TP/SL on startup
- ✅ **One-Click Close** - Emergency exit button to close all positions

### Real-Time Monitoring
- 📈 **Profit/Loss in USD** - See estimated profit/loss in your account currency
- 📊 **Profit/Loss in Pips** - Track performance in industry-standard pips
- 💰 **Position Stats** - Monitor total positions count and lot size
- 📡 **Spread Display** - Real-time spread monitoring in pips
- ⏱️ **Candle Countdown** - Precise countdown to next candle close (HH:MM:SS)
- 🕒 **Market Countdown** - See when market closes (Friday) or opens (Monday)

### Automation Features
- ⏰ **Auto Close at Time** - Automatically close all positions at specified time daily
- 🌅 **Auto Entry After Weekend** - Open positions when market reopens on Monday
- 🎯 **Smart Entry** - Waits for price to reach entry level before executing

## 📥 Installation

### Quick Installation (3 Steps)

1. **Download** the file below: `MT_MANAGER.ex5` ⬇️
   
2. **Copy to MT5 folder:**
   ```
   C:\Users\[YourUsername]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Experts\
   ```
   
   **Quick way:**
   - Open MT5
   - Press `Ctrl + Shift + D` (Open Data Folder)
   - Navigate to `MQL5\Experts\`
   - Paste `MT_MANAGER.ex5`

3. **Refresh MT5:**
   - Right-click on **Navigator → Expert Advisors**
   - Click **"Refresh"**
   - Drag **"MT_MANAGER by nwf"** onto chart

✅ **Done! Ready to use.**

## 📚 Full Documentation

For complete user guide, features explanation, and troubleshooting:  
👉 [Read Full Documentation](https://github.com/nawf-dev/MT_MANAGER#readme)

## 🎯 Perfect For

- 📊 **Scalpers** managing 5-10 positions simultaneously
- 📈 **Day Traders** who need quick TP/SL adjustments
- 💼 **Swing Traders** holding multiple positions overnight
- ⚡ **Any trader** tired of manually managing each position

## ⚙️ Input Parameters

### Basic Settings
- `TargetTP` - Default TP price on startup (0.0 = auto-detect)
- `TargetSL` - Default SL price on startup (0.0 = auto-detect)

### Auto Close Feature
- `EnableAutoClose` - Enable/disable auto-close (default: false)
- `AutoCloseTime` - Time to close all positions (default: "23:00")

### Auto Entry Feature (After Weekend)
- `EnableAutoEntry` - Enable/disable auto-entry (default: false)
- `EntryType` - BUY or SELL (default: BUY)
- `EntryPrice` - Target entry price (default: 0.0)
- `EntryLot` - Lot size (default: 0.01)
- `EntryTPPips` - TP in pips from entry (default: 30)
- `EntrySLPips` - SL in pips from entry (default: 20)

## 🆕 What's New in v1.0.0

- 🎉 Initial stable release
- ✅ Core TP/SL management
- ✅ Real-time monitoring (USD + Pips)
- ✅ Spread display
- ✅ Candle close countdown
- ✅ Market open/close countdown
- ✅ Auto-close feature
- ✅ Auto-entry after weekend
- ✅ Clean borderless UI

## ⚠️ Important Notes

### System Requirements
- **Platform:** MetaTrader 5 (Build 3000+)
- **OS:** Windows 7/8/10/11
- **Broker:** Any MT5 broker

### Trading Disclaimer
⚠️ **Trading forex carries significant risk.**  
This EA is a tool, not a guarantee of profit. Always use proper risk management and test on demo account before live trading.

The author is NOT LIABLE for any trading losses. Use at your own risk.

## 📞 Support

- **Issues/Bugs:** [GitHub Issues](https://github.com/nawf-dev/MT_MANAGER/issues)
- **Feature Requests:** [GitHub Discussions](https://github.com/nawf-dev/MT_MANAGER/discussions)
- **Documentation:** [README.md](https://github.com/nawf-dev/MT_MANAGER#readme)

## 📄 License

Freeware - Free to use for personal and commercial trading.  
See [LICENSE](https://github.com/nawf-dev/MT_MANAGER/blob/main/LICENSE) for details.

---

## 📊 Statistics

- **Version:** 1.0.0
- **Release Date:** February 7, 2025
- **File Size:** ~50 KB
- **Platform:** MetaTrader 5
- **Language:** MQL5
- **License:** Freeware (Source-Available - see [LICENSE](LICENSE))

---

**Made with ❤️ for the trading community**

If you find this EA useful, please ⭐ **star the repository**!

---

## 🔥 Quick Links

- 📖 [Full Documentation](https://github.com/nawf-dev/MT_MANAGER#readme)
- 🐛 [Report Bug](https://github.com/nawf-dev/MT_MANAGER/issues/new)
- 💡 [Request Feature](https://github.com/nawf-dev/MT_MANAGER/issues/new)
- 📝 [Changelog](https://github.com/nawf-dev/MT_MANAGER/blob/main/CHANGELOG.md)

---

**Thank you for downloading MT_MANAGER! 🎯**
```

### 3. Upload File

**Attach binaries:**
- Drag and drop `MT_MANAGER.ex5` from:
  ```
  C:\Users\kaysa\OneDrive\Documents\ai_trade\MT_MANAGER.ex5
  ```
- Or click "Attach binaries by dropping them here or selecting them"

### 4. Publish

Click: **"Publish release"** (green button)

---

## ✅ After Publishing

Your download link will be:
```
https://github.com/nawf-dev/MT_MANAGER/releases/download/v1.0.0/MT_MANAGER.ex5
```

Update README.md badge to point to release:
```markdown
[![Download](https://img.shields.io/badge/Download-MT__MANAGER.ex5-success)](https://github.com/nawf-dev/MT_MANAGER/releases/latest/download/MT_MANAGER.ex5)
```

---

## 🎯 Why Release Instead of Repo?

### ✅ Advantages:
1. **Cleaner repo** - No binary files in source control
2. **Version control** - Each version has its own download
3. **GitHub standard** - Professional presentation
4. **Download stats** - See how many people downloaded
5. **Easier updates** - Just create new release for v1.1, v1.2, etc.
6. **Auto-generated changelog** - GitHub creates comparison

### Example:
```
v1.0.0 - Initial release (50 downloads)
v1.1.0 - Added Break Even (120 downloads)
v1.2.0 - Added Trailing Stop (200 downloads)
```

---

## 📸 Screenshot Example

Your release page will look like this:

```
MT_MANAGER v1.0.0 - Professional Position Management EA
───────────────────────────────────────────────────────
Published by nawf-dev on Feb 7, 2025

[Description here with features, installation, etc.]

Assets
──────
MT_MANAGER.ex5    (50.2 KB)    [Download]
Source code (zip)              [Download]
Source code (tar.gz)           [Download]
```

---

## 🚀 Next Steps After Release

1. Update README.md download link to point to release
2. Share release link on:
   - MQL5 Forum
   - Forex Factory
   - Reddit (r/Forex)
   - Twitter/X
3. Monitor download stats
4. Respond to issues/questions

---

**Ready? Go create your release now! 🎉**

👉 https://github.com/nawf-dev/MT_MANAGER/releases/new
