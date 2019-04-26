# API

If you have any questions please ask in the Development channel of the [Discord](https://discord.gg/crjsdJr). We also give airdrops to developers who are interested in building on P3C.

## Price Oracle

GET `https://api.p3c.io/chart/info`

This returns the current supply of P3C, the USD Price, the ETC Price, the ETC Market cap, the ETC market cap, and ETC price in USD.

## Historical Price Information (for making charts)

GET `https://api.p3c.io/chart/ohlc`

This returns an array of the open, high, low, and close of the P3C token, denominated in USD. Measurements are made daily.

## Known Crops/Accounts

GET `https://api.p3c.io/farm/crops`

This returns a list of all of the created crops.

## Crop Value over time.

GET `https://api.p3c.io/price/crop/0xB751eb15542D3fba12065A63f87E0b059c04091C`

Can be called on any crop. Returns the growth in ETC/USD over a 1 day, 7 day, and 30 day period.

GET `https://api.p3c.io/price/crop/`

Returns prices information for all crops.

## P3C Ad 

GET `https://api.p3c.io/sponsor/`

Returns sponsor information as raw HTML. This can be loaded into page with

```
<div class="ui horizontal segment">
  <div id="sponsor" class="sponsor"></div>
    <span class="ui text blue small" style="float: right"><a href="https://p3c.io/sponsor.html" target="_blank">Buy this sponsorship instantly with ETC!</a>
    </span>
</div>
```
and 

`$('#sponsor').load("https://api.p3c.io/sponsor/")`




