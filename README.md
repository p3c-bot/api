# API

If you have any questions please ask in the Development channel of the [Discord](https://discord.gg/crjsdJr). We also give airdrops to developers who are interested in building on P3C.

## Price Oracle

GET `http://api.p3c.io/airdrop/info`

This returns the current supply of P3C, the USD Price, the ETC Price, the ETC Market cap, the ETC market cap.

## Known Crops/Accounts

GET `https://api.p3c.io/farm/crops`

This returns a list of all of the created crops.

## Crop Value over time.

GET `https://api.p3c.io/price/crop/0xB751eb15542D3fba12065A63f87E0b059c04091C`

Can be called on any crop. Returns the growth in ETC/USD over a 1 day, 7 day, and 30 day period.
