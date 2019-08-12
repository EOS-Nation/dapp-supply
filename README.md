# DAPP token supply calculations

The following requests will allow you to calculate the `active` supply of DAPP tokens in circulations based on the `dappservices` token contract.

1. get `dappservices` supply
2. get `regulartrack` supply
3. get `instanttrack` supply
4. DAPP token supply calculations

> `dappservices` supply - `regulartrack` balance - `instanttrack` balance = **DAPP active supply**

## 1. get `dappservices` supply of DAPP tokens

```bash
$ curl --request POST \
  --url https://api.eosn.io/v1/chain/get_currency_stats \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"code":"dappservices","symbol":"DAPP"}'
{"DAPP":{"supply":"1012305677.0485 DAPP","max_supply":"20000000000.0000 DAPP","issuer":"dappservices"}}
```

- **supply**: `1012305677.0485 DAPP`

## 2. get `regulartrack` supply

```
$ curl --request POST \
  --url http://api.eosn.io/v1/chain/get_currency_balance \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"code":"dappservices","account":"regulartrack"}'
["125000000.1359 DAPP"]
```

- **regulartrack** balance: `125000000.1359 DAPP`

## 3. get `instanttrack` supply

```
$ curl --request POST \
  --url http://api.eosn.io/v1/chain/get_currency_balance \
  --header 'accept: application/json' \
  --header 'content-type: application/json' \
  --data '{"code":"dappservices","account":"instanttrack"}'
["125000000.1359 DAPP"]
```

- **instanttrack** balance: `125000000.1359 DAPP`

## 4. DAPP token supply calculations

`dappservices` supply - `regulartrack` balance - `instanttrack` balance = **DAPP active supply**

```js
1012305677.0485 - 125000000.1359 - 125000000.1359 = 762305676.7767
```
