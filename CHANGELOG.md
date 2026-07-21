# Changelog

All notable changes to MT_MANAGER will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.1.0] - 2026-07-21

### Added
- **Position Filter**
  - `MagicNumber` input to manage only positions opened by a specific EA/magic number (default `0` keeps the v1.0.0 behavior of managing all positions on the symbol)
- **Break Even Automation**
  - `EnableBreakEven`, `BreakEvenTriggerPips`, `BreakEvenOffsetPips` inputs
  - Moves SL to entry (plus a configurable offset) once a position reaches a target profit in pips; SL only ever moves in the favorable direction
- **Trailing Stop**
  - `EnableTrailingStop`, `TrailingStartPips`, `TrailingStepPips` inputs
  - Keeps SL a fixed distance behind price once a position is far enough in profit
- **Max Spread Filter**
  - `EnableMaxSpreadFilter`, `MaxSpreadPips` inputs
  - Skips (and later retries) Auto Entry while the spread is wider than the configured threshold
- **Sound Alerts**
  - `EnableSoundAlerts` input
  - Audible confirmation on Close All, Auto Close, Auto Entry, and Break Even events
- **Live Floating P/L**
  - New info panel line showing the real, current profit/loss of open positions (previously the panel only showed a hypothetical profit/loss *if* TP/SL were hit)
- **Status Line**
  - New info panel line summarizing which automations (Magic filter, Break Even, Trailing Stop, Auto Close, Auto Entry, Spread Filter) are currently active

### Fixed
- Pip calculations (`TP Pips` / `SL Pips`, and `EntryTPPips` / `EntrySLPips` for Auto Entry) were hardcoded for 5-digit brokers and produced 10x wrong values on 4-digit or 2-digit quote symbols; pip size is now derived from the symbol's actual digit count
- TP/SL modifications that were too close to the current market price failed silently with a generic broker error; they are now validated against the symbol's stop/freeze level beforehand and skipped with a clear, actionable log message

### Changed
- Refactored the info panel's label layout to use a running vertical offset instead of hand-tuned magic-number coordinates, removing the root cause of the previously reported panel text overlap issue
- Source code (`MT_MANAGER.mq5`) is now part of this repository again; see [README's License section](README.md#-license) and [LICENSE](LICENSE) for updated terms (still freeware, still no redistribution/resale, but source-available rather than closed-source)

---

## [1.0.0] - 2025-02-07

### Added
- **Core Position Management**
  - Unified TP/SL setting for all positions on current symbol
  - Interactive input boxes with Enter key support
  - Auto-detection of existing TP/SL from positions on startup
  - One-click Close All button

- **Real-Time Monitoring**
  - Live profit/loss tracking in account currency (USD/EUR/etc)
  - Profit/loss calculation in pips
  - Total positions count display
  - Total lot size display
  - Real-time spread monitoring in pips
  - Candle close countdown (HH:MM:SS format)
  - Market close countdown (until Friday 23:59)
  - Market open countdown (during weekends until Monday 00:00)

- **Automation Features**
  - Auto Close at Time: Close all positions at specified time daily
  - Auto Entry After Weekend: Open position when market reopens Monday
  - Smart entry execution (waits for price to reach entry level)

- **User Interface**
  - Clean borderless panel design
  - Dual panel layout (controls left, info right)
  - Color-coded information (green=profit, red=loss, yellow=alerts)
  - Non-intrusive display

- **Documentation**
  - Comprehensive README.md
  - Freeware License file
  - Changelog file
  - Installation guide
  - Usage scenarios
  - FAQ section

### Technical Details
- Language: MQL5
- Platform: MetaTrader 5
- Lines of Code: ~1,250
- Dependencies: Trade.mqh (standard library)

### Configuration Options
- TargetTP: Default TP price (default: 0.0 = auto-detect)
- TargetSL: Default SL price (default: 0.0 = auto-detect)
- EnableAutoClose: Enable auto-close feature (default: false)
- AutoCloseTime: Time to close all positions (default: "23:00")
- EnableAutoEntry: Enable auto-entry feature (default: false)
- EntryType: BUY or SELL (default: ORDER_TYPE_BUY)
- EntryPrice: Target entry price (default: 0.0)
- EntryLot: Lot size for auto-entry (default: 0.01)
- EntryTPPips: TP in pips from entry (default: 30)
- EntrySLPips: SL in pips from entry (default: 20)

### Known Issues
- None reported

---

## [Unreleased]

### Planned for v2.0
- Partial Close functionality
- Account info panel
- One-click trading
- Session time indicator
- Max drawdown protection
- Email/Telegram notifications
- Daily statistics
- Correlation monitor

---

## Version History Summary

- **v1.1.0** (2026-07-21) - Break Even, Trailing Stop, Magic Number filter, spread filter, sound alerts, live floating P/L, pip-calculation fix
- **v1.0.0** (2025-02-07) - Initial stable release with core features

---

**Note:** For detailed information about each version, see the [README](README.md) roadmap section.
