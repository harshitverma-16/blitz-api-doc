# LTP API

## Overview

The **LTP (Last Traded Price) API** provides real-time last traded price data for a list of instrument IDs. This is useful for fetching the latest market price of stocks, indices, or derivatives.

---

## Endpoint

| Method | URL                    |
|--------|------------------------|
| POST   | `/api/marketfeed/ltp` |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## Request Body

| Field          | Type     | Description                            | Required |
|----------------|----------|----------------------------------------|----------|
| InstrumentIds  | array    | List of instrument IDs (numeric array) | Yes      |

### Example

```json
{
  "InstrumentIds": [
    1010010002000001,
    1010010002000002,
    1010010000000025,
    1010010000002885,
    2053580000060968,
    2041920000055251
  ]
}
```
### Successful Response (200 OK)
```json
{
    {
  "data": {
    "1010010000000025": {
      "InstrumentID": 1010010000000025,
      "InstrumentName": "ADANIENT",
      "LTP": 3121.95
    },
    "1010010000002885": {
      "InstrumentID": 1010010000002885,
      "InstrumentName": "RELIANCE",
      "LTP": 3186.3
    },
    "1010010002000001": {
      "InstrumentID": 1010010002000001,
      "InstrumentName": "NIFTY 50",
      "LTP": 24407.3
    },
    "1010010002000002": {
      "InstrumentID": 1010010002000002,
      "InstrumentName": "NIFTY BANK",
      "LTP": 52420.75
    },
    "2041920000055251": {
      "InstrumentID": 2041920000055251,
      "InstrumentName": "BANKNIFTY10JUL2453600PE",
      "LTP": 1209.35
    }
  },
  "status": "success"
}

}
```
### Error Response (400 / 500)
```json
 {
  "status": "error",
  "message": "Invalid or missing instrument IDs.",
  "error": "InstrumentIds array must not be empty."
}
