The positions API lets you retrieve the current holdings for a client or entity. With Blitz, you can monitor your positions in real time, track pending and non-acknowledged quantities, analyze trade values, and maintain full control over your portfolio — all through a simple, easy-to-use API.

These endpoints let you retrieve, filter, and monitor positions efficiently.

| **Type** | **Endpoint** | **Description** |
|----------|--------------|----------------|
| GET      | [positions](#fetching-positions) | Retrieve the list of all positions for a client/entity. |

---

### Glossary / Notes
- `positions` → Refers to all holdings for the client/entity.  
- Quantities:
  - `open_buy_quantity` → Current open buy quantity.  
  - `open_sell_quantity` → Current open sell quantity.  
  - `non_ack_buy_quantity` → Buy quantity not yet acknowledged by the system.  
  - `non_ack_sell_quantity` → Sell quantity not yet acknowledged by the system.  
- `long_position` → Total long quantity held.  
- `short_position` → Total short quantity held.  
- `net_position` → Long minus short positions.  

---

## Blitz API: Position-Related Fields

| Field                        | Type     | Description |
|-------------------------------|---------|-------------|
| `entity_id`                   | string  | Unique identifier for the entity/client. |
| `client_id`                   | string  | Client code. |
| `rms_entity_code`             | string  | RMS entity code (may be empty). |
| `instrument_id`               | number  | Unique identifier for the instrument. |
| `exchange_segment`            | string  | Trading segment (e.g., NSECM). |
| `instrument_name`             | string  | Name of the instrument (e.g., RELIANCE). |
| `non_ack_buy_quantity`        | number  | Non-acknowledged buy quantity. |
| `non_ack_sell_quantity`       | number  | Non-acknowledged sell quantity. |
| `open_buy_quantity`           | number  | Open buy quantity. |
| `open_sell_quantity`          | number  | Open sell quantity. |
| `long_position`               | number  | Total long position held. |
| `short_position`              | number  | Total short position held. |
| `net_position`                | number  | Net position (long - short). |
| `net_position_in_lot`         | number  | Net position in lot size. |
| `order_count`                 | number  | Number of orders executed for this instrument. |
| `trade_count`                 | number  | Number of trades executed for this instrument. |
| `previous_net_position`       | number  | Previous net position before today’s trades. |
| `trade_buy_value`             | number  | Total value of buy trades executed. |
| `trade_sell_value`            | number  | Total value of sell trades executed. |
| `trade_net_value`             | number  | Net trade value (buy - sell). |
| `avg_buy`                     | number  | Average buy price. |
| `avg_sell`                    | number  | Average sell price. |
| `avg_net`                     | number  | Net average price. |
| `exposure`                    | number  | Exposure value of the position. |
| `unrealized`                  | number  | Unrealized P&L for the position. |
| `realized`                    | number  | Realized P&L for the position. |
| `last_traded_price`           | number  | Last traded price of the instrument. |
| `open_position_trade_value`   | number  | Trade value of open positions. |
| `turnover_value`              | number  | Total turnover value of the instrument. |
| `turnover_value_options`      | number  | Turnover value for options (if any). |

---

## 1. Fetching Positions {#fetching-positions}

Retrieve a complete list of all positions for a specific client or entity. This includes:

- **Open positions:** Positions with pending or active trades.  
- **Non-acknowledged quantities:** Trades placed but not yet acknowledged by the system.  
- **Trade counts and values:** Orders executed, total buy/sell/trade values.  
- **Exposure and P&L:** Both realized and unrealized.  

```bash
curl -X 'GET' \
  'http://api.blitz.com/api/v1/positions' \
  -H 'accept: */*'
```

### Response
```json
{
    "SIDD09": [
        {
            "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
            "client_id": "SIDD09",
            "rms_entity_code": "",
            "instrument_id": 1010010000002885,
            "exchange_segment": "NSECM",
            "instrument_name": "RELIANCE",
            "non_ack_buy_quantity": 0,
            "non_ack_sell_quantity": 0,
            "open_buy_quantity": 0,
            "open_sell_quantity": 0,
            "short_position": 0,
            "long_position": 11,
            "net_position": 11,
            "net_position_in_lot": 11,
            "order_count": 2,
            "trade_count": 5,
            "previous_net_position": 0,
            "trade_buy_value": 15600.399999999998,
            "trade_sell_value": 0,
            "trade_net_value": -15600.399999999998,
            "avg_buy": 1418.2181818181816,
            "avg_sell": 0,
            "avg_net": -1418.2181818181816,
            "exposure": 15585.900000000001,
            "unrealized": -14.499999999996362,
            "realized": 0,
            "last_traded_price": 1416.9,
            "open_position_trade_value": 15600.399999999998,
            "turnover_value": 15600.399999999998,
            "turnover_value_options": 0
        },
        {
            "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
            "client_id": "SIDD09",
            "rms_entity_code": "",
            "instrument_id": 1010010000002885,
            "exchange_segment": "NSECM",
            "instrument_name": "RELIANCE",
            "non_ack_buy_quantity": 0,
            "non_ack_sell_quantity": 0,
            "open_buy_quantity": 0,
            "open_sell_quantity": 0,
            "short_position": 0,
            "long_position": 11,
            "net_position": 11,
            "net_position_in_lot": 11,
            "order_count": 2,
            "trade_count": 5,
            "previous_net_position": 0,
            "trade_buy_value": 15600.399999999998,
            "trade_sell_value": 0,
            "trade_net_value": -15600.399999999998,
            "avg_buy": 1418.2181818181816,
            "avg_sell": 0,
            "avg_net": -1418.2181818181816,
            "exposure": 15585.900000000001,
            "unrealized": -14.499999999996362,
            "realized": 0,
            "last_traded_price": 1416.9,
            "open_position_trade_value": 15600.399999999998,
            "turnover_value": 15600.399999999998,
            "turnover_value_options": 0
        }
    ]
}
```