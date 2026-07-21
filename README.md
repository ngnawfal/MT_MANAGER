# MT_MANAGER by nwf

[![MT5](https://img.shields.io/badge/Platform-MetaTrader%205-blue)](https://www.metatrader5.com/)
[![MQL5](https://img.shields.io/badge/Language-MQL5-orange)](https://www.mql5.com/)
[![License](https://img.shields.io/badge/License-Freeware-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-1.1.0-brightgreen)](https://github.com/nawf-dev/MT_MANAGER/releases)
[![Download](https://img.shields.io/badge/Download-MT__MANAGER.ex5-success)](https://github.com/nawf-dev/MT_MANAGER/releases/latest/download/MT_MANAGER.ex5)
[![GitHub release](https://img.shields.io/github/v/release/nawf-dev/MT_MANAGER)](https://github.com/nawf-dev/MT_MANAGER/releases/latest)

> **Professional Position Management Tool for MetaTrader 5**  
> Manage Take Profit, Stop Loss, and monitor all your trades from a single, powerful interface.

---

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Screenshots](#screenshots)
- [Installation](#installation)
- [Quick Start](#quick-start)
- [User Interface Guide](#user-interface-guide)
- [Features Explained](#features-explained)
- [Configuration](#configuration)
- [FAQ](#faq)
- [Troubleshooting](#troubleshooting)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)
- [Author](#author)

---

## 🎯 Overview

**MT_MANAGER** is a comprehensive Expert Advisor designed for MetaTrader 5 that simplifies position management by allowing traders to:

- **Synchronize TP/SL** across all open positions with a single click
- **Monitor real-time metrics** including profit/loss in both USD and pips
- **Automate trading tasks** like auto-close at specific times and auto-entry after weekends
- **Track market timing** with candle close countdown and market open/close timers
- **View critical information** at a glance without cluttering your chart

Perfect for scalpers, day traders, and swing traders who manage multiple positions simultaneously.

---

## ✨ Features

### 🎛️ Core Position Management
- ✅ **Unified TP/SL Setting** - Set Take Profit and Stop Loss for all positions on the current symbol at once
- ✅ **Interactive Input Boxes** - Quick input with visual feedback and Enter key support
- ✅ **Auto-Detection** - Automatically detects existing TP/SL from open positions on EA startup
- ✅ **One-Click Close All** - Emergency exit button to close all positions instantly
- ✅ **Magic Number Filter** - Optionally manage only the positions opened by a specific EA/magic number, instead of every position on the symbol
- ✅ **Broker Stop-Distance Validation** - Detects when a TP/SL is too close to the market price (below the broker's stop/freeze level) and skips it with a clear warning instead of a silent broker rejection

### 📊 Real-Time Monitoring
- 📈 **Live Floating P/L** - Real, current profit/loss of all open positions (not just a hypothetical at TP/SL)
- 📈 **Live Profit/Loss Tracking** - See estimated profit/loss in account currency (USD/EUR/etc) if TP/SL is hit
- 📊 **Pips Calculation** - Track profit/loss in pips for better risk assessment (correctly handles both 5/3-digit and 4/2-digit broker quotes)
- 💰 **Total Position Stats** - Monitor total positions count and lot size
- 📡 **Spread Display** - Real-time spread monitoring in pips
- ⏱️ **Candle Countdown** - Precise countdown to next candle close (HH:MM:SS)
- 🕒 **Market Countdown** - See when market closes (Friday) or opens (Monday during weekends)
- 🔖 **Status Line** - At-a-glance summary of which automations (Magic filter, Break Even, Trailing Stop, Auto Close, Auto Entry, Spread Filter) are currently active

### 🤖 Automation Features
- ⏰ **Auto Close at Time** - Automatically close all positions at a specified time daily
- 🌅 **Auto Entry After Weekend** - Open positions when market reopens on Monday with predefined parameters
- 🎯 **Smart Entry Execution** - Waits for price to reach entry level before executing
- 🛡️ **Break Even Automation** - Moves SL to entry (plus a small offset) once a position reaches a defined profit in pips
- 📉 **Trailing Stop** - Keeps SL a fixed distance behind price once a position is far enough in profit
- 🌊 **Max Spread Filter** - Skips Auto Entry while the spread is wider than an acceptable threshold (e.g. during a volatile Monday open)
- 🔊 **Sound Alerts** - Optional audio confirmation for Close All, Auto Close, Auto Entry, and Break Even events

### 🎨 User Interface
- 🖥️ **Clean Design** - Borderless panels with color-coded information
- 📍 **Dual Panel Layout** - Control panel (left) and info display (right)
- 🎨 **Color Coding** - Green for profits, red for losses, yellow for alerts
- 📱 **Non-Intrusive** - Stays out of your way while providing critical info

---

## 📸 Screenshots

### Main Interface

```
┌─────────────────────────┐                    ┌──────────────────────────────┐
│  CONTROL PANEL          │                    │  MT_MANAGER by nwf           │
├─────────────────────────┤                    ├──────────────────────────────┤
│ Input Target TP:        │                    │ Symbol: EURUSD               │
│ [1.09500            ]   │                    │ Timeframe: M15               │
│ [      SET TP       ]   │                    │ Spread: 1.5 pips             │
│                         │                    │ Close Candle: 00:12:45       │
│ Input Target SL:        │                    │ Market Close: 2 hari 8 jam   │
│ [1.08800            ]   │                    │                              │
│ [      SET SL       ]   │                    │ Target TP: 1.09500           │
│                         │                    │ Target SL: 1.08800           │
│ [    CLOSE ALL      ]   │                    │                              │
└─────────────────────────┘                    │ Total Posisi: 3              │
                                               │ Total Lot: 0.15              │
                                               │ Estimasi Profit TP: +375 USD │
                                               │ Estimasi Loss SL: -225 USD   │
                                               │ TP Pips: 50.0 pips           │
                                               │ SL Pips: -30.0 pips          │
                                               └──────────────────────────────┘
```

> Since v1.1.0 the info panel also shows a **Floating P/L** line (the real,
> current profit/loss of open positions) and a **Mode** status line
> summarizing which automations (Magic filter, Break Even, Trailing Stop,
> Auto Close, Auto Entry, Spread Filter) are currently active.

### Weekend Mode

```
┌──────────────────────────────┐
│  MT_MANAGER by nwf           │
├──────────────────────────────┤
│ Symbol: GBPUSD               │
│ Timeframe: H1                │
│ Spread: 2.1 pips             │
│ Close Candle: 00:45:23       │
│ Market Opens: 1 hari 8 jam   │ ← Countdown to Monday open!
│                              │
│ Target TP: Belum diset       │
│ Target SL: Belum diset       │
│                              │
│ Total Posisi: 0              │
│ Total Lot: 0.00              │
│ Estimasi Profit TP: -        │
│ Estimasi Loss SL: -          │
│ TP Pips: -                   │
│ SL Pips: -                   │
└──────────────────────────────┘
```

---

## 📦 Installation

### Quick Installation (3 Steps)

1. **Download the EA**
   
   👉 **[DOWNLOAD MT_MANAGER.ex5](https://github.com/nawf-dev/MT_MANAGER/releases/latest/download/MT_MANAGER.ex5)**  
   _(From GitHub Releases)_

2. **Copy to MetaTrader 5 folder**
   
   Copy `MT_MANAGER.ex5` to:
   ```
   C:\Users\[YourUsername]\AppData\Roaming\MetaQuotes\Terminal\[TerminalID]\MQL5\Experts\
   ```
   
   **Quick way:**
   - Open MT5
   - Press `Ctrl + Shift + D` (Open Data Folder)
   - Navigate to `MQL5\Experts\`
   - Paste `MT_MANAGER.ex5`

3. **Refresh MT5**
   - In MT5, right-click on **Navigator → Expert Advisors**
   - Click **"Refresh"**
   - You should see **"MT_MANAGER by nwf"**

✅ **Done! Ready to use.**

### Building from Source (Optional)

Prefer to compile it yourself, or want to customize the EA first? The source is in this repo:

1. Open **MetaEditor** (Press F4 in MT5)
2. Open `MT_MANAGER.mq5` from your cloned copy of this repository
3. Press **F7** to compile — you should see `0 errors, 0 warnings`
4. Copy the generated `MT_MANAGER.ex5` to `MQL5\Experts\` as above

---

## 🚀 Quick Start

### 1. Attach EA to Chart

1. Open MetaTrader 5
2. Open a chart (e.g., EURUSD M15)
3. Navigate to **Navigator → Expert Advisors**
4. Drag **MT_MANAGER by nwf** onto the chart
5. Click **OK** in the settings dialog (use defaults for first time)

### 2. Basic Usage

#### Setting Take Profit
1. Type target TP price in the input box (e.g., `1.09500`)
2. Click **SET TP** button (or press Enter)
3. All positions on current symbol will have TP set to 1.09500

#### Setting Stop Loss
1. Type target SL price in the input box (e.g., `1.08800`)
2. Click **SET SL** button (or press Enter)
3. All positions on current symbol will have SL set to 1.08800

#### Close All Positions
- Click **CLOSE ALL** button (red)
- All positions on current symbol will close immediately
- Use with caution!

### 3. Monitor Your Trades

The right panel shows:
- Current profit/loss if TP is reached
- Current loss if SL is reached
- Total pips profit/loss
- Real-time spread
- Time until next candle close
- Time until market close (or opens on weekends)

---

## 🎛️ User Interface Guide

### Left Panel: Controls

| Element | Description | Action |
|---------|-------------|--------|
| **Input Target TP** | Text input box for TP price | Type price + Enter or click SET TP |
| **SET TP Button** | Green button | Applies TP to all positions |
| **Input Target SL** | Text input box for SL price | Type price + Enter or click SET SL |
| **SET SL Button** | Orange-red button | Applies SL to all positions |
| **CLOSE ALL Button** | Red button | Closes all positions instantly |

### Right Panel: Information Display

| Field | Description | Color |
|-------|-------------|-------|
| **Symbol** | Current trading pair | White |
| **Timeframe** | Current chart timeframe | White |
| **Spread** | Current spread in pips | Yellow |
| **Close Candle** | Countdown to next candle | Yellow (Bold) |
| **Market Close/Opens** | Countdown to Friday close or Monday open | Orange |
| **Target TP** | Current TP setting | Green |
| **Target SL** | Current SL setting | Orange |
| **Total Posisi** | Number of open positions | White |
| **Total Lot** | Sum of all lot sizes | White |
| **Floating P/L** | Real, current profit/loss of all open positions right now | Green (profit) / Red (loss) |
| **Estimasi Profit TP** | Expected profit in USD if TP hits | Green (profit) / Red (loss) |
| **Estimasi Loss SL** | Expected loss in USD if SL hits | Red (loss) / Green (profit) |
| **TP Pips** | Total profit in pips | Aqua |
| **SL Pips** | Total loss in pips | Orange |
| **Mode** | Summary of active automations (Magic filter, BE, TS, Auto Close, Auto Entry, Spread Filter) | Silver |

---

## 🔧 Features Explained

### 1. Unified TP/SL Management

**Problem:** Managing TP/SL for multiple positions individually is time-consuming and error-prone.

**Solution:** MT_MANAGER allows you to set the same TP or SL for all positions on the current symbol with one click.

**Example:**
```
You have 5 BUY positions on EURUSD at different prices:
- Position 1: Entry 1.08500
- Position 2: Entry 1.08600
- Position 3: Entry 1.08700

You want all to close at 1.09500:
1. Type 1.09500 in TP input
2. Click SET TP
3. All 5 positions now have TP = 1.09500 ✅
```

### 2. Auto-Detection of Existing TP/SL

**When EA loads**, it scans all open positions and:
- If all positions have the same TP → Auto-fills TP input box
- If all positions have the same SL → Auto-fills SL input box
- If positions have different TP/SL → Leaves inputs empty

**Benefit:** No need to remember what TP/SL you set before!

### 3. Profit/Loss Calculation

#### In Account Currency (USD/EUR/etc)
```
Estimasi Profit TP: +375 USD
```
Shows how much money you'll make if all positions hit TP.

#### In Pips
```
TP Pips: 50.0 pips
```
Shows total profit in pips across all positions (industry standard).

**Why both?**
- **USD** = Easy to understand for account management
- **Pips** = Better for analyzing trade quality

### 4. Real-Time Spread Monitoring

```
Spread: 1.5 pips
```

**Why it matters:**
- High spread = Higher trading cost
- Spreads widen during news → Avoid trading
- Compare brokers by spread

**Example:**
```
EURUSD normal spread: 0.8-1.5 pips ✅
EURUSD during NFP news: 5.0-10.0 pips ⚠️ (wait!)
```

### 5. Candle Close Countdown

```
Close Candle: 00:12:45
```

**Use cases:**
- Wait for candle close confirmation before entry
- Know when your pending order might trigger
- Time your manual entries better

**Format:** HH:MM:SS (Hours:Minutes:Seconds)

### 6. Market Open/Close Countdown

**During Trading Week (Monday-Friday):**
```
Market Close: 2 hari 8 jam
```
Shows time until Friday market close.

**During Weekend (Saturday-Sunday):**
```
Market Opens: 1 hari 8 jam 15 mnt
```
Shows time until Monday market open.

**Benefit:** Plan your weekend, know when you can trade again!

### 7. Auto Close at Time ⭐

**Purpose:** Automatically close all positions at a specific time every day.

**Configuration:**
```mql5
EnableAutoClose = true
AutoCloseTime = "23:00"  // 11 PM every day
```

**Use cases:**
- Avoid holding positions overnight
- Close before major news events
- Stick to your trading hours discipline

**Example:**
```
You trade 09:00-17:00 daily.
Set AutoCloseTime = "17:00"
→ EA closes all positions at 5 PM automatically
→ No stress, no late-night monitoring!
```

### 8. Auto Entry After Weekend ⭐

**Purpose:** Open position automatically when market opens Monday.

**Configuration:**
```mql5
EnableAutoEntry = true
EntryType = ORDER_TYPE_BUY  // or ORDER_TYPE_SELL
EntryPrice = 1.09000        // Target entry price
EntryLot = 0.01             // Lot size
EntryTPPips = 30            // TP = 30 pips from entry
EntrySLPips = 20            // SL = 20 pips from entry
```

**How it works:**
1. Market opens Monday morning
2. EA waits for price to reach `EntryPrice`
3. Once price reaches, EA opens position with specified TP/SL
4. Only executes once per Monday

**Example:**
```
Friday close: EURUSD = 1.08500
You expect gap up on Monday.

Settings:
- EntryType = BUY
- EntryPrice = 1.09000
- EntryLot = 0.05
- EntryTPPips = 50
- EntrySLPips = 30

Monday open: Price = 1.08900
→ EA waits...

Price hits 1.09000:
→ EA opens BUY 0.05 lot
→ TP = 1.09500 (50 pips)
→ SL = 1.08700 (30 pips)
→ Done! ✅
```

---

## ⚙️ Configuration

### Input Parameters

#### Basic Settings

```mql5
input double TargetTP = 0.0;  // Default TP price on startup
input double TargetSL = 0.0;  // Default SL price on startup
```

**Recommended:** Leave at `0.0` to let EA auto-detect from existing positions.

#### Auto Close Settings

```mql5
input group "=== AUTO CLOSE AT TIME ==="
input bool EnableAutoClose = false;     // Enable Auto Close (default: OFF)
input string AutoCloseTime = "23:00";   // Close Time (HH:MM)
```

**Example configurations:**

| Trading Style | Setting | Reason |
|---------------|---------|--------|
| Day Trader | `EnableAutoClose = true`<br>`AutoCloseTime = "17:00"` | Close at end of trading day |
| Swing Trader | `EnableAutoClose = false` | Hold positions overnight |
| News Avoider | `AutoCloseTime = "14:29"` | Close 1 min before 14:30 news |

#### Auto Entry Settings

```mql5
input group "=== AUTO ENTRY AFTER WEEKEND ==="
input bool EnableAutoEntry = false;              // Enable Auto Entry (default: OFF)
input ENUM_ORDER_TYPE EntryType = ORDER_TYPE_BUY; // Entry Type (BUY/SELL)
input double EntryPrice = 0.0;                   // Entry Price
input double EntryLot = 0.01;                    // Lot Size
input int EntryTPPips = 30;                      // TP in Pips
input int EntrySLPips = 20;                      // SL in Pips
```

**Example: Gap Trading Strategy**

```mql5
EnableAutoEntry = true
EntryType = ORDER_TYPE_BUY
EntryPrice = 1.09000
EntryLot = 0.05
EntryTPPips = 50
EntrySLPips = 30
```

#### Position Filter (Magic Number)

```mql5
input group "=== POSITION FILTER ==="
input long MagicNumber = 0;   // Magic Number Filter (0 = kelola semua posisi)
```

**Default (`0`):** MT_MANAGER manages **every** position on the current symbol, regardless of how it was opened (manual, other EAs, pending orders) — same behavior as v1.0.0.

**Non-zero value:** MT_MANAGER only manages positions tagged with that exact magic number. Useful when you run multiple EAs on the same symbol and only want MT_MANAGER touching its own trades (including the ones opened by Auto Entry).

#### Break Even

```mql5
input group "=== BREAK EVEN ==="
input bool EnableBreakEven = false;       // Enable Break Even (default: OFF)
input int BreakEvenTriggerPips = 20;      // Move SL to entry after X pips profit
input int BreakEvenOffsetPips = 2;        // Offset SL from entry (locks a small profit)
```

Once a position is `BreakEvenTriggerPips` in profit, its SL is moved to `entry ± BreakEvenOffsetPips`. SL only ever moves in the favorable direction — it will never be loosened.

> **Important:** Break Even (and Trailing Stop below) only run while the unified **Target SL** input box / `TargetSL` is empty (`0`). If you set a unified SL, that takes priority so the two systems don't fight over the same position.

#### Trailing Stop

```mql5
input group "=== TRAILING STOP ==="
input bool EnableTrailingStop = false;    // Enable Trailing Stop (default: OFF)
input int TrailingStartPips = 30;         // Start trailing after X pips profit
input int TrailingStepPips = 10;          // Distance SL trails behind price (pips)
```

Once profit passes `TrailingStartPips`, SL is kept `TrailingStepPips` behind the current price, tightening as price moves further in your favor.

#### Max Spread Filter

```mql5
input group "=== SPREAD FILTER ==="
input bool EnableMaxSpreadFilter = false; // Enable Max Spread Filter (default: OFF)
input double MaxSpreadPips = 3.0;         // Max spread allowed for Auto Entry (pips)
```

When enabled, Auto Entry is skipped (and retried later) while the spread is wider than `MaxSpreadPips` — useful for avoiding the spread spike that often happens right at Monday's market open.

#### Sound Alerts

```mql5
input group "=== ALERTS ==="
input bool EnableSoundAlerts = false;     // Enable Sound Alerts (default: OFF)
```

Plays a short sound on Close All, Auto Close, Auto Entry, and Break Even events, so you get audible confirmation without staring at the chart.

---

## 🎓 Usage Scenarios

### Scenario 1: Scalping Multiple Positions

**Situation:** You opened 5 quick scalp positions, want to take profit at key level.

**Steps:**
1. Identify target level: `1.09500`
2. Type `1.09500` in TP input
3. Press Enter
4. All 5 positions now target 1.09500
5. Monitor "Estimasi Profit TP" → `+$250 USD`
6. Watch price reach TP, all close automatically!

### Scenario 2: Moving Stop Loss to Break Even

**Situation:** Price moved 30 pips in profit, want to protect.

**Steps:**
1. Check average entry price in info panel
2. Type that price in SL input
3. Click SET SL
4. SL now at entry = Zero risk!

### Scenario 3: Emergency Exit

**Situation:** Major news just released, market going crazy!

**Steps:**
1. Click **CLOSE ALL** button
2. All positions close within 1 second
3. Preserved capital ✅

### Scenario 4: Weekend Gap Trading

**Situation:** Strong trend on Friday, expect continuation Monday.

**Setup:**
```mql5
EnableAutoEntry = true
EntryType = ORDER_TYPE_BUY
EntryPrice = 1.09200
EntryLot = 0.10
EntryTPPips = 60
EntrySLPips = 40
```

**Result:**
- Go enjoy your weekend
- EA monitors market Monday morning
- Auto-enters when price hits 1.09200
- You wake up to an active trade!

---

## 💡 Best Practices

### ✅ DO

- **Use on demo first** - Test all features before live trading
- **Set realistic TP/SL** - Based on technical analysis, not random numbers
- **Monitor spread** - Avoid trading when spread is abnormally high
- **Enable auto-close for day trading** - Enforce discipline
- **Keep EA running** - Auto-features only work when EA is active
- **Use on one chart per symbol** - Avoid conflicts

### ❌ DON'T

- **Don't set TP below current price for BUY** - Invalid TP!
- **Don't set SL above current price for BUY** - Invalid SL!
- **Don't use CLOSE ALL carelessly** - It's instant and irreversible
- **Don't rely 100% on auto-entry** - Market conditions change
- **Don't run multiple instances** - Can cause duplicate trades
- **Don't ignore logs** - Check Experts tab for errors

---

## ❓ FAQ

### Q: Does MT_MANAGER open new positions?

**A:** Only if you enable `EnableAutoEntry = true` for weekend auto-entry. By default, it only **manages existing positions**.

### Q: Can I use it on multiple charts?

**A:** Yes, but each instance only manages positions for **its own symbol**. 
- EURUSD chart → Manages EURUSD positions only
- GBPUSD chart → Manages GBPUSD positions only

### Q: What happens if I set invalid TP/SL?

**A:** MT5 will reject the modification. Check the Experts tab for error messages like:
```
Error modifying TP position #12345: Invalid stops
```

### Q: Does it work with other EAs?

**A:** Yes! MT_MANAGER reads all positions, regardless of how they were opened (manual, EA, pending orders).

### Q: How much resources does it use?

**A:** Very lightweight. Updates only on new ticks (milliseconds CPU time).

### Q: Can I change panel position?

**A:** Currently panels are fixed (left and right). You can modify the code if needed.

### Q: Does it support Magic Number filtering?

**A:** Yes, since v1.1.0. Set the `MagicNumber` input to filter which positions MT_MANAGER manages; leave it at `0` (default) to manage all positions on the symbol, same as before.

### Q: What about partial closes?

**A:** Not yet. CLOSE ALL closes 100% of all positions. (Planned for v2.0)

### Q: Does auto-entry work on all days?

**A:** No, only on Monday 00:00-03:00 (market open detection).

---

## 🔧 Troubleshooting

### Issue: EA doesn't appear in Navigator

**Solution:**
1. Check if file is in correct folder: `MQL5\Experts\`
2. Compile the file (F7 in MetaEditor)
3. Check for compilation errors
4. Refresh Navigator (right-click → Refresh)

### Issue: Buttons don't work

**Solution:**
1. Check if EA is actually running (smiley face in top-right corner)
2. Enable "Allow DLL imports" in EA settings
3. Enable "Allow live trading" in EA settings
4. Check Experts tab for errors

### Issue: TP/SL not updating

**Solution:**
1. Check if positions exist on the current symbol
2. Verify TP/SL prices are valid:
   - BUY: TP > current price, SL < current price
   - SELL: TP < current price, SL > current price
3. Check broker's minimum stop level (some brokers require 10+ pips)
4. Look at Experts tab for "Invalid stops" errors

### Issue: Profit/Loss shows wrong amount

**Solution:**
1. Ensure you're looking at the right symbol
2. Currency conversion affects display (if account is EUR but pair is USD-based)
3. This is **estimated** profit, actual may vary due to spread/commission

### Issue: Auto-close not working

**Solution:**
1. Check `EnableAutoClose = true` in settings
2. Verify time format is "HH:MM" (e.g., "23:00", not "23:0" or "11 PM")
3. EA must be running at that exact time
4. Check Experts tab for execution confirmation

### Issue: Auto-entry not triggering

**Solution:**
1. Check `EnableAutoEntry = true`
2. Must be Monday 00:00-03:00 hour
3. Price must reach `EntryPrice` level
4. Only executes once per Monday
5. Check logs for "Auto Entry executed" message

### Issue: Panel text overlapping

**Solution:**
This shouldn't happen in latest version. If it does:
1. Refresh chart (F5)
2. Recompile EA
3. Remove and re-attach EA
4. Report issue on GitHub

---

## 🗺️ Roadmap

### Version 1.0.0 ✅
- [x] Unified TP/SL management
- [x] Real-time profit/loss display (USD + Pips)
- [x] Spread monitoring
- [x] Candle countdown
- [x] Market open/close countdown
- [x] Auto-close at time
- [x] Auto-entry after weekend
- [x] Interactive UI

### Version 1.1.0 (Current) ✅
- [x] Break Even automation (move SL to entry after X pips profit)
- [x] Trailing Stop (auto-adjust SL as price moves in favor)
- [x] Magic Number filtering (manage only specific EA's positions)
- [x] Max spread filter (prevent Auto Entry when spread > X pips)
- [x] Sound alerts (Close All, Auto Close, Auto Entry, Break Even)
- [x] Live Floating P/L display (real, not just estimated, profit/loss)
- [x] Correct pip math on 3-digit (JPY-style) symbols, not just 5-digit
- [x] Broker stop/freeze-distance validation with clear warnings

### Version 2.0 (Planned) 🔜

**Advanced Position Management:**
- [ ] Partial Close (close 50% at TP1, rest at TP2)

**Enhanced UI:**
- [ ] Account info panel (Balance, Equity, Margin, Daily P&L)
- [ ] One-click trading buttons (BUY/SELL with preset lot)
- [ ] Session time indicator (Asia/London/NY sessions)
- [ ] Position duration display

**Risk Management:**
- [ ] Max drawdown protection (auto-close all if DD > X%)
- [ ] Daily profit target (stop trading after +X% profit)
- [ ] Lot size calculator (risk % based position sizing)

**Notifications:**
- [ ] Visual alerts (popup messages)
- [ ] Email notifications (optional)
- [ ] Telegram integration (send alerts to phone)

**Analytics:**
- [ ] Daily statistics (trades, win rate, profit)
- [ ] CSV export (trade history)
- [ ] Correlation monitor (EURUSD vs GBPUSD relationship)

### Version 3.0 (Future) 🔮
- [ ] Multi-symbol management (manage all pairs from one panel)
- [ ] Custom templates (save/load settings)
- [ ] Hotkey support (keyboard shortcuts)
- [ ] Mobile-friendly remote panel
- [ ] Strategy presets (scalping, swing, news trading)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Bugs

1. Check [existing issues](https://github.com/nawf-dev/MT_MANAGER/issues)
2. Create new issue with:
   - MT5 version
   - Broker name
   - Steps to reproduce
   - Expected vs actual behavior
   - Screenshots if possible

### Suggesting Features

1. Check [roadmap](#roadmap) first
2. Open issue with tag `enhancement`
3. Describe use case and benefit

### Code Contributions

The source (`MT_MANAGER.mq5`) lives in this repository. Fork it, make your change, and open a pull request — see [CONTRIBUTING.md](CONTRIBUTING.md) for the full workflow, style guide, and testing checklist.

---

## 📄 License

This software is provided as **Freeware** for personal and commercial use.

**Terms:**
- ✅ **Free to use** for personal and commercial trading
- ✅ **Free to download** and install on unlimited MT5 accounts
- ✅ **Source-available** - `MT_MANAGER.mq5` is in this repository; you may view and modify it for personal use
- ❌ **No redistribution** - Do not re-upload or sell this EA, or any modified version of it
- ✅ **No warranty** - Use at your own risk
- ⚠️ **Author not liable** for any trading losses

**Trading Disclaimer:** Trading forex carries significant risk. This EA is a tool, not a guarantee of profit. Always use proper risk management and test on demo before live trading.

---

## 👤 Author

**nwf (Developer)**

- GitHub: [@nawf-dev](https://github.com/nawf-dev)
- Repository: [MT_MANAGER](https://github.com/nawf-dev/MT_MANAGER)

---

## 🙏 Acknowledgments

- **MetaQuotes** - For MetaTrader 5 platform
- **MQL5 Community** - For documentation and support
- **Beta Testers** - For valuable feedback

---

## 📚 Additional Resources

### Learning Resources
- [MQL5 Documentation](https://www.mql5.com/en/docs)

### Related Tools
- [MetaTrader 5 Download](https://www.metatrader5.com/en/download)
- [MQL5 Editor](https://www.mql5.com/en/articles/177)

### Support
- [GitHub Issues](https://github.com/nawf-dev/MT_MANAGER/issues)
- [MQL5 Forum](https://www.mql5.com/en/forum)

---

## 📊 Statistics

![GitHub stars](https://img.shields.io/github/stars/nawf-dev/MT_MANAGER?style=social)
![GitHub forks](https://img.shields.io/github/forks/nawf-dev/MT_MANAGER?style=social)
![GitHub watchers](https://img.shields.io/github/watchers/nawf-dev/MT_MANAGER?style=social)

---

<div align="center">

**⭐ If you find this EA useful, please give it a star! ⭐**

**Made with ❤️ for the trading community**

</div>

---

## 📝 Changelog

See [CHANGELOG.md](CHANGELOG.md) for the full history. Highlights:

### v1.1.0 (2026-07-21)
- ✅ Magic Number filter (manage only a specific EA's positions)
- ✅ Break Even automation
- ✅ Trailing Stop
- ✅ Max Spread Filter for Auto Entry
- ✅ Sound alerts
- ✅ Live Floating P/L display
- 🐛 Fixed pip calculation on non-5-digit (e.g. JPY-style 3-digit) symbols
- 🐛 Added broker stop/freeze-distance validation to avoid silent TP/SL rejections
- ♻️ Refactored info panel layout to eliminate label-overlap bugs

### v1.0.0 (2025-02-07)
- 🎉 Initial release
- ✅ Core TP/SL management
- ✅ Real-time monitoring
- ✅ Auto-close feature
- ✅ Auto-entry feature
- ✅ Full UI implementation

---

**Last Updated:** July 21, 2026
**Current Version:** 1.1.0
**Status:** Stable ✅
