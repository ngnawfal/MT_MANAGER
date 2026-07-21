# INSTRUCTIONS FOR UPLOADING TO GITHUB

> **Note:** This documents the original one-time migration to a compiled-release
> workflow. `MT_MANAGER.mq5` is tracked in this repository again (source-available,
> see [LICENSE](LICENSE)); only the compiled `.ex5` binary is still kept out of
> git history and attached to GitHub Releases instead. Steps below still apply
> whenever you want to publish a new compiled build.

## Step 1: Compile MT_MANAGER.mq5 to .ex5

1. Open **MetaEditor** (Press F4 in MT5)
2. Open file: `MT_MANAGER.mq5`
3. Press **F7** (or click Compile button)
4. Make sure you see: **"0 errors, 0 warnings"**
5. The compiled file `MT_MANAGER.ex5` will be created in the same folder

## Step 2: Push the source

`MT_MANAGER.mq5` is tracked in git, so commit and push it like any other file:

```bash
git add MT_MANAGER.mq5
git commit -m "Update MT_MANAGER.mq5"
git push -u origin main
```

## Step 3: Publish the compiled .ex5 via a GitHub Release

`.ex5` files are intentionally excluded from git (see `.gitignore`) so compiled
binaries don't bloat the repository's history. Instead, attach the freshly
compiled `MT_MANAGER.ex5` to a GitHub Release — see
[CREATE_RELEASE.md](CREATE_RELEASE.md) for the full step-by-step.

## Step 4: Update GitHub Repository Settings

Go to: https://github.com/nawf-dev/MT_MANAGER/settings

### Repository Description:
```
🎯 Professional MT5 Position Manager | Unified TP/SL Control | Auto-Close | Real-time P&L in USD & Pips | Free Download
```

### Topics (Add these tags):
```
metatrader5
mt5
mql5
expert-advisor
forex-trading
trading-tools
position-management
risk-management
automated-trading
forex
scalping
day-trading
trading-bot
forex-tools
metatrader
```

### Website (optional):
```
https://github.com/nawf-dev/MT_MANAGER
```

## Step 5: Update README.md badges (already done)

README.md already carries the current badge set (Freeware license, current
version, download link to the latest Release). Only touch these again if the
version bumps or the download link changes.

## Step 6: Create Release (Optional but Recommended)

1. Go to: https://github.com/nawf-dev/MT_MANAGER/releases
2. Click: "Create a new release"
3. Tag version: `v1.0.0`
4. Release title: `MT_MANAGER v1.0.0 - Initial Release`
5. Description:
```markdown
# MT_MANAGER v1.0.0 - Professional Position Management EA

## 🎯 Features
- Unified TP/SL management for all positions
- Real-time profit/loss in USD and pips
- Auto-close at specified time
- Spread monitoring
- Market countdown timers
- Clean, professional interface

## 📥 Installation
1. Download `MT_MANAGER.ex5`
2. Copy to: `MQL5\Experts\` folder
3. Restart MT5
4. Drag EA onto chart

## 📚 Full Documentation
See [README.md](https://github.com/nawf-dev/MT_MANAGER#readme)

## ⚠️ Disclaimer
Trading forex carries risk. Use at your own risk.
```

6. Attach file: `MT_MANAGER.ex5`
7. Click: "Publish release"

## Done! 🎉

Your repo will now have:
- ✅ Source code (`MT_MANAGER.mq5`, source-available under [LICENSE](LICENSE))
- ✅ Compiled `.ex5` attached to the GitHub Release (not committed to git)
- ✅ Full documentation (README.md)
- ✅ SEO-optimized description
- ✅ Professional presentation

---

## Marketing Tips:

### Share on:
1. **MQL5 Forum**: https://www.mql5.com/en/forum
2. **Forex Factory**: https://www.forexfactory.com/
3. **Reddit**: r/Forex, r/algotrading
4. **Twitter/X**: Use hashtags #MT5 #Forex #TradingTools
5. **YouTube**: Create demo video

### Sample Post:
```
🚀 Just released MT_MANAGER - Free Position Manager for MT5!

✅ Set TP/SL for all positions with 1 click
✅ Real-time P&L in USD & pips
✅ Auto-close feature
✅ Spread monitor & timers

Perfect for scalpers & day traders!

Download: https://github.com/nawf-dev/MT_MANAGER

#MT5 #Forex #Trading #Free
```
