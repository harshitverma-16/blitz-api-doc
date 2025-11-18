# Historical Data API

## Overview
The Historical Data API provides OHLCV (Open, High, Low, Close, Volume) data for a given instrument over a specified date range and interval. This is useful for charting, backtesting, analytics, and historical market insights.

---

## Endpoint

| Method | URL |
|--------|-----------------------------|
| POST   | **/marketfeed/historicalData** |

---

## Headers

| Header | Value | Required |
|--------|--------|----------|
| Content-Type | application/json | Yes |
| Accept | */* | Yes |

---

## Request Body

| Field | Type | Description | Required |
|--------|--------|-----------------------------|----------|
| InstrumentId | number | Unique instrument ID for which data is requested | Yes |
| FromDate | string (YYYY-MM-DD) | Start date for historical data | Yes |
| ToDate | string (YYYY-MM-DD) | End date for historical data | Yes |
| Interval | string | Candle interval (e.g., `"1m"`, `"5m"`, `"15m"`, `"1h"`, `"1d"`) | Yes |

---

### Example

```json
{
  "InstrumentId": 1010010000002885,
  "FromDate": "2024-01-01",
  "ToDate": "2024-01-10",
  "Interval": "1d"
}
```

---

### Successful Response (200 OK)
```json
{
  "status": "success",
  "data": {
    "InstrumentID": 1010010000002885,
    "InstrumentName": "RELIANCE",
    "Interval": "1d",
    "Candles": [
      {
        "Date": "2024-01-01",
        "Open": 2890.50,
        "High": 2912.00,
        "Low": 2875.10,
        "Close": 2901.25,
        "Volume": 3289121
      },
      {
        "Date": "2024-01-02",
        "Open": 2901.25,
        "High": 2938.40,
        "Low": 2895.00,
        "Close": 2922.30,
        "Volume": 4120051
      }
    ]
  }
}

```

### Error Response (400 / 500)

```json
{
  "status": "error",
  "message": "Invalid request parameters.",
  "error": "InstrumentId, FromDate, ToDate, and Interval are required fields."
}
```