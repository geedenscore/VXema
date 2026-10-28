# VXema — Multi-Timeframe EMA

A TradingView indicator (Pine Script v6) that draws **one EMA length across as many timeframes as you choose**, all on a single chart. You get, for example, the real 15m, 1h and 4h EMA 200 together on a 1m chart.

## What it does

Pick an EMA length once and tick the timeframes you want. Each line is that timeframe's own EMA, not an approximation:

- **True higher-timeframe EMAs.** Above the chart timeframe, each line is pulled from that timeframe's own data. A 1h EMA 200 on a 1m chart would otherwise need 12,000 chart candles to compute, more than TradingView loads. VXema uses the 1h series' own history, so it's always correct.
- **Non-repainting.** HTF values come from the last closed candle of that timeframe only.
- **Smooth or stepped.** A higher-timeframe EMA normally only updates once per HTF candle, which draws as a staircase on a lower chart.
  - **Smooth (default):** the same EMA re-run at chart resolution with an identical time constant, fed by every chart close and seeded from the HTF value so it's correct from the first bar. Nothing is averaged away.
  - **Stepped:** the literal HTF value, flat between HTF closes.
- **Lower timeframes scaled down.** Timeframes below the chart can be redrawn with the length divided by the timeframe ratio (a 15m EMA 200 on a 4h chart becomes a 13-length EMA, shown in the label), or hidden.
- **11 rows.** Chart, 1m, 3m, 5m, 10m, 15m, 30m, 1h, 2h, 4h and D, each with its own colour, line style (solid, dashed, dotted) and thickness.
- **Labels.** Tag, badge or text-only labels, placed past the live candle or pinned to the left or centre of the visible chart.

## Key settings

| Setting | What it controls |
|---|---|
| EMA length | The one length applied to every ticked timeframe (default 200) |
| Source | Price source for the EMA |
| Line detail | Smooth or Stepped rendering of higher-timeframe EMAs |
| Timeframes below chart TF | Scale down or Hide |
| Timeframes | Per-row enable, colour, style and thickness |
| Labels | Style, position, offset, size and text colour |

## Installation

1. Open TradingView and go to **Pine Editor**.
2. Paste the contents of `VXema.pine`.
3. Click **Add to chart**.

## License

[Creative Commons Attribution-NonCommercial-ShareAlike 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0/). Free to use and adapt for non-commercial purposes with attribution.

## Disclaimer

This indicator is for educational and informational purposes only and is not financial advice. Trading futures and other leveraged products carries substantial risk of loss.
