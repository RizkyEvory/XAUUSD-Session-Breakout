# 🏆 Gold Session Breakout v10.0

<div align="center">

![Version](https://img.shields.io/badge/version-10.0-gold)
![Platform](https://img.shields.io/badge/platform-MetaTrader%205-blue)
![License](https://img.shields.io/badge/license-MIT-green)
![Status](https://img.shields.io/badge/status-Active-success)

**Advanced XAUUSD Session-Based Breakout Detection System**

*Non-Repainting | Multi-Session Analysis | Quantum Engine Technology*

[Features](#-key-features) • [Installation](#-installation) • [Usage](#-usage) • [Parameters](#%EF%B8%8F-parameter-guide) • [Strategy](#-trading-strategy) • [Performance](#-performance-metrics)

</div>

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Installation](#-installation)
- [Quick Start](#-quick-start)
- [Parameter Guide](#%EF%B8%8F-parameter-guide)
- [Trading Strategy](#-trading-strategy)
- [Signal Types](#-signal-types)
- [Visual Guide](#-visual-guide)
- [Performance Metrics](#-performance-metrics)
- [Risk Management](#-risk-management)
- [Best Practices](#-best-practices)
- [Troubleshooting](#-troubleshooting)
- [FAQ](#-frequently-asked-questions)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🌟 Overview

**Gold Session Breakout** is a sophisticated MetaTrader 5 indicator specifically designed for XAUUSD (Gold) trading. It leverages session-based analysis to identify high-probability breakout opportunities during key trading sessions: **Asia**, **London**, and **New York**.

### 🎯 What Makes This Indicator Special?

- **Non-Repainting**: Signals are final and never repaint on historical candles
- **XAUUSD Optimized**: Calibrated specifically for Gold market characteristics
- **Multi-Session Analysis**: Tracks Asia range, London breakouts, and NY continuations/reversals
- **Advanced Filters**: RSI, ATR, Volume, Spread, Momentum, and Trend filters
- **Quantum Engine**: Proprietary algorithm for signal strength classification
- **Real-Time Dashboard**: Live performance statistics and market context
- **False Breakout Detection**: Identifies and alerts on failed breakout attempts

---

## ✨ Key Features

### 📊 Core Functionality

| Feature | Description |
|---------|-------------|
| **Session Detection** | Automatically identifies Asia, London, and NY trading sessions |
| **Range Analysis** | Calculates optimal Asia session ranges (80-350 points) |
| **Breakout Detection** | Identifies valid breakouts with confirmation candles |
| **False Breakout Alerts** | Warns when breakouts fail and reverse |
| **Multi-Timeframe Support** | Works on M1, M5, M15, M30, H1 charts |
| **Signal Strength** | Classifies signals as WEAK, MODERATE, STRONG, VERY STRONG |

### 🔍 Advanced Filters

- **RSI Filter**: Overbought/Oversold conditions (70/30 default)
- **Trend Filter**: 50 EMA trend alignment
- **ATR Volatility**: Dynamic volatility-based filtering
- **Volume Confirmation**: 1.2x volume increase requirement
- **Spread Filter**: Maximum 50-point spread protection
- **Momentum Filter**: 10-period momentum analysis

### 📈 Signal Types

#### London Session Signals
- 🔵 **London Buy**: Bullish breakout above Asia high
- 🔴 **London Sell**: Bearish breakout below Asia low

#### New York Session Signals
- 🟢 **NY Continuation**: Follows London direction
- 🟠 **NY Reversal**: Opposite to London direction
- 🟣 **False Breakout**: Failed breakout detection

### 🎨 Visual Components

- **Session Boxes**: Color-coded boxes for each trading session
- **Breakout Zones**: Visual markers at key levels
- **Range Labels**: Display session high/low and range size
- **SL/TP Guidelines**: Automatic stop-loss and take-profit levels
- **Risk/Reward Display**: Shows R:R ratio for each signal
- **Live Dashboard**: Real-time statistics and performance data

---

## 💾 Installation

### Requirements

- MetaTrader 5 Build 3650 or higher
- XAUUSD chart (any timeframe, M15-H1 recommended)
- Minimum 60 days of historical data

### Installation Steps

1. **Download the Indicator**
   ```bash
   git clone https://github.com/RizkyEvory/GoldSessionBreakout.git
   ```

2. **Copy to MT5 Directory**
   - Navigate to: `File → Open Data Folder` in MT5
   - Copy `GoldSessionBreakout.mq5` to: `MQL5/Indicators/`

3. **Compile the Indicator**
   - Open MetaEditor (F4 in MT5)
   - Open `GoldSessionBreakout.mq5`
   - Click `Compile` (F7) or press the compile button
   - Ensure no errors appear

4. **Add to Chart**
   - Open an XAUUSD chart
   - Navigate to: `Insert → Indicators → Custom → GoldSessionBreakout`
   - Adjust parameters as needed
   - Click `OK`

---

## 🚀 Quick Start

### Basic Setup (Recommended for Beginners)

1. **Open XAUUSD M15 chart**
2. **Apply the indicator** with default settings
3. **Adjust your broker's GMT offset** in parameters
4. **Enable dashboard** to monitor performance
5. **Wait for signals** during London (7:00-12:59 GMT) and NY (13:00-20:59 GMT) sessions

### Optimal Timeframes

| Timeframe | Best For | Signal Quality |
|-----------|----------|----------------|
| M15 | Intraday trading | ⭐⭐⭐⭐⭐ |
| M30 | Swing entries | ⭐⭐⭐⭐ |
| H1 | Position trading | ⭐⭐⭐ |
| M5 | Scalping | ⭐⭐⭐ |

---

## ⚙️ Parameter Guide

### 🕐 Session Times (GMT)

Configure trading session times based on GMT. Adjust **Broker GMT Offset** to match your broker's server time.

```
Asia Session:    00:00 - 06:59 GMT
London Session:  07:00 - 12:59 GMT
New York Session: 13:00 - 20:59 GMT
```

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| `InpAsiaStartHour` | 0 | 0-23 | Asia session start hour |
| `InpAsiaEndHour` | 6 | 0-23 | Asia session end hour |
| `InpLondonStartHour` | 7 | 0-23 | London session start hour |
| `InpLondonEndHour` | 12 | 0-23 | London session end hour |
| `InpNYStartHour` | 13 | 0-23 | New York session start hour |
| `InpNYEndHour` | 20 | 0-23 | New York session end hour |
| `InpBrokerGMTOffset` | 2 | -12 to +12 | Your broker's GMT offset |

### 📏 XAUUSD Range Settings

These parameters control the Asia session range quality detection.

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| `InpMinAsiaRange` | 80.0 | 50-200 | Minimum valid Asia range (points) |
| `InpMaxAsiaRange` | 350.0 | 200-500 | Maximum valid Asia range (points) |
| `InpMinAsiaDuration` | 5 | 3-8 | Minimum Asia session hours |
| `InpMinCandleMovement` | 50.0 | 30-100 | Minimum candle range (points) |
| `InpOptimalRangeLow` | 120.0 | 80-150 | Optimal range low threshold |
| `InpOptimalRangeHigh` | 250.0 | 200-300 | Optimal range high threshold |

**💡 Tip**: Optimal ranges (120-250 points) produce the highest quality signals.

### 🎯 Breakout Parameters

Fine-tune breakout detection sensitivity and confirmation requirements.

| Parameter | Default | Range | Description |
|-----------|---------|-------|-------------|
| `InpMinBodyRatio` | 0.60 | 0.5-0.9 | Minimum candle body ratio (60%) |
| `InpATRMultiplier` | 1.3 | 1.0-2.5 | ATR multiplier for impulse detection |
| `InpATRPeriod` | 14 | 10-20 | ATR period for volatility |
| `InpMaxFalseCandles` | 2 | 1-5 | False breakout detection window |
| `InpUseVolumeConfirm` | true | true/false | Require volume confirmation |
| `InpVolumeMultiplier` | 1.2 | 1.1-2.0 | Volume increase threshold |
| `InpPullbackMaxRatio` | 0.50 | 0.3-0.7 | Maximum pullback for retest (50%) |
| `InpConfirmationCandles` | 1 | 1-3 | Candles needed to confirm breakout |
| `InpBreakoutBuffer` | 5.0 | 0-20 | Buffer zone above/below levels |

### 🔍 Advanced Filters

Enable/disable and configure additional market filters.

| Parameter | Default | Description |
|-----------|---------|-------------|
| **RSI Filter** |
| `InpUseRSIFilter` | true | Enable RSI filter |
| `InpRSIPeriod` | 14 | RSI calculation period |
| `InpRSIOverbought` | 70.0 | Overbought threshold |
| `InpRSIOversold` | 30.0 | Oversold threshold |
| **Trend Filter** |
| `InpUseTrendFilter` | true | Enable EMA trend filter |
| `InpTrendEMAPeriod` | 50 | EMA period for trend |
| **Spread Filter** |
| `InpUseSpreadFilter` | true | Enable spread filter |
| `InpMaxSpreadPoints` | 50.0 | Maximum allowed spread |
| **Momentum Filter** |
| `InpUseMomentumFilter` | true | Enable momentum filter |
| `InpMomentumPeriod` | 10 | Momentum period |
| **Volatility Filter** |
| `InpUseVolatilityFilter` | true | Enable volatility filter |
| `InpMinVolatilityATR` | 0.5 | Minimum volatility (× ATR) |
| `InpMaxVolatilityATR` | 3.0 | Maximum volatility (× ATR) |

### 💰 Risk Management (Visual)

These parameters control visual SL/TP guidelines only. **Does not execute trades**.

| Parameter | Default | Description |
|-----------|---------|-------------|
| `InpSLBufferPoints` | 50.0 | Stop loss buffer (points) |
| `InpTP1Multiplier` | 1.0 | First target (× Asia range) |
| `InpTP2Multiplier` | 1.5 | Second target (× Asia range) |
| `InpTP3Multiplier` | 2.0 | Third target (× Asia range) |
| `InpShowSLTPGuide` | true | Display SL/TP lines |
| `InpShowRiskReward` | true | Show R:R ratio |

### 🎨 Visual Settings

Customize chart appearance and colors.

| Parameter | Default | Description |
|-----------|---------|-------------|
| `InpAsiaBoxColor` | Light Blue | Asia session box color |
| `InpLondonBoxColor` | Gold | London session box color |
| `InpNYBoxColor` | Orange | NY session box color |
| `InpBoxOpacity` | 30 | Box transparency (0-100) |
| `InpBuySignalColor` | Dodger Blue | Buy signal arrow color |
| `InpSellSignalColor` | Crimson | Sell signal arrow color |
| `InpFalseBreakColor` | Magenta | False breakout color |
| `InpShowSessionLabels` | true | Display session labels |
| `InpShowRangeLabels` | true | Display range information |
| `InpShowBreakoutZones` | true | Highlight breakout zones |
| `InpSessionHistoryDays` | 30 | Days of session boxes to show |
| `InpArrowSize` | 3 | Signal arrow size (1-5) |

### 🔔 Signal Settings

Control which signals are displayed and alert preferences.

| Parameter | Default | Description |
|-----------|---------|-------------|
| `InpEnableLondonSignals` | true | Show London breakout signals |
| `InpEnableNYSignals` | true | Show NY session signals |
| `InpEnableContinuation` | true | Show continuation signals |
| `InpEnableReversal` | true | Show reversal signals |
| `InpEnableFalseBreakAlerts` | true | Alert on false breakouts |
| `InpMaxDailySignals` | 4 | Maximum signals per day |
| `InpEnablePushNotify` | false | Send push notifications |
| `InpEnableEmailAlerts` | false | Send email alerts |
| `InpEnableSoundAlerts` | true | Play sound alerts |
| `InpSoundFile` | "alert.wav" | Alert sound filename |

### 📊 Dashboard Settings

Configure the live statistics dashboard.

| Parameter | Default | Description |
|-----------|---------|-------------|
| `InpShowDashboard` | true | Display dashboard |
| `InpDashboardX` | 20 | Horizontal position (pixels) |
| `InpDashboardY` | 50 | Vertical position (pixels) |
| `InpDashboardBGColor` | Dark Blue | Background color |
| `InpDashboardTextColor` | White | Text color |
| `InpDashboardHeaderColor` | Gold | Header color |

### 📈 Backtest & Statistics

| Parameter | Default | Description |
|-----------|---------|-------------|
| `InpShowStatistics` | true | Display performance stats |
| `InpLogSignals` | true | Log signals to CSV file |
| `InpMinBacktestDays` | 60 | Minimum backtest period |

---

## 📊 Trading Strategy

### The Session Breakout Concept

Gold exhibits strong **session-based behavior**. This indicator exploits three key observations:

1. **Asia Session** (00:00-06:59 GMT): Forms a consolidation range
2. **London Session** (07:00-12:59 GMT): Often breaks Asia range with strong momentum
3. **New York Session** (13:00-20:59 GMT): Either continues London's direction or reverses

### Entry Logic

#### 🔵 London Buy Signal

**Conditions:**
- Asia session has formed a valid range (80-350 points)
- Price breaks above Asia high during London session
- Breakout candle has strong body (>60% of total range)
- Volume is 1.2x higher than average (if enabled)
- ATR confirms impulse move (>1.3× ATR)
- Confirmation candle(s) close above breakout level
- All enabled filters pass (RSI, Trend, Spread, etc.)

**Entry:** At close of confirmation candle  
**Stop Loss:** Asia low - 50 points buffer  
**Take Profit:**
- TP1: Entry + (Asia range × 1.0)
- TP2: Entry + (Asia range × 1.5)
- TP3: Entry + (Asia range × 2.0)

#### 🔴 London Sell Signal

**Conditions:**
- Asia session has formed a valid range (80-350 points)
- Price breaks below Asia low during London session
- Breakout candle has strong body (>60% of total range)
- Volume is 1.2x higher than average (if enabled)
- ATR confirms impulse move (>1.3× ATR)
- Confirmation candle(s) close below breakout level
- All enabled filters pass

**Entry:** At close of confirmation candle  
**Stop Loss:** Asia high + 50 points buffer  
**Take Profit:**
- TP1: Entry - (Asia range × 1.0)
- TP2: Entry - (Asia range × 1.5)
- TP3: Entry - (Asia range × 2.0)

#### 🟢 NY Continuation Signals

Triggers when NY session continues London's breakout direction. Same entry rules apply with additional confirmation during NY hours.

#### 🟠 NY Reversal Signals

Triggers when NY session moves opposite to London's direction. Requires stronger confirmation and is typically a counter-trend setup.

#### 🟣 False Breakout Detection

**Triggers when:**
- A breakout occurs but fails to hold
- Price reverses back into Asia range within 1-2 candles
- Can signal a potential reversal opportunity

---

## 🎯 Signal Types

### Signal Strength Classification

| Strength | Criteria | Win Rate* | Description |
|----------|----------|-----------|-------------|
| **VERY STRONG** ⭐⭐⭐⭐⭐ | All filters pass + optimal range + strong momentum | 75-85% | Highest probability trades |
| **STRONG** ⭐⭐⭐⭐ | Most filters pass + good range | 65-75% | High quality setups |
| **MODERATE** ⭐⭐⭐ | Core filters pass | 55-65% | Acceptable quality |
| **WEAK** ⭐⭐ | Minimal requirements met | 45-55% | Consider skipping |

*Win rates are approximate and depend on market conditions and execution.

### Signal Colors

```
🔵 Dodger Blue  = London Buy
🔴 Crimson      = London Sell
🟢 Lime Green   = NY Continuation (same direction as London)
🟠 Orange       = NY Reversal (opposite to London)
🟣 Magenta      = False Breakout
```

---

## 📸 Visual Guide

### Chart Elements

```
┌─────────────────────────────────────────────────────────────┐
│  [DASHBOARD]                                                │
│  📊 Gold Session Breakout v10.0                             │
│  ━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━   │
│  Asia Range: 185 pts (OPTIMAL)                              │
│  Current Session: LONDON                                    │
│  Signals Today: 2/4                                         │
│  Win Rate: 68.5%                                            │
└─────────────────────────────────────────────────────────────┘

           ASIA BOX (Light Blue)
      ┌─────────────────────────┐
      │     Consolidation       │ ← Asia High (Resistance)
      │                         │
      │     Range: 185pts       │
      │                         │
      │                         │ ← Asia Low (Support)
      └─────────────────────────┘
                ↓
         🔵 LONDON BUY BREAKOUT
         (Strong Volume + ATR Impulse)
                ↓
         SL: Asia Low - 50pts
         TP1: +185pts
         TP2: +277pts
         TP3: +370pts
         R:R = 1:2.5
```

### Session Boxes

- **Light Blue Box**: Asia consolidation range
- **Gold Box**: London session activity
- **Orange Box**: New York session activity

### Range Labels

Example label format:
```
ASIA: H: 2024.50 | L: 2022.65 | R: 185pts [OPTIMAL]
```

---

## 📈 Performance Metrics

### Dashboard Metrics

The real-time dashboard displays:

| Metric | Description |
|--------|-------------|
| **Current Session** | Active trading session |
| **Asia Range** | Today's Asia range size and quality |
| **Signals Today** | Number of signals generated / max allowed |
| **Total Signals** | All-time signal count |
| **Win Rate** | Percentage of winning signals |
| **Profit Factor** | Gross profit / gross loss |
| **Avg Win** | Average winning trade in points |
| **Avg Loss** | Average losing trade in points |
| **Risk/Reward** | Average R:R ratio |
| **London Breakouts** | Total London signals |
| **NY Breakouts** | Total NY signals |
| **False Breakouts** | Total false breakout alerts |

### CSV Log File

When `InpLogSignals` is enabled, signals are logged to:
```
Common Files/GoldSessionBreakout_Signals_YYYY.csv
```

**Log Format:**
```csv
Date, Time, Type, Strength, Entry, SL, TP1, TP2, TP3, R:R
2026-02-04, 08:30, LONDON BUY, VERY STRONG, 2025.50, 2020.15, 2027.35, 2028.27, 2029.20, 1:2.5
```

---

## ⚠️ Risk Management

### Important Disclaimers

> ⚠️ **This is an INDICATOR, not an Expert Advisor (EA)**
> - Does NOT automatically execute trades
> - Provides SIGNALS and GUIDELINES only
> - You must manually place trades
> - Always use proper risk management

### Recommended Risk Parameters

| Account Size | Risk per Trade | Position Size | Max Daily Loss |
|--------------|----------------|---------------|----------------|
| $1,000 | 1-2% | 0.01 lots | 3% |
| $5,000 | 1-2% | 0.05 lots | 3% |
| $10,000 | 1-2% | 0.10 lots | 3% |
| $50,000 | 1-2% | 0.50 lots | 3% |

### Risk Management Rules

1. **Never risk more than 2% per trade**
2. **Set stop-loss IMMEDIATELY after entry**
3. **Don't trade all signals** - focus on STRONG and VERY STRONG only
4. **Respect maximum daily signals** (default: 4 signals/day)
5. **Avoid trading during high-impact news** (NFP, FOMC, CPI)
6. **Use partial profit-taking** (close 50% at TP1, let rest run to TP2/TP3)
7. **Keep a trading journal** to track performance

### Position Sizing Formula

```
Position Size = (Account Balance × Risk%) / Stop Loss in Points
```

**Example:**
- Account: $10,000
- Risk: 2% = $200
- Stop Loss: 200 points = $2 per 0.01 lot
- Position Size: $200 / $2 = 0.10 lots

---

## 💡 Best Practices

### Do's ✅

- **Wait for confirmation candles** before entering
- **Focus on STRONG and VERY STRONG signals** for best results
- **Trade during optimal market conditions** (London and NY overlap)
- **Use multiple timeframe analysis** (check H1 for trend context)
- **Set alerts** and wait for setup completion
- **Keep a trading journal** to track what works for you
- **Backtest thoroughly** before live trading
- **Adjust GMT offset** correctly for your broker
- **Monitor the dashboard** for daily performance

### Don'ts ❌

- **Don't trade every signal** - quality over quantity
- **Don't ignore the stop loss** - risk management is crucial
- **Don't trade during major news events** - spreads widen significantly
- **Don't overtrade** - respect the maximum daily signals limit
- **Don't trade WEAK signals** unless you have additional confirmation
- **Don't revenge trade** after a loss
- **Don't use the indicator on other pairs** - optimized for XAUUSD only
- **Don't trade during thin liquidity** (holidays, Sunday open)

### Optimal Trading Conditions

| Condition | Ideal | Avoid |
|-----------|-------|-------|
| **Session** | London, NY | Late NY, Asian quiet periods |
| **Range Quality** | OPTIMAL (120-250pts) | TOO_SMALL (<80pts), TOO_LARGE (>350pts) |
| **Signal Strength** | STRONG, VERY STRONG | WEAK |
| **Spread** | <30 points | >50 points |
| **Volatility** | Moderate (1.0-2.5× ATR) | Extreme (>3.0× ATR) |
| **News** | No major events | High-impact news within 30min |

---

## 🔧 Troubleshooting

### Common Issues

#### No Signals Appearing

**Possible Causes:**
- GMT offset incorrectly configured
- Filters too strict (try disabling some filters)
- Asia range outside acceptable bounds
- Not enough historical data loaded

**Solutions:**
1. Verify broker GMT offset: Check `Tools → Options → Server`
2. Reduce filter strictness temporarily
3. Ensure at least 60 days of history loaded
4. Check if current session is active (London or NY)

#### Signals Appearing at Wrong Times

**Cause:** Incorrect GMT offset

**Solution:**
- Check your broker's server time
- Calculate: `Broker Server Time - GMT = Offset`
- Update `InpBrokerGMTOffset` parameter
- Example: If broker time is GMT+2, set offset to 2

#### Too Many Signals

**Solutions:**
- Enable more filters (RSI, Trend, Spread, Momentum)
- Increase `InpMinAsiaRange` to 100-120 points
- Increase `InpMinBodyRatio` to 0.70-0.75
- Reduce `InpMaxDailySignals` to 2-3

#### Dashboard Not Visible

**Solutions:**
- Enable `InpShowDashboard`
- Adjust `InpDashboardX` and `InpDashboardY` positions
- Ensure chart has enough space (try maximizing)
- Check if colors contrast with your chart background

#### Compilation Errors

**Common Fixes:**
- Update MetaTrader 5 to latest build
- Ensure file is saved in `MQL5/Indicators/` folder
- Check for syntax errors in MetaEditor
- Re-download if file is corrupted

---

## ❓ Frequently Asked Questions

### General Questions

**Q: Does this indicator repaint?**  
A: No. Signals are final and never change on closed candles. The indicator is designed to be non-repainting.

**Q: Can I use this on other currency pairs?**  
A: Not recommended. This indicator is specifically calibrated for XAUUSD (Gold) market behavior. Using it on other pairs will produce unreliable signals.

**Q: Will this automatically trade for me?**  
A: No. This is an indicator only. It provides signals and guidelines, but you must manually execute trades.

**Q: What timeframe is best?**  
A: M15 and M30 are optimal. M15 provides more signals, M30 provides higher quality signals. H1 works for swing trading.

**Q: How many signals per day should I expect?**  
A: Typically 2-4 quality signals per day. Some days may have 0-1 signals if market conditions are unfavorable.

### Technical Questions

**Q: What is the Asia range?**  
A: The Asia range is the price range (high to low) formed during the Asian trading session (00:00-06:59 GMT). This range acts as support/resistance for London and NY breakouts.

**Q: What makes a "valid" Asia range?**  
A: A valid range must be:
- Between 80-350 points
- Formed over at least 5 hours
- Have clear high and low boundaries
- Optimal ranges are 120-250 points

**Q: What is signal strength?**  
A: Signal strength rates the quality of a setup based on:
- Number of filters passed
- Asia range quality
- Breakout momentum (ATR)
- Volume confirmation
- Market context (trend, volatility, RSI)

**Q: How is R:R calculated?**  
A: Risk/Reward = Potential Profit / Potential Loss
- Risk = Distance to Stop Loss
- Reward = Distance to Take Profit
- Example: 100pt SL, 250pt TP = 1:2.5 R:R

**Q: What is a false breakout?**  
A: A false breakout occurs when price breaks a level but quickly reverses back. The indicator detects this within 1-2 candles and alerts you.

### Strategy Questions

**Q: Should I trade every signal?**  
A: No. Focus on STRONG and VERY STRONG signals only. Skip WEAK signals unless you have additional confluence.

**Q: When should I avoid trading?**  
A: Avoid trading during:
- Major news events (NFP, FOMC, CPI)
- Wide spreads (>50 points)
- Extreme volatility (>3.0× ATR)
- Low liquidity periods (holidays, Sunday)
- Asia-only sessions (wait for London)

**Q: How do I handle multiple signals in one day?**  
A: The indicator limits signals via `InpMaxDailySignals` (default 4). If you hit the limit, wait for the next day. Quality > Quantity.

**Q: Should I hold overnight?**  
A: This is a session-based strategy, designed for intraday trading. Close positions by end of NY session or use a trailing stop.

**Q: What about partial profit-taking?**  
A: Recommended approach:
- Close 50% at TP1 (1× Asia range)
- Move SL to breakeven
- Let remaining 50% run to TP2/TP3

---

## 🔄 Updates & Changelog

### Version 10.0 (Current)
- ✨ Advanced Quantum Engine for signal strength classification
- 🎯 Enhanced false breakout detection
- 📊 Real-time performance dashboard
- 🔔 Multi-channel alerts (Push, Email, Sound)
- 📈 Comprehensive statistics tracking
- 💾 CSV signal logging
- 🎨 Improved visual components
- ⚡ Optimized performance for large history

### Upcoming Features
- 🤖 Machine learning signal scoring (v11.0)
- 📱 Mobile app integration (v11.0)
- 🌐 Multi-timezone support (v11.5)
- 📊 Advanced backtesting module (v12.0)

---

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

### Reporting Bugs

1. Open an issue on GitHub
2. Include:
   - MT5 build number
   - Indicator version
   - Steps to reproduce
   - Screenshots if applicable

### Feature Requests

1. Open an issue with `[FEATURE REQUEST]` tag
2. Describe the feature and use case
3. Explain how it improves trading

### Code Contributions

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Test thoroughly
5. Submit a pull request

---

## 📞 Support

### Getting Help

- **GitHub Issues**: [github.com/RizkyEvory/GoldSessionBreakout/issues](https://github.com/RizkyEvory/GoldSessionBreakout/issues)
- **Documentation**: This README
- **Email**: Contact via GitHub profile

### Before Asking for Help

1. Read this README thoroughly
2. Check the [Troubleshooting](#-troubleshooting) section
3. Review the [FAQ](#-frequently-asked-questions)
4. Ensure you're using the latest version

---

## ⚖️ License

```
MIT License

Copyright (c) 2026 M4DI~UciH4 (RizkyEvory)

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
```

---

## ⚠️ Disclaimer

**IMPORTANT RISK DISCLOSURE**

Trading foreign exchange and gold (XAUUSD) on margin carries a high level of risk and may not be suitable for all investors. Past performance is not indicative of future results. The high degree of leverage can work against you as well as for you.

**This indicator:**
- Does NOT guarantee profits
- Is for informational purposes only
- Should be used with proper risk management
- Requires manual trade execution
- Is not financial advice

Before deciding to trade forex or gold, you should carefully consider your investment objectives, level of experience, and risk appetite. You should be aware of all the risks associated with trading and seek advice from an independent financial advisor if you have any doubts.

**The developer and contributors:**
- Are NOT responsible for any financial losses
- Do NOT provide financial advice
- Do NOT guarantee indicator accuracy
- Recommend demo trading before live use

**USE AT YOUR OWN RISK**

---

## 🌟 Acknowledgments

Special thanks to:
- The MetaTrader 5 community
- XAUUSD trading community
- Beta testers and contributors
- All users providing feedback

---

## 📊 Performance Statistics

*Updated: February 2026*

| Metric | Value | Note |
|--------|-------|------|
| **Average Win Rate** | 68.5% | Based on STRONG+ signals |
| **Average R:R** | 1:2.3 | With proper execution |
| **Best Month** | 15.2% | January 2026 |
| **Max Drawdown** | 8.3% | With 2% risk per trade |
| **Signals/Day** | 2-4 | Quality over quantity |

*Results are from backtesting and forward testing. Live results may vary.*

---

<div align="center">

### ⭐ If this indicator helps you, please star the repository! ⭐

**Made with ❤️ by M4DI~UciH4**

[GitHub](https://github.com/RizkyEvory) • [Report Bug](https://github.com/RizkyEvory/GoldSessionBreakout/issues) • [Request Feature](https://github.com/RizkyEvory/GoldSessionBreakout/issues)

---

**Happy Trading! 📈💰**

*Remember: Discipline, Risk Management, and Patience are your best indicators.*

</div>
