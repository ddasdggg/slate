---
title: Bitmusa API Documentation

toc_footers:
  - <a href='https://bitmusa.com'>Bitmusa</a>

includes:
  - error

search: true

code_clipboard: true

meta:
  - name: Bitmusa API Documentation
  - content: Bitmusa API Documentation
---

# Introduction
## API Key Setup
- Some endpoints will require an API Key.
- For security on the generated API Key, it is recommended to set IP restrictions on the key.
- Never share your API key/secret key to ANYONE.
- Please refer to [this page](https://bitmusa.com) regarding API key creation.

<aside class="warning">
If your API key is inadvertently exposed, delete it immediately and generate a new key.
</aside>

# General Info
## General API Information
- Base API URL
  - ```https://api.bitmusa.com/api/v1```
- All endpoints return either a JSON object or array.
- Data is returned in descending order. The largest or newest comes first, the smallest or oldest last.

## Error Code and Messages
- If there is an error, the API will return an error with a message of the reason.
- Specific error codes and messages defined in [Error Code](#error-code) Error Code.

## General Information on Endpoints
- For ```GET```, ```POST```, ```PUT``` endpoints, the parameters may be sent as a query string or in the request body

## Endpoint security type
- API key are passed into the Rest API via the ```x-api-key``` header.

# Market Endpoint
## Spot Coins Information
Get information of coins

> Response

```json
[
  {
    "name": "USDT",
    "nameCn": "USDT",
    "unit": "USDT",
    "status": 0,
    "minTxFee": 5.0,
    "maxTxFee": 5.0,
    "cnyRate": 0.0,
    "usdRate": 1.0,
    "enableRpc": 1,
    "sort": 0,
    "canSend": 1,
    "canWithdraw": 1,
    "canRecharge": 1,
    "canTransfer": 1,
    "canAutoWithdraw": 0,
    "withdrawScale": 6,
    "withdrawThreshold": 1.0,
    "minWithdrawAmount": 50.0,
    "maxWithdrawAmount": 10000.0,
    "minRechargeAmount": 1.0,
    "isPlatformCoin": 1,
    "isToken": 1,
    "hasLegal": false,
    "allBalance": null,
    "coldWalletAddress": "",
    "hotAllBalance": null,
    "blockHeight": null,
    "minerFee": null,
    "infolink": "",
    "information": "USDT",
    "accountType": 0,
    "depositAddress": null,
    "memoAdjust": null,
    "scanTxidWeburl": "https://etherscan.io/tx/",
    "scanAddressWeburl": "https://etherscan.io/address/",
    "visible": 1,
    "testMode": 0,
    "networkCoins": [
      {
        "networkCoin": "ETH",
        "info": "Ethereum (ERC20)"
      },
      {
        "networkCoin": "TRX",
        "info": "Tron (TRC20)"
      }
    ],
    "icon": "https://dev-static.neonexteam.com/image/coin/USDT.svg",
    "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg",
    "spotTradable": false
  },
  {
    "name": "Bitcoin",
    "nameCn": "Bitcoin",
    "unit": "BTC",
    "status": 0,
    "minTxFee": 0.001,
    "maxTxFee": 0.001,
    "cnyRate": 0.0,
    "usdRate": 20284.93,
    "enableRpc": 1,
    "sort": 1,
    "canSend": 1,
    "canWithdraw": 1,
    "canRecharge": 1,
    "canTransfer": 0,
    "canAutoWithdraw": 0,
    "withdrawScale": 5,
    "withdrawThreshold": 0.1,
    "minWithdrawAmount": 2.0E-5,
    "maxWithdrawAmount": 10.0,
    "minRechargeAmount": 1.0E-6,
    "isPlatformCoin": 1,
    "isToken": 0,
    "hasLegal": false,
    "allBalance": null,
    "coldWalletAddress": "",
    "hotAllBalance": null,
    "blockHeight": null,
    "minerFee": null,
    "infolink": "",
    "information": "BTC",
    "accountType": 0,
    "depositAddress": "mi1Q3VpBYr7XJL9pP51Vpw1WLc1eXSQxzX",
    "memoAdjust": null,
    "scanTxidWeburl": "https://www.blockchain.com/btc/tx/",
    "scanAddressWeburl": "https://www.blockchain.com/btc/address/",
    "visible": 1,
    "testMode": 0,
    "networkCoins": [],
    "icon": "https://dev-static.neonexteam.com/image/coin/BTC.svg",
    "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg",
    "spotTradable": true
  }
]
```

```GET /spot/coins```

## Spot Coin Information
Get information of coin

> Response

```json
{
  "name": "Bitcoin",
  "nameCn": "Bitcoin",
  "unit": "BTC",
  "status": 0,
  "minTxFee": 0.001,
  "maxTxFee": 0.001,
  "cnyRate": 0.0,
  "usdRate": 0.0,
  "enableRpc": 1,
  "sort": 1,
  "canSend": 1,
  "canWithdraw": 1,
  "canRecharge": 1,
  "canTransfer": 0,
  "canAutoWithdraw": 0,
  "withdrawScale": 5,
  "withdrawThreshold": 0.1,
  "minWithdrawAmount": 2.0E-5,
  "maxWithdrawAmount": 10.0,
  "minRechargeAmount": 1.0E-6,
  "isPlatformCoin": 1,
  "isToken": 0,
  "hasLegal": false,
  "allBalance": null, 
  "coldWalletAddress": "",
  "hotAllBalance": null,
  "blockHeight": null,
  "minerFee": null,
  "infolink": "",
  "information": "BTC",
  "accountType": 0,
  "depositAddress": "mi1Q3VpBYr7XJL9pP51Vpw1WLc1eXSQxzX",
  "memoAdjust": null,
  "scanTxidWeburl": "https://www.blockchain.com/btc/tx/",
  "scanAddressWeburl": "https://www.blockchain.com/btc/address/",
  "visible": 1,
  "testMode": 0,
  "networkCoins": null,
  "icon": "https://dev-static.neonexteam.com/image/coin/BTC.svg",
  "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg",
  "spotTradable": null
}
```

```GET /spot/coins/{SYMBOL}```

## Future Coin Information
Get information of coin

> Response

```json
[
  {
    "name": "USDT",
    "unit": "USDT",
    "sort": 0,
    "withdrawScale": 4,
    "withdrawThreshold": 10000000,
    "minWithdrawAmount": 10,
    "maxWithdrawAmount": 100,
    "cnyRate": 0.0,
    "usdRate": 0.0,
    "icon": "https://dev-static.neonexteam.com/image/coin/USDT.svg",
    "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg"
  }
]
```

```GET /future/coins```

## Spot ticker Information
Get information of ticker

> Response

```json
[
  {
    "symbol": "BTC/USDT",
    "coinSymbol": "BTC",
    "baseSymbol": "USDT",
    "enable": 1,
    "exchangeable": 1,
    "sort": 1,
    "coinScale": 5,
    "baseCoinScale": 2,
    "icon": "https://dev-static.neonexteam.com/image/coin/BTC.svg",
    "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg"
  },
  {
    "symbol": "ETH/USDT",
    "coinSymbol": "ETH",
    "baseSymbol": "USDT",
    "enable": 1,
    "exchangeable": 1,
    "sort": 2,
    "coinScale": 4,
    "baseCoinScale": 2,
    "icon": "https://dev-static.neonexteam.com/image/coin/ETH.svg",
    "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg"
  }
]
```

```GET /spot/ticker```

## Future ticker Information
Get information of ticker

> Response

```json
[
  {
    "id": 1,
    "ticker": "BTCUSDT",
    "base_symbol": "USDT",
    "coin_symbol": "BTC"
  },
  {
    "id": 2,
    "ticker": "ETHUSDT",
    "base_symbol": "USDT",
    "coin_symbol": "ETH"
  }
]
```

```GET /future/ticker```

## Spot Latest Trade Information
Get information of The Latest Trade

> Response

```json
[
  {
    "symbol": "BTC/USDT",
    "open": 23750.66,
    "high": 23750.66,
    "low": 19782.59,
    "close": 20024.22,
    "chg": -0.1622,
    "change": -3726.44,
    "volume": 5363.5369,
    "turnover": 1.090050297121894E8,
    "lastDayClose": 23898.99,
    "usdRate": 20024.22,
    "baseUsdRate": 1,
    "zone": 0,
    "baseCoinScale": 2
  },
  {
    "symbol": "ETH/USDT",
    "open": 1565.68,
    "high": 1565.68,
    "low": 1413.64,
    "close": 1424.01,
    "chg": -0.0905,
    "change": -141.67,
    "volume": 12301.5638,
    "turnover": 2.0499971019869E7,
    "lastDayClose": 1565.69,
    "usdRate": 1424.01,
    "baseUsdRate": 1,
    "zone": 0,
    "baseCoinScale": 2
  }
]
```

```GET /spot/conclusion/last```

## Spot Price Information
Get information of Price

> Response

```json
[
  {
    "symbol": "BTC/USDT",
    "open": 0,
    "high": 0,
    "low": 0,
    "close": 20284.93,
    "chg": 0,
    "change": 0,
    "volume": 0.0,
    "turnover": 1.885732163209894E8,
    "lastDayClose": 20284.93,
    "usdRate": 20284.93,
    "baseUsdRate": 1,
    "zone": 0,
    "baseCoinScale": 2
  },
  {
    "symbol": "ETH/USDT",
    "open": 0,
    "high": 0,
    "low": 0,
    "close": 1408.83,
    "chg": 0,
    "change": 0,
    "volume": 0.0,
    "turnover": 7.6566709455669E7,
    "lastDayClose": 1408.83,
    "usdRate": 1408.83,
    "baseUsdRate": 1,
    "zone": 0,
    "baseCoinScale": 2
  }
]
```

```GET /spot/price```

## Spot Orderbook Information
Get information of Orderbook

> Response

```json
{
  "ask": {
    "direction": "SELL",
    "maxAmount": 99.44249,
    "minAmount": 2.0E-4,
    "highestPrice": 20100.0,
    "lowestPrice": 20054.12,
    "symbol": "BTC/USDT",
    "items": [
      {
        "price": 20054.12,
        "amount": 0.00328
      }
    ]
  },
  "bid": {
    "direction": "BUY",
    "maxAmount": 28.449,
    "minAmount": 5.0E-4,
    "highestPrice": 20053.48,
    "lowestPrice": 20000,
    "symbol": "BTC/USDT",
    "items": [
      {
        "price": 20053.48,
        "amount": 1.96376
      }
    ]
  }
}
```

```GET /spot/order-book/{ticker}```

## Future Price Information
Get information of Price

> Response

```json
[
  {
    "pk": "01GV51JC0TDG08K9V68ZG26T7Y",
    "ticker": "BTCUSDT",
    "base_price": 0,
    "high_price": 0,
    "low_price": 0,
    "last_price": 0,
    "mark_price": 20045.61738,
    "index_price": 20045.61738,
    "funding_fee_rate": 0,
    "funding_time": 1678417200000,
    "remaining_funding_time": 2797984,
    "change_price": 0,
    "change_rate": 0,
    "total_qty": 0,
    "total_value": 0,
    "last_updated_time": 1678418002016
  },
  {
    "pk": "01GV51JBJ5H29CYTGANHPT9YCP",
    "ticker": "ETHUSDT",
    "base_price": 0,
    "high_price": 0,
    "low_price": 0,
    "last_price": 0,
    "mark_price": 1425.69211,
    "index_price": 1425.69211,
    "funding_fee_rate": 0,
    "funding_time": 1678417200000,
    "remaining_funding_time": 2797979,
    "change_price": 0,
    "change_rate": 0,
    "total_qty": 0,
    "total_value": 0,
    "last_updated_time": 1678418002021
  }
]
```

```GET /future/price```

## Future Ticker Price Information
Get information of Price

> Response

```json
{
  "pk": "01GV51JBJ5H29CYTGANHPT9YCP",
  "ticker": "BTCUSDT",
  "base_price": 20015.7,
  "high_price": 20052.3,
  "low_price": 20013.0,
  "last_price": 20451.3,
  "mark_price": 20497.77833333,
  "index_price": 22271.0,
  "funding_fee_rate": 1.0E-4,
  "funding_time": 1678428000000,
  "remaining_funding_time": 3446349,
  "change_price": 435.6,
  "change_rate": 2.1763,
  "total_qty": 158678.045,
  "total_value": 3.229769364407E9,
  "last_updated_time": 1678676553651
}
```

```GET /future/price/{ticker}```

## Future Orderbook Scale Information
Get information of orderbook Scale

> Response

```json
[
  {
    "scale": 0.1
  },
  {
    "scale": 1.0
  },
  {
    "scale": 10.0
  },
  {
    "scale": 50.0
  },
  {
    "scale": 100.0
  }
]
```

```GET /future/order-book/scale/{ticker}```

## Future Orderbook Information
Get information of Future orderbook

> Response

```json
{
  "sell": [
    {
      "payload": null,
      "price": "29000.0",
      "ticker": "BTCUSDT",
      "amount": "29000.0",
      "qty": "1.0",
      "total": 2195361.0461,
      "total_qty": 106.937,
      "position": "1",
      "scale": "1",
      "updated_time": "1678438966233",
      "mode": "add"
    }
  ],
  "buy": [
    {
      "payload": null,
      "price": "20451",
      "ticker": "BTCUSDT",
      "amount": "2045.13",
      "qty": "0.1",
      "total": 2045.13,
      "total_qty": 0.1,
      "position": "0",
      "scale": "1",
      "updated_time": "1678675428190",
      "mode": "add"
    }
  ]
}
```

```GET /future/order-book/{ticker}```

### Parameter:

| Name    | Type        | Required | Description |
|---------|-------------|----------|-------------|
| scale   | Decimal     | Yes      | price scale |
| size    | Integer     | No       | default 50  |

# User Endpoint

## Profile Information
Get information of profile

> Response

```json
{
  "data": {
    "username": null,
    "nickname": "site-ppp",
    "id": 83037,
    "createTime": null,
    "realVerified": null,
    "emailVerified": 1,
    "phoneVerified": 1,
    "loginVerified": 1,
    "fundsVerified": 0,
    "realAuditing": null,
    "mobilePhone": "+**-**********",
    "email": "***@neonex.team",
    "realName": null,
    "realNameRejectReason": null,
    "idCard": null,
    "avatar": null,
    "accountVerified": null,
    "googleStatus": 1,
    "countryCode": "82"
  },
  "code": 0,
  "message": "SUCCESS"
}
```

```GET /member```

### Headers:
| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Favorite Ticker
Get information of user favorite ticker

> Response

```json
[
  "BTCUSDT",
  "ETCUSDT"
]
```

```GET /member/favorite```

### Headers:
| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Add Favorite Ticker
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```PUT /member/favorite```

### Headers:
| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:
| Name   | Type   | Required | Description |
|--------|--------|----------|-------------|
| ticker | String | Yes      |             |

## Delete Favorite Ticker
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```DELETE /member/favorite```

### Headers:
| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:
| Name   | Type   | Required | Description |
|--------|--------|----------|-------------|
| ticker | String | Yes      |             |

# Asset Endpoint

## Wallets
Get Information of Spot / Future Wallet
> Response

```json
{
  "spot": [
    {
      "id": 2286,
      "memberId": 83037,
      "coin": {
        "name": "Bitcoin",
        "nameCn": "Bitcoin",
        "unit": "BTC",
        "status": 0,
        "minTxFee": 0.001,
        "maxTxFee": 0.001,
        "cnyRate": 0.0,
        "usdRate": 20284.93,
        "enableRpc": 1,
        "sort": 1,
        "canSend": 1,
        "canWithdraw": 1,
        "canRecharge": 1,
        "canTransfer": 0,
        "canAutoWithdraw": 0,
        "withdrawScale": 5,
        "withdrawThreshold": 0.10000000,
        "minWithdrawAmount": 0.00002000,
        "maxWithdrawAmount": 10.00000000,
        "minRechargeAmount": 0.00000100,
        "isPlatformCoin": 1,
        "isToken": 0,
        "hasLegal": false,
        "allBalance": null,
        "coldWalletAddress": "14QZK9h8udeB6riNfrNRYhK5ptHzJTmjM5",
        "hotAllBalance": null,
        "blockHeight": null,
        "minerFee": null,
        "infolink": "",
        "information": "BTC",
        "accountType": 0,
        "depositAddress": "mi1Q3VpBYr7XJL9pP51Vpw1WLc1eXSQxzX",
        "memoAdjust": null,
        "scanTxidWeburl": "https://www.blockchain.com/btc/tx/",
        "scanAddressWeburl": "https://www.blockchain.com/btc/address/",
        "visible": 1,
        "testMode": 0,
        "networkCoins": null,
        "icon": null,
        "defaultIcon": null,
        "spotTradable": null
      },
      "balance": 0E-16,
      "frozenBalance": 0E-16,
      "lockedBalance": 0E-16,
      "toReleased": 0E-8,
      "networkCoin": null,
      "address": "",
      "tag": null,
      "memo": null,
      "isLock": 0
    }
  ],
  "futures": [
    {
      "symbol": "USDT",
      "position": [],
      "total_wallet_balance": 100000.0,
      "total_margin_balance": 100000.0,
      "total_available_balance": 100000.0,
      "total_unpnl": 0
    }
  ]
}
```

```GET /asset```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Spot Wallet

Get Information of Spot Wallet

> Response

```json
{
  "data": [
    {
      "id": 2900,
      "memberId": 83037,
      "coin": {
        "name": "USDT",
        "nameCn": "USDT",
        "unit": "USDT",
        "status": 0,
        "minTxFee": 5.0,
        "maxTxFee": 5.0,
        "cnyRate": 0.0,
        "usdRate": 1.0,
        "enableRpc": 1,
        "sort": 0,
        "canSend": 1,
        "canWithdraw": 1,
        "canRecharge": 1,
        "canTransfer": 1,
        "canAutoWithdraw": 0,
        "withdrawScale": 6,
        "withdrawThreshold": 1.0,
        "minWithdrawAmount": 50.0,
        "maxWithdrawAmount": 10000.0,
        "minRechargeAmount": 1.0,
        "isPlatformCoin": 1,
        "isToken": 1,
        "hasLegal": false,
        "allBalance": null,
        "coldWalletAddress": "",
        "hotAllBalance": null,
        "blockHeight": null,
        "minerFee": null,
        "infolink": "",
        "information": "USDT",
        "accountType": 0,
        "depositAddress": null,
        "memoAdjust": null,
        "scanTxidWeburl": "https://etherscan.io/tx/",
        "scanAddressWeburl": "https://etherscan.io/address/",
        "visible": 1,
        "testMode": 0,
        "networkCoins": null,
        "icon": "https://dev-static.neonexteam.com/image/coin/USDT.svg",
        "defaultIcon": "https://dev-static.neonexteam.com/image/coin/default.svg",
        "spotTradable": null
      },
      "balance": 999998.8885,
      "frozenBalance": 0.0,
      "lockedBalance": 0.0,
      "toReleased": 0.0,
      "networkCoin": null,
      "address": "",
      "tag": null,
      "memo": null,
      "isLock": 0
    }
  ],
  "code": 0,
  "message": "SUCCESS"
}
```

```GET /asset/spot```
### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Spot Coin Wallet
Get Information of spot wallet on a symbol

> Response

```json
{
  "data": {
    "id": 2901,
    "memberId": 83037,
    "coin": {
      "name": "Bitcoin",
      "nameCn": "Bitcoin",
      "unit": "BTC",
      "status": 0,
      "minTxFee": 0.001,
      "maxTxFee": 0.001,
      "cnyRate": 0.0,
      "usdRate": 0.0,
      "enableRpc": 1,
      "sort": 1,
      "canSend": 1,
      "canWithdraw": 1,
      "canRecharge": 1,
      "canTransfer": 0,
      "canAutoWithdraw": 0,
      "withdrawScale": 5,
      "withdrawThreshold": 0.1,
      "minWithdrawAmount": 2.0E-5,
      "maxWithdrawAmount": 10.0,
      "minRechargeAmount": 1.0E-6,
      "isPlatformCoin": 1,
      "isToken": 0,
      "hasLegal": false,
      "allBalance": null,
      "coldWalletAddress": "14QZK9h8udeB6riNfrNRYhK5ptHzJTmjM5",
      "hotAllBalance": null,
      "blockHeight": null,
      "minerFee": null,
      "infolink": "",
      "information": "BTC",
      "accountType": 0,
      "depositAddress": "mi1Q3VpBYr7XJL9pP51Vpw1WLc1eXSQxzX",
      "memoAdjust": null,
      "scanTxidWeburl": "https://www.blockchain.com/btc/tx/",
      "scanAddressWeburl": "https://www.blockchain.com/btc/address/",
      "visible": 1,
      "testMode": 0,
      "networkCoins": null,
      "icon": null,
      "defaultIcon": null,
      "spotTradable": null
    },
    "balance": 20.0,
    "frozenBalance": 0.0,
    "lockedBalance": 0.0,
    "toReleased": 0.0,
    "networkCoin": null,
    "address": "",
    "tag": null,
    "memo": null,
    "isLock": 0
  },
  "code": 0,
  "message": "success"
}
```

```GET /asset/spot/{symbol}```
### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Future Wallet
Get Information of Future Wallet

> Response

```json
[
  {
    "symbol": "USDT",
    "total_wallet_balance": 100000.0,
    "total_margin_balance": 100000.0,
    "total_available_balance": 100000.0,
    "total_unpnl": 0,
    "position": []
  }
]
```

```GET /asset/future```
### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Transfer
Spot or future asset transfer

> Response

```json
```

```GET /asset/exchange```
### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |


### Request Body:

| Name   | Type     | Required | Description             |
|--------|----------|----------|-------------------------|
| unit   | String   | Yes      |                         |
| from   | Interger | Yes      | 0: Spot,<br/> 1: Future |
| to     | Interger | Yes      | 0: Spot,<br/> 1: Future |
| amount | Decimal  | Yes      | API key                 |

# Spot Endpoint

## Order
> Response

```json
{
  "data": "E167842752431114",
  "code": 0,
  "message": "success"
}
```

```PUT /spot/trade```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name      | Type    | Required | Description                   |
|-----------|---------|----------|-------------------------------|
| symbol    | String  | Yes      |                               |
| price     | Decimal | Yes      |                               |
| amount    | Decimal | Yes      |                               |
| direction | String  | Yes      | BUY,<br/>SELL                 |
| type      | String  | Yes      | LIMIT_PRICE,<br/>MARKET_PRICE |

## Order Histories
> Response

```json
{
  "content": [
    {
      "orderId": "E167868675922825",
      "memberId": 83037,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "status": "COMPLETED",
      "direction": "BUY",
      "type": "LIMIT_PRICE",
      "price": 20284.93,
      "amountSymbol": "BTC",
      "amountType": "COIN",
      "amount": 1.0,
      "tradedAmount": 1.0,
      "turnover": 20284.93,
      "time": 1678686759228,
      "completedTime": 1678686759280,
      "canceledTime": null,
      "useDiscount": "0",
      "orderResource": "CUSTOMER",
      "detail": null,
      "completed": true
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalElements": 1,
  "totalPages": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "first": true,
  "numberOfElements": 1,
  "empty": false
}
```

```GET /spot/trade/transaction```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name      | Type    | Required | Description  |
|-----------|---------|----------|--------------|
| symbol    | String  | Yes      |              |
| pageNo    | Integer | Yes      |              |
| pageSize  | Integer | Yes      |              |

## Order History
> Response

```json
[
  {
    "orderId": "E167868675922825",
    "price": 20284.93,
    "amountSymbol": "BTC",
    "amountType": "COIN",
    "amount": 1.0,
    "turnover": 20284.93,
    "fee": 0.001,
    "feeSymbol": "BTC",
    "time": 1678686759247
  }
]
```

```GET /spot/trade/transaction/{orderId}```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Trade History
> Response

```json
{
  "content": [
    {
      "tradeId": "71635908",
      "tradeTime": 1678686759247,
      "memberId": 83037,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "direction": "BUY",
      "type": "LIMIT_PRICE",
      "role": "TAKER",
      "price": 20284.93,
      "tradedAmount": 1.0,
      "turnover": 20284.93,
      "orderId": "E167868675922825",
      "feeSymbol": "BTC",
      "fee": 0.001
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalElements": 1,
  "totalPages": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "first": true,
  "numberOfElements": 1,
  "empty": false
}
```

```GET /spot/trade/conclusion```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name      | Type    | Required | Description                    |
|-----------|---------|----------|--------------------------------|
| symbol    | String  | No       |                                |
| type      | String  | No       | LIMIT_PRICE,<br/> MARKET_PRICE |
| direction | String  | No       | BUY,<br/> SELL                 |
| startTime | String  | No       |                                |
| endTime   | String  | No       |                                |
| pageNo    | Integer | Yes      |                                |
| pageSize  | Integer | Yes      |                                |

## Current Open Order
Get all open orders or get all open orders on a symbol.
> Response

```json
{
  "content": [
    {
      "orderId": "E167868662035342",
      "memberId": 83037,
      "symbol": "BTC/USDT",
      "coinSymbol": "BTC",
      "baseSymbol": "USDT",
      "status": "TRADING",
      "direction": "BUY",
      "type": "LIMIT_PRICE",
      "price": 20017.5,
      "amountSymbol": "BTC",
      "amountType": "COIN",
      "amount": 1.0,
      "tradedAmount": 0,
      "turnover": 0,
      "time": 1678686620353,
      "completedTime": null,
      "canceledTime": null,
      "useDiscount": "0",
      "orderResource": "CUSTOMER",
      "detail": [],
      "completed": false
    }
  ],
  "pageable": {
    "sort": {
      "empty": false,
      "sorted": true,
      "unsorted": false
    },
    "offset": 0,
    "pageNumber": 0,
    "pageSize": 10,
    "paged": true,
    "unpaged": false
  },
  "last": true,
  "totalElements": 1,
  "totalPages": 1,
  "size": 10,
  "number": 0,
  "sort": {
    "empty": false,
    "sorted": true,
    "unsorted": false
  },
  "first": true,
  "numberOfElements": 1,
  "empty": false
}
```

```GET /spot/trade/non```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name      | Type    | Required | Description                    |
|-----------|---------|----------|--------------------------------|
| symbol    | String  | No       |                                |
| pageNo    | Integer | Yes      |                                |
| pageSize  | Integer | Yes      |                                |

## Cancel Orders
Cancel all orders.
> Response

```json
{
  "data": null,
  "code": 0,
  "message": "success"
}
```

```POST /spot/trade/cancel```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Cancel Order
Cancel all orders on a symbol.
> Response

```json
{
  "data": null,
  "code": 0,
  "message": "success"
}
```

```POST /spot/trade/cancel/{orderId}```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |


# Future Endpoint

## Order
> Response

```json
{
    "detail": {
        "code": 0,
        "msg": "SUCCESS"
    }
}
```

```PUT /future/trade```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name           | Type    | Required | Description                              |
|----------------|---------|----------|------------------------------------------|
| ticker         | String  | Yes      |                                          |
| margin_mode    | Integer | Yes      | Isolated: 0,<br/> Cross: 1               |
| direction      | Integer | Yes      | Open: 0,<br/> Liquidation: 1             |
| position       | Integer | Yes      | Long : 0,<br/> Short: 1                  |
| order_type     | Integer | Yes      | Market: 0,<br/> Limit: 1                 |
| leverage       | Integer | Yes      |                                          |
| order_price    | Decimal | Yes      |                                          |
| order_qty      | Decimal | Yes      |                                          |
| is_post_only   | Boolean | Yes      | post only: true,<br/> otherwise: false   |
| is_reduce_only | Boolean | Yes      | reduce only: true,<br/> otherwise: false |

## Order History
> Response

```json
{
  "order_list": [
    {
      "id": 834,
      "ticker_id": 1,
      "member_id": 9,
      "order_id": "F166984747713249",
      "margin_mode": 0,
      "direction": 0,
      "position": 0,
      "role": 0,
      "order_type": 1,
      "status": 3,
      "tif_mode": 0,
      "trigger_type": 0,
      "trigger_direction": 0,
      "ticker": "BTCUSDT",
      "coin_symbol": "BTC",
      "base_symbol": "USDT",
      "leverage": 50,
      "order_price": 20007.88,
      "order_qty": 5.43,
      "traded_price": 0,
      "traded_qty": 5.43,
      "traded_value": 108642.7884,
      "left_qty": 0,
      "is_post_only": false,
      "is_reduce_only": false,
      "is_liquid": false,
      "is_price_protected": false,
      "order_time": "2022-12-01T07:31:17",
      "filled_time": "2022-12-01T07:31:18",
      "cancel_time": null
    },
    {
      "id": 833,
      "ticker_id": 1,
      "member_id": 9,
      "order_id": "F166984746102258",
      "margin_mode": 0,
      "direction": 0,
      "position": 1,
      "role": 0,
      "order_type": 1,
      "status": 2,
      "tif_mode": 0,
      "trigger_type": 0,
      "trigger_direction": 0,
      "ticker": "BTCUSDT",
      "coin_symbol": "BTC",
      "base_symbol": "USDT",
      "leverage": 50,
      "order_price": 20007.88,
      "order_qty": 10.43,
      "traded_price": 20007.88,
      "traded_qty": 5.43,
      "traded_value": 108642.7884,
      "left_qty": 5,
      "is_post_only": false,
      "is_reduce_only": false,
      "is_liquid": false,
      "is_price_protected": false,
      "order_time": "2022-12-01T07:31:01",
      "filled_time": null,
      "cancel_time": "2022-12-01T07:31:46"
    }
  ],
  "trade_dict": {
    "F166984747713249": [
      {
        "ticker_id": 1,
        "symbol": "USDT",
        "order_id": "F166984747713249",
        "income_symbol": "BTC",
        "order_type": 1,
        "price": 20007.88,
        "opposite_order_id": "F166984746102258",
        "traded_qty": 5.43,
        "margin_mode": 0,
        "traded_value": 108642.7884,
        "member_id": 9,
        "direction": 0,
        "trading_fee": 65.18567304,
        "id": 351,
        "position": 0,
        "role": 0,
        "transaction_time": "2022-11-30T22:31:17",
        "ticker": "BTCUSDT",
        "profit_and_loss": 0
      }
    ],
    "F166984746102258": []
  }
}
```

```GET /future/trade/transaction```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Parameter:

| Name       | Type    | Required | Description                                                                        |
|------------|---------|----------|------------------------------------------------------------------------------------|
| ticker     | String  | Yes      |                                                                                    |
| direction  | Integer | Yes      | Open: 0,<br/> Liquidation: 1                                                       |
| position   | Integer | Yes      | Long : 0,<br/> Short: 1                                                            |
| order_type | Integer | Yes      | Market: 0,<br/> Limit: 1,<br/>Take Profit: 2,<br/>Stop Less: 3,<br/>Liquidation: 4 |
| status     | Integer | Yes      | Open: 0,<br/> Partial: 2,<br/> Cancelled: 3,<br/> Filled: 4                        |
| size       | Integer | No       | Default 50                                                                         |
| page       | Integer | No       | Default 1                                                                          |
| start_time | String  | No       | Unix Timestamp                                                                     |
| end_time   | String  | No       | Unix Timestamp                                                                     |

## Current Open Order History
> Response

```json
[
    {
        "role": 0,
        "tif_mode": 0,
        "trigger_type": 0,
        "trigger_direction": 0,
        "order_price": 20006.52,
        "traded_price": 0.0,
        "traded_qty": 0.0,
        "traded_value": 0.0,
        "is_post_only": false,
        "is_reduce_only": false,
        "is_liquid": false,
        "is_price_protected": false,
        "filled_time": null,
        "cancel_time": null,
        "id": 818,
        "ticker_id": 1,
        "member_id": 9,
        "order_id": "F166973879588370",
        "margin_mode": 0,
        "direction": 0,
        "position": 1,
        "order_type": 1,
        "status": 0,
        "ticker": "BTCUSDT",
        "coin_symbol": "BTC",
        "base_symbol": "USDT",
        "leverage": 50,
        "order_qty": 0.55,
        "left_qty": 0.55,
        "order_time": "2022-11-30T01:19:56"
    },
    {
        "role": 0,
        "tif_mode": 0,
        "trigger_type": 0,
        "trigger_direction": 0,
        "order_price": 20005.52,
        "traded_price": 0.0,
        "traded_qty": 0.0,
        "traded_value": 0.0,
        "is_post_only": false,
        "is_reduce_only": false,
        "is_liquid": false,
        "is_price_protected": false,
        "filled_time": null,
        "cancel_time": null,
        "id": 817,
        "ticker_id": 1,
        "member_id": 9,
        "order_id": "F166973871288012",
        "margin_mode": 0,
        "direction": 0,
        "position": 1,
        "order_type": 1,
        "status": 0,
        "ticker": "BTCUSDT",
        "coin_symbol": "BTC",
        "base_symbol": "USDT",
        "leverage": 50,
        "order_qty": 0.52,
        "left_qty": 0.52,
        "order_time": "2022-11-30T01:18:33"
    },
    {
        "role": 0,
        "tif_mode": 0,
        "trigger_type": 0,
        "trigger_direction": 0,
        "order_price": 20004.51,
        "traded_price": 0.0,
        "traded_qty": 0.0,
        "traded_value": 0.0,
        "is_post_only": false,
        "is_reduce_only": false,
        "is_liquid": false,
        "is_price_protected": false,
        "filled_time": null,
        "cancel_time": null,
        "id": 815,
        "ticker_id": 1,
        "member_id": 9,
        "order_id": "F166973652175041",
        "margin_mode": 0,
        "direction": 0,
        "position": 1,
        "order_type": 1,
        "status": 0,
        "ticker": "BTCUSDT",
        "coin_symbol": "BTC",
        "base_symbol": "USDT",
        "leverage": 50,
        "order_qty": 0.53,
        "left_qty": 0.53,
        "order_time": "2022-11-30T00:42:02"
    }
]
```

```GET /future/trade/non```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Parameter:

| Name       | Type    | Required | Description    |
|------------|---------|----------|----------------|
| ticker     | String  | Yes      |                |
| size       | Integer | No       | Default 50     |
| page       | Integer | No       | Default 1      |
| start_time | String  | No       | Unix Timestamp |

## Cancel Orders
Cancel all orders on a ticker.
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```POST /future/trade/cancel```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Parameter:

| Name       | Type    | Required | Description    |
|------------|---------|----------|----------------|
| ticker     | String  | Yes      |                |


## Cancel Order
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```POST /future/trade/cancel{orderId}```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Future Leverage
Get Information of future leverage on a ticker.
> Response

```json
{
  "leverage": 125
}
```

```GET /future/trade/leverage/{ticker}```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Future Leverage Settings
Get Information of future leverage on a ticker.
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```POST /future/trade/leverage```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name     | Type    | Required | Description |
|----------|---------|----------|-------------|
| ticker   | String  | Yes      |             |
| leverage | Integer | Yes      |             |

## Future Position
Get Information of future position on a ticker.
> Response

```json
[
  {
    "take_profit_price": 0,
    "stop_loss_price": 0,
    "profit_and_loss": 0,
    "adl": 0,
    "entry_time": "2022-12-01T10:58:39",
    "close_time": null,
    "id": 217,
    "ticker_id": 1,
    "member_id": 9,
    "margin_mode": 0,
    "position": 1,
    "status": 0,
    "ticker": "BTCUSDT",
    "coin_symbol": "BTC",
    "base_symbol": "USDT",
    "leverage": 50,
    "qty": 3.43,
    "value": 68627.0284,
    "entry_price": 20007.88,
    "liquid_price": 20307.9982,
    "bankruptcy_price": 20408.0376,
    "initial_margin": 1372.540568,
    "maintenance_margin": 343.13514200000003,
    "liquid_margin": 300.1182,
    "position_margin": 1414.5403093808,
    "close_fee": 41.9997413808
  }
]
```

```GET /future/trade/position/{ticker}```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

## Future Position Close
Close all or close on a ticker
> Response

```json
{
  "detail": {
    "code": 0,
    "msg": "SUCCESS"
  }
}
```

```POST /future/trade/position/close```

### Headers:

| Name        | Type   | Required | Description |
|-------------|--------|----------|-------------|
| x-api-token | String | Yes      | API key     |

### Request Body:

| Name     | Type    | Required | Description    |
|----------|---------|----------|----------------|
| ticker   | String  | Yes      | all: Close All |
