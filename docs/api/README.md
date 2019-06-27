# API

List of available REST API's for scotbot

## state

Shows the state of scotbot

### Endpoint

`GET /state`

### Types

| Field                   |                         Description                          |
| :---------------------- | :----------------------------------------------------------: |
| last_backend_timestamp  |              Timestamp from the backend server               |
| last_streamed_block     |     last streamed block number from the steem blockchain     |
| last_streamed_timestamp |             timestamp of the last streamed block             |
| time_delay_seconds      | delay in seconds between the last streamed block and the backend clock |

### Examples

```sh
curl https://scot-api.steem-engine.com/state
```

```json
{
  "last_backend_timestamp": "2019-06-27T16:58:18",
  "last_streamed_block": 34171200,
  "last_streamed_timestamp": "2019-06-27T16:58:12",
  "time_delay_seconds": 6.785371
}
```

## info

Shows information about all scot tokens

### Endpoint

`GET /info`

### Query Parameters

| Name  |  Type   | Description     |      Required      |
| :---- | :-----: | :-------------- | :----------------: |
| token | strings | scot token name | :white_check_mark: |

### Types

| Field | Description |
| :---- | :---------: |
|       |      `      |
|       |             |

### Examples

```sh
curl https://scot-api.steem-engine.com/info?token=PAL
```

```json
{
  "claimed_token": 50530384,
  "enabled": true,
  "inflation_tools": 2,
  "issuer": "minnowsupport",
  "last_mining_claim_block_num": 34170996,
  "last_mining_claim_trx": "cec63019c8181b3272892e0364e73eef9dcdabdc",
  "last_other_accounts_transfer_block_num": 34169330,
  "last_processed_mining_claim_block_num": 34169813,
  "last_processed_staking_claim_block_num": 0,
  "last_reduction_block_num": 33534726,
  "last_reward_block_num": 34171294,
  "last_staking_claim_block_num": null,
  "last_staking_claim_trx": null,
  "mining_enabled": true,
  "mining_reward_pool": 24805,
  "next_mining_claim_number": 0,
  "next_staking_claim_number": 0,
  "other_reward_pool": 46501,
  "pending_rshares": 181558451316,
  "pending_token": 5438732,
  "precision": 3,
  "reward_pool": 26952324,
  "rewards_token": 62000,
  "setup_complete": 2,
  "staked_mining_power": 2713.0,
  "staked_token": 1867123816,
  "staking_enabled": false,
  "staking_reward_pool": 0,
  "start_block_num": 33534726,
  "start_date": "Wed, 05 Jun 2019 15:44:21 GMT",
  "symbol": "PAL",
  "total_generated_token": 98331000,
  "voting_enabled": true
}
```
## config

Shows configuration of a scot token

### Endpoint

`GET /config`

### Query Parameters

| Name  |  Type   | Description     | Required |
| :---- | :-----: | :-------------- | :------: |
| token | strings | scot token name |          |

### Types

| Field | Description |
| :---- | :---------: |
|       |      `      |
|       |             |

### Examples

```sh
curl https://scot-api.steem-engine.com/config?token=PAL
```

```json
{
  "author_curve_exponent": 1.05,
  "author_reward_percentage": 50.0,
  "beneficiaries_account": "null",
  "beneficiaries_reward_percentage": 0.0,
  "cashout_window_days": 7.0,
  "curation_curve_exponent": 0.5,
  "downvote_power_consumption": 2000,
  "downvote_regeneration_seconds": 432000,
  "downvote_window_days": -1,
  "enable_account_muting": true,
  "issue_token": true,
  "json_metadata_app_value": null,
  "json_metadata_key": "tags",
  "json_metadata_value": "palnet",
  "miner_tokens": "{\"PALM\": 1, \"PALMM\": 4}",
  "mining_pool_claim_number": 9,
  "mining_pool_claims_per_year": 8760,
  "muting_account": "nopal4u",
  "n_daily_posts_muted_accounts": 1,
  "other_pool_accounts": "{\"msp-active\": 10, \"msp-mods\": 5}",
  "other_pool_percentage": 15.0,
  "other_pool_send_token_per_year": 365,
  "pob_pool_percentage": 75.0,
  "posm_pool_percentage": 10.0,
  "promoted_post_account": "null",
  "reduction_every_n_block": 10512000,
  "reduction_percentage": 1.0,
  "rewards_token": 62.0,
  "rewards_token_every_n_block": 400,
  "staking_pool_claim_number": 0,
  "staking_pool_claims_per_year": 0,
  "staking_pool_percentage": 0.0,
  "token": "PAL",
  "token_account": "minnowsupport",
  "vote_power_consumption": 200,
  "vote_regeneration_seconds": 432000,
  "vote_window_days": -1
}
```
## @account

Shows account information

### Endpoint

`GET /@account_name`

### Query Parameters

| Name  |  Type   | Description     | Required |
| :---- | :-----: | :-------------- | :------: |
| token | strings | scot token name |          |

### Types

| Field | Description |
| :---- | :---------: |
|       |      `      |
|       |             |

### Examples

```sh
curl https://scot-api.steem-engine.com/@holger80?token=PAL
```

```json
{
  "downvoting_power": 10000,
  "earned_token": 176098,
  "last_downvote_time": "2019-01-01T00:00:00",
  "last_post": "Tue, 25 Jun 2019 10:46:54 GMT",
  "last_root_post": "Fri, 21 Jun 2019 11:07:45 GMT",
  "last_vote_time": "2019-06-27T16:07:12",
  "last_won_mining_claim": "Tue, 01 Jan 2019 00:00:00 GMT",
  "last_won_staking_claim": "Tue, 01 Jan 2019 00:00:00 GMT",
  "loki": null,
  "muted": false,
  "name": "holger80",
  "pending_token": 183,
  "staked_mining_power": 0.0,
  "staked_tokens": 2277000,
  "symbol": "PAL",
  "voting_power": 9646
}
```

## @account/permlink

Shows information about a post

### Endpoint

`GET /@account/permlink`

### Query Parameters

| Name  |  Type   | Description     |      Required      |
| :---- | :-----: | :-------------- | :----------------: |
|  |  | | |

### Types

| Field | Description |
| :---- | :---------: |
|       |      `      |
|       |             |

### Examples

```sh
curl https://scot-api.steem-engine.com/@holger80/scotbot-time-delay-can-be-checked-and-account-blacklisting-possible
```

```json

{
  "PAL": {
    "active_votes": [
      {
        "authorperm": "@holger80/scotbot-time-delay-can-be-checked-and-account-blacklisting-possible",
        "block_num": 34165478,
        "percent": 10000,
        "rshares": 2816703,
        "timestamp": "2019-06-27T12:11:57",
        "token": "PAL",
        "voter": "steemaction",
        "weight": 121
      },
      ],
      ,
    "app": "palnet/0.1",
    "author": "holger80",
    "author_curve_exponent": 1.05,
    "authorperm": "@holger80/scotbot-time-delay-can-be-checked-and-account-blacklisting-possible",
    "beneficiaries_payout_value": 0,
    "block": 33991602,
    "cashout_time": "2019-06-28T11:07:42",
    "children": 14,
    "created": "2019-06-21T11:07:42",
    "curator_payout_value": 0,
    "decline_payout": false,
    "desc": "![](https://cdn.steemitimages.com/DQmVLEQz4R6TLspWojh1uHaiMhZ2w8125zWdBp1YeodBrzM/image.png)\n\nScotbot has a new endpoint:\n\nhttps://scot-api.steem-engine.com/state\n\nwhich can be used to check the current time delay of scotbot:\n\n```\n{\"last_backend_timestamp\":\"2019-06-21T10:15:20\",\"last_streamed_block\"",
    "json_metadata": "{\"tags\": [\"steem-engine\", \"palnet\", \"sct\", \"weedcash\", \"spt\"], \"image\": [\"https://cdn.steemitimages.com/DQmVLEQz4R6TLspWojh1uHaiMhZ2w8125zWdBp1YeodBrzM/image.png\"], \"links\": [\"https://scot-api.steem-engine.com/state\", \"https://scot-api.steem-engine.com/config\", \"https://steemworld.org\", \"https://steemworld.org/@sct\", \"https://scot-api.steem-engine.com/@account\", \"https://scot-api.steem-engine.com/@null.promoted?token=SCT\"], \"app\": \"palnet/0.1\", \"format\": \"markdown\"}",
    "last_payout": "1970-01-01T00:00:00",
    "last_update": "2019-06-27T08:45:02",
    "main_post": true,
    "pending_token": 49290,
    "precision": 3,
    "promoted": 0,
    "score_hot": 156115.0,
    "score_trend": 3256.45,
    "tags": "steem-engine,palnet,sct,weedcash,spt",
    "title": "Scotbot: time delay can be checked and account blacklisting possible",
    "token": "PAL",
    "total_payout_value": 0,
    "total_vote_weight": 0,
    "vote_rshares": 137150552
  },
  }
```
