The **Trades API** lets you retrieve all trade details executed under a given entity, strategy, or client.  
Using this API, you can monitor executed orders, pending trades, and their execution details in real time.

These endpoints let you **retrieve, filter, and monitor trade executions** efficiently.

| **Type** | **Endpoint** | **Description** |
|-----------|--------------|----------------|
| GET | [`trades`](#fetching-trades) | Retrieve the list of all trades. |
| GET | [`trades/{boid}`](#fetching-trades-by-boid) | Retrieve trade details for a specific BlitzOrderId. |


---

#### **Glossary / Notes**

- `trades` → Refers to individual trade executions associated with strategies or entities.  
- Each trade represents one completed or pending transaction within a trading strategy.  
- Common fields like `order_side`, `status`, and `execution_type` help track the lifecycle of a trade.  
- Use filtering parameters (e.g., `entity_id`, `client_id`, `strategy_id`) to narrow results.

---

## **1. Trades** {#fetching-trades}

Retrieve all trades currently recorded for a given client, entity, or strategy instance.

```bash
curl -X 'GET' \
  'http://api.blitz.com/api/v1/trades' \
  -H 'accept: application/json'
```

### Response
```json
[
  {
    "id": 1,
    "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
    "strategy_id": "STRAT123",
    "strategy_instance_id": "INST001",
    "strategy_instance_name": "Momentum_Strategy",
    "strategy_name": "Momentum Trading",
    "iv_object_name": "NIFTY_FUT",
    "instrument_id": 1010010000002885,
    "exchange_segment": "NSEFO",
    "exchange_instrument_id": 2885,
    "instrument_name": "NIFTY24OCTFUT",
    "instrument_type": 1,
    "blitz_order_id": 9001,
    "exchange_order_id": "EX123456",
    "execution_id": "EXEC001",
    "account": "ACC001",
    "client_id": "SIDD09",
    "order_type": "LIMIT",
    "order_side": "BUY",
    "status": "Filled",
    "order_quantity": 50,
    "order_price": 22450.00,
    "order_stop_price": 0,
    "order_trigger_price": 0,
    "last_traded_quantity": 50,
    "last_traded_price": 22450.00,
    "cumulative_quantity": 50,
    "leaves_quantity": 0,
    "tif": "DAY",
    "order_expiry_date": 20251013,
    "order_disclosed_quantity": 0,
    "minimum_quantity": 0,
    "order_generated_date_time": 1728796800,
    "last_request_date_time": 1728797000,
    "exchange_transact_time": 1728797050,
    "order_modification_count": 0,
    "order_trade_count": 1,
    "average_traded_price": 22450.00,
    "average_traded_value": 1122500.00,
    "is_fictive_order": false,
    "reject_type": "",
    "reject_type_reason": "",
    "order_tag": "StrategyOrder",
    "ctcl_id": "CTCL001",
    "algo_id": "ALGO001",
    "algo_category_id": "CAT001",
    "clearing_firm_id": "CLF001",
    "pan_id": "ABCDE1234F",
    "is_order_completed": true,
    "user_text": "Auto-executed by Momentum Strategy",
    "execution_type": "REGULAR",
    "strategy_tag": "MOMENTUM",
    "sequence_number": 10001
  }
]
```

## Trades by BlitzOrderId (BOID) {#fetching-trades-by-boid}

The **Trades by BOID API** lets you retrieve detailed trade execution information for a specific **Blitz Order ID (BOID)**.  
Using this endpoint, you can monitor the lifecycle, fills, and execution data of an individual order in real time.

This API is particularly useful for **audit trails**, **strategy performance tracking**, and **trade reconciliation**.

#### **Glossary / Notes**

- `boid` → Refers to the **BlitzOrderId**, a unique identifier assigned to every order placed in the OMS system.  
- This endpoint returns only the trades associated with that **specific BOID**.  
- Common fields such as `execution_type`, `order_side`, and `status` help understand the execution progress.  
- Use this API to trace the **status**, **execution history**, and **filled quantity** of any given order.

---
```bash
curl -X 'GET' \
  'http://api.blitz.com/api/v1/trades/{boid}' \
  -H 'accept: application/json'
  ```

### REsponse
```json
[
  {
    "id": 5,
    "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
    "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
    "strategy_instance_id": "9e1be6c0-c44b-4eb4-a159-b47af104422a",
    "strategy_instance_name": "IDEA|SIDD09|SIDDHESH",
    "strategy_name": "Manual Trading",
    "iv_object_name": "IDEA",
    "instrument_id": 1010010000014366,
    "exchange_segment": "NSECM",
    "exchange_instrument_id": 1010010000014366,
    "instrument_name": "IDEA",
    "instrument_type": 1,
    "blitz_order_id": 1914165469,
    "exchange_order_id": "3104043042150699",
    "execution_id": "3104043042156643",
    "account": "",
    "client_id": "SIDD09",
    "order_type": "Limit",
    "order_side": "Buy",
    "status": "Filled",
    "order_quantity": 1,
    "order_price": 9,
    "order_stop_price": 0,
    "order_trigger_price": 0,
    "last_traded_quantity": 1,
    "last_traded_price": 8.31,
    "cumulative_quantity": 1,
    "leaves_quantity": 0,
    "tif": "GFD",
    "order_expiry_date": 1761996937257,
    "order_disclosed_quantity": 0,
    "minimum_quantity": 0,
    "order_generated_date_time": 1761996937257,
    "last_request_date_time": 1761996937257,
    "exchange_transact_time": 1761996937000,
    "order_modification_count": 0,
    "order_trade_count": 0,
    "average_traded_price": 8.31,
    "average_traded_value": 0,
    "is_fictive_order": false,
    "reject_type": "None",
    "reject_type_reason": "",
    "order_tag": "NormalOrder",
    "ctcl_id": "201301001001000",
    "algo_id": "0",
    "algo_category_id": "0",
    "clearing_firm_id": "",
    "pan_id": "GABPB5317L",
    "is_order_completed": true,
    "user_text": "",
    "execution_type": "Fill",
    "strategy_tag": "General",
    "sequence_number": 0
  }
]
```

### Field Descriptions

| Field | Type | Description |
|-------|------|------------|
| id | integer | Internal unique ID of the order |
| entity_id | string | ID of the entity (user) who placed the order |
| strategy_id | string | Strategy associated with the order, if any |
| strategy_instance_id | string | Instance of the strategy executing the order |
| strategy_instance_name | string | Name of the strategy instance |
| strategy_name | string | Name of the strategy |
| iv_object_name | string | Name of the IV object linked to this order |
| instrument_id | integer | Internal ID of the instrument being traded |
| exchange_segment | string | Exchange segment (e.g., NSEFO, BSECM) |
| exchange_instrument_id | integer | Instrument ID used by the exchange |
| instrument_name | string | Symbol or name of the instrument |
| instrument_type | integer | Type of instrument (Equity, Futures, Options, etc.) |
| blitz_order_id | integer | Order ID in OMS system |
| exchange_order_id | string | Exchange-assigned order ID |
| execution_id | string | Execution ID for trades generated by this order |
| account | string | Account under which the order was placed |
| client_id | string | Client ID who placed the order |
| order_type | string | Type of order (LIMIT, MARKET, STOP, etc.) |
| order_side | string | Side of the order: BUY or SELL |
| status | string | Current status of the order (OPEN, CANCELLED, FILLED, etc.) |
| order_quantity | number | Quantity of the order |
| order_price | number | Price specified for the order |
| order_stop_price | number | Stop price, if applicable |
| order_trigger_price | number | Trigger price for conditional orders |
| last_traded_quantity | number | Quantity executed in the last trade |
| last_traded_price | number | Price executed in the last trade |
| cumulative_quantity | number | Total quantity executed |
| leaves_quantity | number | Quantity remaining to be executed |
| tif | string | Time-in-force (GFD, GTC, IOC, FOK, GTD) |
| order_expiry_date | integer | Expiry date of the order |
| order_disclosed_quantity | number | Disclosed quantity for iceberg orders |
| minimum_quantity | number | Minimum quantity allowed per execution |
| order_generated_date_time | integer | Timestamp when order was generated |
| last_request_date_time | integer | Timestamp of the last modification request |
| exchange_transact_time | integer | Exchange timestamp for the transaction |
| order_modification_count | number | Number of modifications made |
| order_trade_count | number | Number of trades executed |
| average_traded_price | number | Average price for executed trades |
| average_traded_value | number | Total value of executed trades |
| is_fictive_order | boolean | True if the order is simulated/fictive |
| reject_type | string | Type of rejection, if any |
| reject_type_reason | string | Reason for rejection |
| order_tag | string | Optional tag for order categorization |
| algo_id | string | Algorithm ID if placed via algo |
| algo_category_id | string | Algorithm category ID |
| clearing_firm_id | string | Clearing firm ID |
| pan_id | string | PAN ID of the client |
| is_order_completed | boolean | True if order is completed |
| user_text | string | Optional user notes |
| execution_type | string | Execution type (New, PartialFill, Fill, Cancelled) |
| strategy_tag | string | Tag assigned to the strategy |
| sequence_number | number | Sequence number of the order in the system |
