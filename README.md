# API

If you have any questions please ask in the Development channel of the [Discord](https://discord.gg/crjsdJr). We also give airdrops to developers who are interested in building on P3C. You can also read our [Commercial Best Practices document](https://medium.com/@masterhax/p3c-io-commercial-best-practices-5e52cff29bb8) if you are looking to build an app of business on top of P3C. Developers are also encouraged to use the P3C Pure interface (https://p3c.io/pure.html) which allows for direct connection between wallet and smart contract. [Learn more about the Pure UI](https://medium.com/@masterhax/introducing-p3c-pure-a-ui-for-exchanges-merchants-and-devs-4e150093b2d0).

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

## Referral Bonus from Community Fee

If a user goes to `https://p3c.io/use.html?ref=0x5136958e5D57fa1E282fA976a3985Ca5B395132A` 

The crop address in the URL receieves 33% of the 10% community fee (3% of funds spent to purchase new P3C). This can be used by anyone building something that links to P3C. Keep in mind, this does not affect how much P3C the user gets back, only how much goes to the community fee.

The link can be created via the [Pure](https://p3c.io/pure.html) interface, and requires 1 P3C to be held in the pure account to be active. All bonuses from purchases through the link appear as dividends on the pure interface.

## DappDirect.net Ethereum Classic Smart Contract Digest 

GET `https://api.p3c.io/dappdirect/etc/digest`

Returns a JSON array of all of the contracts, along with their 72 hour volume, balance, and unique users.

## P3C.tv Get Current channel

GET `https://api.p3c.io/tv/`
Returns a JSON object with the current youtube livestream id, the tip amount in USD cents, and the crop to send it to. 

## P3C.tv Change current channel

GET `http://api.p3c.io/tv/use/fnh4V3u9lA4/2/0x5136958e5D57fa1E282fA976a3985Ca5B395132A`

GET `http://api.p3c.io/tv/use/{videoId}/{TipAmountUSDCents}/{cropAddress}`

This sets the channel, tip destination, and tip amount in USD for when a user pays for a tip. Call this to change where the channel is pointing.

* Would set the current channel on https://p3c.tv/ to the livestream ID of `qK9OLRbAW30`
* Every tip is `2` cents USD. 
* When user pays tip, ETC from their wallet is converted into p3c and 50% is sent to `0x5136958e5D57fa1E282fA976a3985Ca5B395132A` and 50% is sent back ot them.

You can get the livestream ID from any youtube livestream URL by taking it off of the end https://www.youtube.com/watch?v=qK9OLRbAW30 . Livestreamer must have enabled embedding.

## P3C.tv - Create a Tippable Link

`https://p3c.tv/index.html?crop=0x5136958e5D57fa1E282fA976a3985Ca5B395132A&tip=5&id=fEvM-OUbaKs`

This creates a link which will override the server set channel when a user clicks on it. This link can be created manually and there *are no checks* performed when a user accesses and tips through the link. Funds from tips will be sent directly to the Crop Address in the URL. Follows the same economic parameters as the server-based link.

A user can create a tippable link by:

`https://p3c.tv/index.html?crop={cropAddress}&tip={tipAmountUSDCents}&id={VideoID}`
