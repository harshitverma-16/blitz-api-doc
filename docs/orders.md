

The order APIs let you place orders of various types, modify or cancel pending orders, and retrieve daily order history. With OMS(Order Management System.), you can manage your trades efficiently, execute orders in real time, track their status, and maintain full control over your portfolio .

These endpoints let you place, modify, cancel, and retrieve orders efficiently.

| **Type** | **Endpoint** | **Description** |
|----------|--------------|----------------|
| GET      | [orders](#fetching-orders) | Retrieve the list of all orders (open and executed) for the day. |
| GET      | [orders/blitzOrderId](#get-order-by-id) | Get all states of a specific order by its BlitzOrderId. |
| POST     | [orders/placeOrder](#place-order) | Place an order of a particular variety. |
| PUT      | [orders/modifyOrder](#modify-order) | Modify an open or pending order. |
| DELETE   | [order/cancelOrder](#cancel-order) | Cancel an open or pending order. |

#### Glossary / Notes { .no-toc }
- `orders` → Refers to all orders for the day.  
- `placeOrder` → Endpoint to create a new order.  
- `modifyOrder` → Endpoint to update an existing order.  
- `cancelOrder` → Endpoint to delete/cancel an order.

#### OMS API: Order-Related Constants

OMS API uses several enum constants when placing, managing, and tracking orders. These constants help standardize order types, sides, statuses, and execution details.

| Enum | Values | Description |
|------|--------|------------|
| `OrderType` | `Market`, `Limit`, `Stop`, `StopLimit`, `MarketIfTouched`, `MarketLimit`, `Pegged` | Type of order to place |
| `OrderSide` | `Buy`, `Sell` | Buy or sell side of the order |
| `TimeInForce` | `GFD`, `GTC`, `IOC`, `FOK`, `GTD` | Duration/order validity |
| `OrderStatus` | `New`, `PartiallyFilled`, `Filled`, `Cancelled`, `Rejected` | Current status of an order |
| `ExecutionType` | `New`, `PartialFill`, `Fill`, `Cancelled`, `Replace`, `Rejected`, `Trade` | Execution events for an order |
| `ProductType` | `MIS`, `NRML`, `CNC`, `MTF`, `ALL` | Product type for the order (Intraday, Delivery, etc.) |

> **Note:** All enum values are used exactly as defined when interacting with the OMS APIs for placing, modifying, canceling, and tracking orders.

## 1. Fetching Orders

Retrieve a complete list of all orders placed by a user for the current trading day. This includes:

- **Open orders:** Orders that have been placed but not yet executed.  
- **Pending orders:** Orders waiting for certain conditions (like trigger price) before execution.  
- **Executed orders:** Orders that have been fully or partially filled.  
- **Cancelled orders:** Orders that were cancelled either by the user or the system.

Using this endpoint, you can:

- Monitor the real-time status of all your orders.  
- Track quantities filled, remaining, and average execution prices.  
- Identify orders that were rejected or failed.  
- Integrate order tracking into dashboards, trading strategies, or reporting tools.

This endpoint provides a **centralized view of your daily trading activity**, making it easier to manage your portfolio and maintain control over all executed, pending, or cancelled trades.

```bash
curl -X 'GET' \
  'http://api.blitz.com/api/order' \
  -H 'accept: */*'
```
### Request Structure
- No Body

### Response Structure

<details>
<summary>Click to view Order List JSON Body</summary>

```json
[
    {
        "id": 25,
        "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
        "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
        "strategy_instance_id": "a78887e2-a295-4d21-b30d-a90cd170aad3",
        "strategy_instance_name": "IDEA",
        "strategy_name": "Manual Trading",
        "iv_object_name": "IDEA",
        "instrument_id": 1010010000014366,
        "exchange_segment": "NSECM",
        "exchange_instrument_id": 1010010000014366,
        "instrument_name": "IDEA",
        "instrument_type": 1,
        "blitz_order_id": 3367140289,
        "exchange_order_id": "0",
        "execution_id": "0",
        "account": "",
        "client_id": "SIDD09",
        "order_type": "Market",
        "order_side": "Buy",
        "status": "PendingNew",
        "order_quantity": 1,
        "order_price": 0,
        "order_stop_price": 0,
        "order_trigger_price": 0,
        "last_traded_quantity": 0,
        "last_traded_price": 0,
        "cumulative_quantity": 0,
        "leaves_quantity": 1,
        "tif": "GFD",
        "order_expiry_date": 1760079432921,
        "order_disclosed_quantity": 0,
        "minimum_quantity": 0,
        "order_generated_date_time": 1760079432921,
        "last_request_date_time": 1760079432921,
        "exchange_transact_time": 1760079432921,
        "order_modification_count": 0,
        "order_trade_count": 0,
        "average_traded_price": 0,
        "average_traded_value": 0,
        "is_fictive_order": false,
        "reject_type": "None",
        "reject_type_reason": "",
        "order_tag": "NormalOrder",
        "ctcl_id": "153541",
        "algo_id": "0",
        "algo_category_id": "0",
        "clearing_firm_id": "",
        "pan_id": "GABPB5317L",
        "is_order_completed": false,
        "user_text": "",
        "execution_type": "None",
        "strategy_tag": "General",
        "sequence_number": 0
    },
    {
        "id": 26,
        "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
        "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
        "strategy_instance_id": "a78887e2-a295-4d21-b30d-a90cd170aad3",
        "strategy_instance_name": "IDEA",
        "strategy_name": "Manual Trading",
        "iv_object_name": "IDEA",
        "instrument_id": 1010010000014366,
        "exchange_segment": "NSECM",
        "exchange_instrument_id": 1010010000014366,
        "instrument_name": "IDEA",
        "instrument_type": 1,
        "blitz_order_id": 3367140289,
        "exchange_order_id": "3084826041727943",
        "execution_id": "3084826041730509",
        "account": "",
        "client_id": "SIDD09",
        "order_type": "Market",
        "order_side": "Buy",
        "status": "New",
        "order_quantity": 1,
        "order_price": 0,
        "order_stop_price": 0,
        "order_trigger_price": 0,
        "last_traded_quantity": 0,
        "last_traded_price": 0,
        "cumulative_quantity": 0,
        "leaves_quantity": 1,
        "tif": "GFD",
        "order_expiry_date": 1760079432921,
        "order_disclosed_quantity": 0,
        "minimum_quantity": 0,
        "order_generated_date_time": 1760079432921,
        "last_request_date_time": 1760079432921,
        "exchange_transact_time": 1760099232000,
        "order_modification_count": 0,
        "order_trade_count": 0,
        "average_traded_price": 0,
        "average_traded_value": 0,
        "is_fictive_order": false,
        "reject_type": "None",
        "reject_type_reason": "",
        "order_tag": "NormalOrder",
        "ctcl_id": "153541",
        "algo_id": "0",
        "algo_category_id": "0",
        "clearing_firm_id": "",
        "pan_id": "GABPB5317L",
        "is_order_completed": false,
        "user_text": "",
        "execution_type": "New",
        "strategy_tag": "General",
        "sequence_number": 0
    },
    {
        "id": 27,
        "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
        "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
        "strategy_instance_id": "a78887e2-a295-4d21-b30d-a90cd170aad3",
        "strategy_instance_name": "IDEA",
        "strategy_name": "Manual Trading",
        "iv_object_name": "IDEA",
        "instrument_id": 1010010000014366,
        "exchange_segment": "NSECM",
        "exchange_instrument_id": 1010010000014366,
        "instrument_name": "IDEA",
        "instrument_type": 1,
        "blitz_order_id": 3367140289,
        "exchange_order_id": "3084826041727943",
        "execution_id": "3084826041730510",
        "account": "",
        "client_id": "SIDD09",
        "order_type": "Market",
        "order_side": "Buy",
        "status": "Filled",
        "order_quantity": 1,
        "order_price": 0,
        "order_stop_price": 0,
        "order_trigger_price": 0,
        "last_traded_quantity": 1,
        "last_traded_price": 6.87,
        "cumulative_quantity": 1,
        "leaves_quantity": 0,
        "tif": "GFD",
        "order_expiry_date": 1760079432922,
        "order_disclosed_quantity": 0,
        "minimum_quantity": 0,
        "order_generated_date_time": 1760079432922,
        "last_request_date_time": 1760079432922,
        "exchange_transact_time": 1760079432000,
        "order_modification_count": 0,
        "order_trade_count": 0,
        "average_traded_price": 6.87,
        "average_traded_value": 0,
        "is_fictive_order": false,
        "reject_type": "None",
        "reject_type_reason": "",
        "order_tag": "NormalOrder",
        "ctcl_id": "153541",
        "algo_id": "0",
        "algo_category_id": "0",
        "clearing_firm_id": "",
        "pan_id": "GABPB5317L",
        "is_order_completed": true,
        "user_text": "",
        "execution_type": "Fill",
        "strategy_tag": "General",
        "sequence_number": 0
    },
    {
        "id": 28,
        "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
        "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
        "strategy_instance_id": "a78887e2-a295-4d21-b30d-a90cd170aad3",
        "strategy_instance_name": "IDEA",
        "strategy_name": "Manual Trading",
        "iv_object_name": "IDEA",
        "instrument_id": 1010010000014366,
        "exchange_segment": "NSECM",
        "exchange_instrument_id": 1010010000014366,
        "instrument_name": "IDEA",
        "instrument_type": 1,
        "blitz_order_id": 3367140290,
        "exchange_order_id": "0",
        "execution_id": "0",
        "account": "",
        "client_id": "SIDD09",
        "order_type": "Limit",
        "order_side": "Buy",
        "status": "PendingNew",
        "order_quantity": 99,
        "order_price": 6.87,
        "order_stop_price": 0,
        "order_trigger_price": 0,
        "last_traded_quantity": 0,
        "last_traded_price": 0,
        "cumulative_quantity": 0,
        "leaves_quantity": 99,
        "tif": "GFD",
        "order_expiry_date": 1760079456283,
        "order_disclosed_quantity": 0,
        "minimum_quantity": 0,
        "order_generated_date_time": 1760079456283,
        "last_request_date_time": 1760079456283,
        "exchange_transact_time": 1760079456283,
        "order_modification_count": 0,
        "order_trade_count": 0,
        "average_traded_price": 0,
        "average_traded_value": 0,
        "is_fictive_order": false,
        "reject_type": "None",
        "reject_type_reason": "",
        "order_tag": "NormalOrder",
        "ctcl_id": "153541",
        "algo_id": "0",
        "algo_category_id": "0",
        "clearing_firm_id": "",
        "pan_id": "GABPB5317L",
        "is_order_completed": false,
        "user_text": "",
        "execution_type": "None",
        "strategy_tag": "General",
        "sequence_number": 0
    } 
]
```
</details>

## 2. Retrieve Order by BlitzOrderID

Fetch the details of a specific order in the OMS system using its unique BlitzOrderId. This endpoint returns all order-related information including status, executed trades, and metadata.

```bash
curl -X 'GET' \
  'http://api.blitz.com/api/orders/{BlitzOrderId}' \
  -H 'accept: application/json' \
  -H 'Authorization: Bearer YOUR_JWT_TOKEN'
```
### Request Structure
- No Body Required.

### Response Structuer

<details>
<summary>Click to view Order by BlitzOrderID JSON Body</summary>

```json
[
  {
    "id": 1,
    "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
    "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
    "strategy_instance_id": "8ababa4e-616c-468e-8672-70f64a8b9c8d",
    "strategy_instance_name": "RELIANCE",
    "strategy_name": "Manual Trading",
    "iv_object_name": "RELIANCE",
    "instrument_id": 1010010000002885,
    "exchange_segment": "NSECM",
    "exchange_instrument_id": 1010010000002885,
    "instrument_name": "RELIANCE",
    "instrument_type": 1,
    "blitz_order_id": 3345637833,
    "exchange_order_id": "0",
    "execution_id": "0",
    "account": "",
    "client_id": "SIDD09",
    "order_type": "Limit",
    "order_side": "Buy",
    "status": "PendingNew",
    "order_quantity": 60,
    "order_price": 1300.8,
    "order_stop_price": 0,
    "order_trigger_price": 0,
    "last_traded_quantity": 0,
    "last_traded_price": 0,
    "cumulative_quantity": 0,
    "leaves_quantity": 60,
    "tif": "GFD",
    "order_expiry_date": 1760333421586,
    "order_disclosed_quantity": 0,
    "minimum_quantity": 0,
    "order_generated_date_time": 1760333421586,
    "last_request_date_time": 1760333421586,
    "exchange_transact_time": 1760333421585,
    "order_modification_count": 0,
    "order_trade_count": 0,
    "average_traded_price": 0,
    "average_traded_value": 0,
    "is_fictive_order": false,
    "reject_type": "None",
    "reject_type_reason": "",
    "order_tag": "NormalOrder",
    "ctcl_id": "153541",
    "algo_id": "0",
    "algo_category_id": "0",
    "clearing_firm_id": "",
    "pan_id": "GABPB5317L",
    "is_order_completed": false,
    "user_text": "",
    "execution_type": "None",
    "strategy_tag": "General",
    "sequence_number": 0
  },
  {
    "id": 2,
    "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
    "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
    "strategy_instance_id": "8ababa4e-616c-468e-8672-70f64a8b9c8d",
    "strategy_instance_name": "RELIANCE",
    "strategy_name": "Manual Trading",
    "iv_object_name": "RELIANCE",
    "instrument_id": 1010010000002885,
    "exchange_segment": "NSECM",
    "exchange_instrument_id": 1010010000002885,
    "instrument_name": "RELIANCE",
    "instrument_type": 1,
    "blitz_order_id": 3345637833,
    "exchange_order_id": "3085784509505998",
    "execution_id": "3085784509505998",
    "account": "",
    "client_id": "SIDD09",
    "order_type": "Limit",
    "order_side": "Buy",
    "status": "New",
    "order_quantity": 60,
    "order_price": 1300.8,
    "order_stop_price": 0,
    "order_trigger_price": 0,
    "last_traded_quantity": 0,
    "last_traded_price": 0,
    "cumulative_quantity": 0,
    "leaves_quantity": 60,
    "tif": "GFD",
    "order_expiry_date": 1760333421594,
    "order_disclosed_quantity": 0,
    "minimum_quantity": 0,
    "order_generated_date_time": 1760333421594,
    "last_request_date_time": 1760333421594,
    "exchange_transact_time": 1760333421000,
    "order_modification_count": 0,
    "order_trade_count": 0,
    "average_traded_price": 0,
    "average_traded_value": 0,
    "is_fictive_order": false,
    "reject_type": "None",
    "reject_type_reason": "",
    "order_tag": "NormalOrder",
    "ctcl_id": "153541",
    "algo_id": "0",
    "algo_category_id": "0",
    "clearing_firm_id": "",
    "pan_id": "GABPB5317L",
    "is_order_completed": false,
    "user_text": "",
    "execution_type": "New",
    "strategy_tag": "General",
    "sequence_number": 0
  },
  {
    "id": 3,
    "entity_id": "163d2248-e81b-4cb3-9482-bb65e3e4ab3f",
    "strategy_id": "36250ee3-ad08-4e09-862f-83deee8cdef9",
    "strategy_instance_id": "8ababa4e-616c-468e-8672-70f64a8b9c8d",
    "strategy_instance_name": "RELIANCE",
    "strategy_name": "Manual Trading",
    "iv_object_name": "RELIANCE",
    "instrument_id": 1010010000002885,
    "exchange_segment": "NSECM",
    "exchange_instrument_id": 1010010000002885,
    "instrument_name": "RELIANCE",
    "instrument_type": 1,
    "blitz_order_id": 3345637833,
    "exchange_order_id": "3085784509505998",
    "execution_id": "3085784509505999",
    "account": "",
    "client_id": "SIDD09",
    "order_type": "Limit",
    "order_side": "Buy",
    "status": "Filled",
    "order_quantity": 60,
    "order_price": 1300.8,
    "order_stop_price": 0,
    "order_trigger_price": 0,
    "last_traded_quantity": 60,
    "last_traded_price": 1300.8,
    "cumulative_quantity": 60,
    "leaves_quantity": 0,
    "tif": "GFD",
    "order_expiry_date": 1760333421594,
    "order_disclosed_quantity": 0,
    "minimum_quantity": 0,
    "order_generated_date_time": 1760333421594,
    "last_request_date_time": 1760333421594,
    "exchange_transact_time": 1760333421000,
    "order_modification_count": 0,
    "order_trade_count": 0,
    "average_traded_price": 1300.8,
    "average_traded_value": 0,
    "is_fictive_order": false,
    "reject_type": "None",
    "reject_type_reason": "",
    "order_tag": "NormalOrder",
    "ctcl_id": "153541",
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
</details>

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
| blitz_order_id | integer | Order ID in Blitz system |
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

## 3. Place an Order

This endpoint allows you to submit a new order to the OMS trading system.
Orders can be placed across supported instruments and exchanges, with full control over price, quantity, type, and validity.
When an order is submitted, the system validates it for trading session availability, risk checks, and sufficient margin before routing it for execution.

> Note:Successful API submission does not guarantee execution at the exchange. The response only confirms that the order has been registered with the OMS system.


```bash
curl -X 'POST' \
  'http://api.blitz.com/api/order/placeOrder' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer YOUR_JWT_TOKEN' \
  -d 'Request JSON'

```
### Request Body

```json
{
    "quantity": 10,
    "product": "NRML",
    "tif": "GFD",
    "price": 150.5,
    "orderType": "Limit",
    // "instrumentId": 1010010000010666,
    "symbol": "NSECM|PNB", 
    "orderSide": "Buy",
    "disclosedQuantity": 0,
    "stopPrice": 0,
    "clientId": "CLIENT_001",
    "tiF_GTD_Date": "2025-10-08",
    
  }'

```

> **Note**
    - Either `instrumentId` **or** `symbol` must be provided in the request.  
        If `symbol` is sent, the system will automatically fetch the corresponding `instrumentId`.  
        If `instrumentId` is sent, the system will verify its validity before placing the order.
    - If both are sent, `instrumentId` will take priority.  


### Response Body
```json
{
    "status": "success",
    "message": "Request processed successfully",
    "data": {
        "blitzOrderId": 23071859690000006
    }
}
```

### Field Descriptions

| Field | Type | Description |
|-------|------|------------|
| quantity | number | Quantity of the order to be placed |
| product | string | Product type for the order: MIS, NRML, CNC, MTF, or NONE |
| tif | string | Time-in-force for the order: GFD, GTC, IOC, FOK, GTD, or None |
| price | number | Price at which the order should be executed |
| orderType | string | Type of order: Market, Limit, Stop, StopLimit, or Unknown |
| instrumentId | integer | Internal ID of the instrument to trade |
| orderSide | string | Side of the order: Buy or Sell |
| disclosedQuantity | number | Quantity disclosed for iceberg orders |
| stopPrice | number | Stop price for stop or stop-limit orders |
| clientId | string | ID of the client placing the order |
| tiF_GTD_Date | string | Expiry date for GTD orders in YYYY-MM-DD format |
| positionEffectOrderFlag | boolean | Flag indicating whether this order opens or closes a position |
| exchangeTradingSessionOrderFlag | boolean | Flag specifying the exchange trading session (Pre-open, Normal, Pre-close, etc.) |
| isFictive | boolean | True if the order is simulated/fictive (not a real order) |

### Response Codes

| HTTP Code | Description |
|------------|-------------|
| **200** |  **Order successfully placed.** The order has been accepted and registered in the OMS system. |
| **400** |  **Bad Request.** One or more parameters are invalid or missing in the request body. |
| **401** |  **Unauthorized.** The request is missing a valid JWT token or the token has expired. |
| **403** |  **Forbidden.** The order cannot be placed due to insufficient margin, risk checks, or permissions. |
| **404** |  **Not Found.** The specified instrument or client ID does not exist. |
| **500** |  **Internal Server Error.** A system or exchange-level error occurred while processing the order. |


> Tip for Placing Orders 
> -  Always confirm the **order status** after placement using the returned `orderId` or `exchangeOrderId`.  
> -  Ensure **sufficient margin/funds** are available before placing the order to prevent rejections.  
> -  Place orders **only during active market hours** for faster acknowledgment and execution.    


## 4. Modify Order

The **Modify Order** endpoint allows you to update an existing order’s parameters such as **quantity**, **price**, **stop price**, or **validity**.  
Use this API to adjust open or pending orders before they are executed at the exchange.

> Note
    Only orders in *open* or *pending* states can be modified.  
    > Once an order is executed or cancelled, modification requests will be rejected.
    - After modification, query the [orders](#fetching-orders) to confirm that the changes were successfully applied. 


---

```bash
curl -X 'PUT' \
  'http://api.blitz.com/api/order/modifyOrder' \
  -H 'accept: */*' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <your_jwt_token>' \
  -d 'Request Json'
```

### Request Body

```json
{
  "modifiedOrderQuantity": 30,
  "orderType": 50,
  "instrumentId": 1010010000002885,
  "disclosedQuantity": 0,
  "stopPrice": 0,
  "tif": "GFD",
  "exchangeOrderId": 3084826041727955,
  "price": 1422,
  "quantity": 10,
  "TiF_GTD_Date": "2025-12-31"  
}
```
### Field Descriptions

| Field | Type | Description |
|-------|------|------------|
| modifiedOrderQuantity | number | Updated quantity of the order |
| price | number | Updated price at which the order should be executed |
| exchangeOrderId | integer | Exchange-assigned order ID identifying which order to modify |
| orderType | string | Type of order: Market, Limit, Stop, StopLimit, or Unknown |
| instrumentId | integer | Internal ID of the instrument being traded |
| disclosedQuantity | number | Updated disclosed quantity for iceberg orders |
| stopPrice | number | Updated stop price for stop or stop-limit orders |
| tif | string | Time-in-force for the order: GFD, GTC, IOC, FOK, GTD, or None |
| tiF_GTD_Date | string | Expiry date for GTD orders in `YYYY-MM-DD` format |

### Response Body
```json
{
    "status": "success",
    "message": "Request processed successfully",
    "data": {
        "blitzOrderId": 23071859690000006
    }
}
```
### Response Codes

| HTTP Code | Description |
|------------|-------------|
| **200** | **Order modified successfully.** The order update has been accepted by the Blitz system. |
| **400** | **Bad Request.** One or more parameters are invalid or missing. |
| **401** | **Unauthorized.** Missing or invalid JWT token. |
| **403** | **Forbidden.** The order cannot be modified (already executed or cancelled). |
| **404** | **Not Found.** The specified `exchangeOrderId` or instrument does not exist. |
| **500** | **Internal Server Error.** A system or exchange-level error occurred while processing the modification. |

> Tip for Modifying Orders
- Always verify the **current order status** before attempting to modify it. Only open or pending orders can be changed.  
- Modify orders **during market hours** to ensure updates are accepted and reflected quickly.    
- Avoid frequent or large modifications in short intervals to prevent exchange-level throttling or rejection.  
- Confirm the **modified parameters** (price, quantity, stop price) meet exchange and instrument-specific limits.   


## 5. Cancel Order {#cancel-order}
The **Cancel Order** endpoint allows you to cancel an existing open or pending order using its unique `InstrumentId` and `ExchangeOrderId`.

:::note
Only orders that are in *open* or *pending* state can be cancelled.  
> Orders that are already executed or expired cannot be cancelled.
:::

### Parameters

| Name | Type | Description |
|------|------|------------|
| InstrumentId | integer | Internal ID of the instrument for which the order was placed |
| ExchangeOrderId | number | Exchange-assigned ID of the order to cancel |

```bash
curl -X 'DELETE' \
  'http://api.blitz.com/api/order/cancelOrder?InstrumentId=123&ExchangeOrderId=456' \
  -H 'accept: */*' \
  -H 'Authorization: Bearer YOUR_JWT_TOKEN'
```
### Response 

```json
{
  "Message": "Order cancelled successfully."
}
```
### Response Codes

| HTTP Code | Description |
|------------|-------------|
| **200** | **Order cancelled successfully.** The order has been removed from the OMS system. |
| **400** | **Bad Request.** Invalid or missing parameters. |
| **401** | **Unauthorized.** Missing or invalid JWT token. |
| **403** | **Forbidden.** The order cannot be cancelled (already executed or expired). |
| **404** | **Not Found.** The specified `ExchangeOrderId` or instrument does not exist. |
| **500** | **Internal Server Error.** A system or exchange-level error occurred while processing the cancellation. |

:::tip Tip for Cancelling Orders

- Confirm that the order is in an **open or pending** state before attempting cancellation. Executed or expired orders cannot be cancelled.  
- Use the correct combination of **InstrumentId** and **ExchangeOrderId** to ensure the intended order is cancelled.   
- Always verify the **cancellation status** using the order status or history endpoint after sending the request.  
- Avoid sending multiple cancellation requests for the same order to prevent duplicate or conflicting actions.  
:::

> **Note:** Ensure the JWT token is valid and included in the `Authorization` header. Without it, the server will respond with `401 Unauthorized`.

