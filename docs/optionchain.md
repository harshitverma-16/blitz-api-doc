# Option Chain 

## Overview

The **Option Chain API** provides the latest option chain data for a given symbol and expiry date. It returns detailed information about call and put options across multiple strike prices.

---

## Endpoint

| Method | URL                            |
|--------|---------------------------------|
| POST   | `/api/marketfeed/optionChain`  |

---

## Headers

| Header        | Value             | Required |
|---------------|-------------------|----------|
| Content-Type  | application/json  | Yes      |
| Accept        | */*               | Yes      |

---

## Request Body

| Field       | Type   | Description                                           | Required |
|-------------|--------|-------------------------------------------------------|----------|
| symbol      | string | Trading symbol (e.g., `"NIFTY"`, `"BANKNIFTY"`)      | Yes      |
| expiryDate  | string | Expiry date of the option in `YYYY-MM-DD` format     | Yes      |

### Example

```json
{
  "symbol": "NIFTY",
  "expiryDate": "2024-07-11"
}
```
### Successful Response (200 OK)
```json
{
    "status": "success",
    "data": {
        "spotPrice": 21991.4,
        "expiryDate": "2025-04-09",
        "atm": 22000,
        "chains": [
            {
                "strikePrice": 21000,
                "callOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": -3.42,
                    "delta": 1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 1085,
                    "iv": 0,
                    "price": 996.75,
                    "rho": 1.15
                },
                "putOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": 0,
                    "delta": 0,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 69.1,
                    "iv": 0,
                    "price": 0,
                    "rho": -0
                }
            },
            {
                "strikePrice": 21050,
                "callOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": -3.43,
                    "delta": 1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 1047.2,
                    "iv": 0,
                    "price": 946.77,
                    "rho": 1.15
                },
                "putOption": {
                    "gamma": 0.0002,
                    "vega": 3.78,
                    "theta": -54.67,
                    "delta": -0.15,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 74.65,
                    "iv": 58.4,
                    "price": 74.83,
                    "rho": -0.18
                }
            },
            {
                "strikePrice": 21100,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 4.26,
                    "theta": -69.65,
                    "delta": 0.82,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 999.2,
                    "iv": 62.82,
                    "price": 998.19,
                    "rho": 0.93
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 3.95,
                    "theta": -56.2,
                    "delta": -0.16,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 79.7,
                    "iv": 57.58,
                    "price": 79.88,
                    "rho": -0.2
                }
            },
            {
                "strikePrice": 21150,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 4.43,
                    "theta": -71.79,
                    "delta": 0.81,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 956.95,
                    "iv": 62.33,
                    "price": 955.96,
                    "rho": 0.92
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 4.11,
                    "theta": -57.69,
                    "delta": -0.17,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 85.05,
                    "iv": 56.74,
                    "price": 85.24,
                    "rho": -0.21
                }
            },
            {
                "strikePrice": 21200,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 4.5,
                    "theta": -70.03,
                    "delta": 0.8,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 905.95,
                    "iv": 59.8,
                    "price": 904.98,
                    "rho": 0.92
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 4.28,
                    "theta": -59.18,
                    "delta": -0.18,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 90.85,
                    "iv": 55.91,
                    "price": 91.06,
                    "rho": -0.22
                }
            },
            {
                "strikePrice": 21250,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 4.79,
                    "theta": -76.47,
                    "delta": 0.78,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 875.5,
                    "iv": 61.64,
                    "price": 874.54,
                    "rho": 0.89
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 4.46,
                    "theta": -60.77,
                    "delta": -0.19,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 97.4,
                    "iv": 55.15,
                    "price": 97.64,
                    "rho": -0.24
                }
            },
            {
                "strikePrice": 21300,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 4.97,
                    "theta": -78.68,
                    "delta": 0.77,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 835.65,
                    "iv": 61.28,
                    "price": 834.73,
                    "rho": 0.88
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 4.63,
                    "theta": -62.02,
                    "delta": -0.21,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 103.75,
                    "iv": 54.23,
                    "price": 103.98,
                    "rho": -0.25
                }
            },
            {
                "strikePrice": 21350,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 5.04,
                    "theta": -76.11,
                    "delta": 0.76,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 783.55,
                    "iv": 58.37,
                    "price": 782.63,
                    "rho": 0.88
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 4.81,
                    "theta": -63.55,
                    "delta": -0.22,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 111.45,
                    "iv": 53.49,
                    "price": 111.69,
                    "rho": -0.27
                }
            },
            {
                "strikePrice": 21400,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 5.3,
                    "theta": -82.63,
                    "delta": 0.74,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 757.55,
                    "iv": 60.46,
                    "price": 756.66,
                    "rho": 0.85
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 4.99,
                    "theta": -64.82,
                    "delta": -0.23,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 119.2,
                    "iv": 52.65,
                    "price": 119.5,
                    "rho": -0.29
                }
            },
            {
                "strikePrice": 21450,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 5.34,
                    "theta": -77.91,
                    "delta": 0.73,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 700,
                    "iv": 56.42,
                    "price": 699.1,
                    "rho": 0.85
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 5.17,
                    "theta": -66,
                    "delta": -0.25,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 127.65,
                    "iv": 51.81,
                    "price": 127.93,
                    "rho": -0.31
                }
            },
            {
                "strikePrice": 21500,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 5.54,
                    "theta": -81.02,
                    "delta": 0.71,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 666.4,
                    "iv": 56.77,
                    "price": 665.53,
                    "rho": 0.82
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 5.34,
                    "theta": -67.05,
                    "delta": -0.27,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 136.6,
                    "iv": 50.95,
                    "price": 136.91,
                    "rho": -0.33
                }
            },
            {
                "strikePrice": 21550,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 5.65,
                    "theta": -79.82,
                    "delta": 0.7,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 620.6,
                    "iv": 54.78,
                    "price": 619.76,
                    "rho": 0.81
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 5.52,
                    "theta": -68.15,
                    "delta": -0.28,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 146.8,
                    "iv": 50.19,
                    "price": 147.15,
                    "rho": -0.35
                }
            },
            {
                "strikePrice": 21600,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 5.78,
                    "theta": -79.04,
                    "delta": 0.69,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 576.95,
                    "iv": 53.08,
                    "price": 576.1,
                    "rho": 0.79
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 5.68,
                    "theta": -68.69,
                    "delta": -0.3,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 156.45,
                    "iv": 49.19,
                    "price": 156.83,
                    "rho": -0.37
                }
            },
            {
                "strikePrice": 21650,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 5.92,
                    "theta": -80.06,
                    "delta": 0.67,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 540.5,
                    "iv": 52.51,
                    "price": 539.69,
                    "rho": 0.77
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 5.83,
                    "theta": -69.27,
                    "delta": -0.32,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 167.6,
                    "iv": 48.31,
                    "price": 168,
                    "rho": -0.4
                }
            },
            {
                "strikePrice": 21700,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 6.07,
                    "theta": -81.94,
                    "delta": 0.64,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 508.75,
                    "iv": 52.56,
                    "price": 507.98,
                    "rho": 0.75
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 5.98,
                    "theta": -69.61,
                    "delta": -0.34,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 179.45,
                    "iv": 47.4,
                    "price": 179.87,
                    "rho": -0.42
                }
            },
            {
                "strikePrice": 21750,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.17,
                    "theta": -80.14,
                    "delta": 0.63,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 465.45,
                    "iv": 50.56,
                    "price": 464.73,
                    "rho": 0.73
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 6.12,
                    "theta": -69.66,
                    "delta": -0.36,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 191.95,
                    "iv": 46.44,
                    "price": 192.38,
                    "rho": -0.45
                }
            },
            {
                "strikePrice": 21800,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.28,
                    "theta": -80.93,
                    "delta": 0.6,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 433.45,
                    "iv": 50.24,
                    "price": 432.75,
                    "rho": 0.7
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 6.24,
                    "theta": -69.63,
                    "delta": -0.39,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 206.05,
                    "iv": 45.58,
                    "price": 206.53,
                    "rho": -0.48
                }
            },
            {
                "strikePrice": 21850,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.36,
                    "theta": -80.22,
                    "delta": 0.58,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 397.85,
                    "iv": 49.17,
                    "price": 397.13,
                    "rho": 0.68
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 6.34,
                    "theta": -69.24,
                    "delta": -0.41,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 220.9,
                    "iv": 44.66,
                    "price": 221.41,
                    "rho": -0.51
                }
            },
            {
                "strikePrice": 21900,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.43,
                    "theta": -79.52,
                    "delta": 0.56,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 364.35,
                    "iv": 48.27,
                    "price": 363.67,
                    "rho": 0.65
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.42,
                    "theta": -68.65,
                    "delta": -0.44,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 237.35,
                    "iv": 43.8,
                    "price": 237.87,
                    "rho": -0.54
                }
            },
            {
                "strikePrice": 21950,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.47,
                    "theta": -78.92,
                    "delta": 0.53,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 333.65,
                    "iv": 47.62,
                    "price": 333,
                    "rho": 0.62
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.47,
                    "theta": -67.63,
                    "delta": -0.47,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 254.65,
                    "iv": 42.88,
                    "price": 255.21,
                    "rho": -0.58
                }
            },
            {
                "strikePrice": 22000,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.49,
                    "theta": -76.96,
                    "delta": 0.51,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 299.95,
                    "iv": 46.32,
                    "price": 299.35,
                    "rho": 0.59
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.49,
                    "theta": -66.29,
                    "delta": -0.5,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 273.35,
                    "iv": 41.97,
                    "price": 273.98,
                    "rho": -0.61
                }
            },
            {
                "strikePrice": 22050,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.48,
                    "theta": -75.46,
                    "delta": 0.48,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 270.85,
                    "iv": 45.52,
                    "price": 270.25,
                    "rho": 0.56
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.48,
                    "theta": -64.6,
                    "delta": -0.53,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 293.7,
                    "iv": 41.08,
                    "price": 294.32,
                    "rho": -0.65
                }
            },
            {
                "strikePrice": 22100,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.44,
                    "theta": -73.55,
                    "delta": 0.45,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 242.8,
                    "iv": 44.68,
                    "price": 242.27,
                    "rho": 0.53
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.43,
                    "theta": -62.48,
                    "delta": -0.56,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 315.4,
                    "iv": 40.17,
                    "price": 316.07,
                    "rho": -0.69
                }
            },
            {
                "strikePrice": 22150,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.37,
                    "theta": -71.27,
                    "delta": 0.42,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 216.15,
                    "iv": 43.83,
                    "price": 215.66,
                    "rho": 0.5
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.33,
                    "theta": -60.23,
                    "delta": -0.59,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 339.75,
                    "iv": 39.42,
                    "price": 340.46,
                    "rho": -0.73
                }
            },
            {
                "strikePrice": 22200,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.26,
                    "theta": -68.64,
                    "delta": 0.39,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 191.15,
                    "iv": 43,
                    "price": 190.68,
                    "rho": 0.46
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 6.19,
                    "theta": -57.03,
                    "delta": -0.62,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 363.8,
                    "iv": 38.35,
                    "price": 364.53,
                    "rho": -0.77
                }
            },
            {
                "strikePrice": 22250,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 6.11,
                    "theta": -65.83,
                    "delta": 0.36,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 168.3,
                    "iv": 42.27,
                    "price": 167.87,
                    "rho": 0.43
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 5.99,
                    "theta": -53.04,
                    "delta": -0.66,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 388.4,
                    "iv": 37.07,
                    "price": 389.18,
                    "rho": -0.81
                }
            },
            {
                "strikePrice": 22300,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 5.92,
                    "theta": -62.68,
                    "delta": 0.33,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 147.05,
                    "iv": 41.54,
                    "price": 146.63,
                    "rho": 0.39
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 5.75,
                    "theta": -49.82,
                    "delta": -0.69,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 418.8,
                    "iv": 36.45,
                    "price": 419.65,
                    "rho": -0.85
                }
            },
            {
                "strikePrice": 22350,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 5.7,
                    "theta": -59.29,
                    "delta": 0.3,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 127.65,
                    "iv": 40.86,
                    "price": 127.26,
                    "rho": 0.36
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 5.5,
                    "theta": -47.29,
                    "delta": -0.72,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 454,
                    "iv": 36.37,
                    "price": 454.84,
                    "rho": -0.89
                }
            },
            {
                "strikePrice": 22400,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 5.44,
                    "theta": -55.69,
                    "delta": 0.28,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 110,
                    "iv": 40.22,
                    "price": 109.69,
                    "rho": 0.33
                },
                "putOption": {
                    "gamma": 0.0006,
                    "vega": 5.12,
                    "theta": -41.79,
                    "delta": -0.75,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 483.2,
                    "iv": 34.87,
                    "price": 484.11,
                    "rho": -0.94
                }
            },
            {
                "strikePrice": 22450,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 5.15,
                    "theta": -51.93,
                    "delta": 0.25,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 94.25,
                    "iv": 39.63,
                    "price": 93.94,
                    "rho": 0.29
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 4.66,
                    "theta": -35.8,
                    "delta": -0.79,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 514.4,
                    "iv": 33.28,
                    "price": 515.38,
                    "rho": -0.98
                }
            },
            {
                "strikePrice": 22500,
                "callOption": {
                    "gamma": 0.0005,
                    "vega": 4.84,
                    "theta": -48.2,
                    "delta": 0.22,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 80.5,
                    "iv": 39.15,
                    "price": 80.24,
                    "rho": 0.26
                },
                "putOption": {
                    "gamma": 0.0005,
                    "vega": 4.18,
                    "theta": -30.45,
                    "delta": -0.83,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 550,
                    "iv": 32.11,
                    "price": 550.98,
                    "rho": -1.03
                }
            },
            {
                "strikePrice": 22550,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 4.5,
                    "theta": -44.09,
                    "delta": 0.2,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 67.65,
                    "iv": 38.55,
                    "price": 67.4,
                    "rho": 0.23
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 3.81,
                    "theta": -27.37,
                    "delta": -0.85,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 592.05,
                    "iv": 32.09,
                    "price": 593.07,
                    "rho": -1.06
                }
            },
            {
                "strikePrice": 22600,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 4.15,
                    "theta": -40.06,
                    "delta": 0.17,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 56.55,
                    "iv": 38.03,
                    "price": 56.33,
                    "rho": 0.2
                },
                "putOption": {
                    "gamma": 0.0004,
                    "vega": 2.99,
                    "theta": -18.43,
                    "delta": -0.89,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 625.6,
                    "iv": 29.1,
                    "price": 626.66,
                    "rho": -1.11
                }
            },
            {
                "strikePrice": 22650,
                "callOption": {
                    "gamma": 0.0004,
                    "vega": 3.8,
                    "theta": -36.37,
                    "delta": 0.15,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 47.45,
                    "iv": 37.69,
                    "price": 47.26,
                    "rho": 0.18
                },
                "putOption": {
                    "gamma": 0.0003,
                    "vega": 2.69,
                    "theta": -16.46,
                    "delta": -0.91,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 672,
                    "iv": 29.53,
                    "price": 673.09,
                    "rho": -1.13
                }
            },
            {
                "strikePrice": 22700,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 3.45,
                    "theta": -32.67,
                    "delta": 0.13,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 39.4,
                    "iv": 37.33,
                    "price": 39.25,
                    "rho": 0.15
                },
                "putOption": {
                    "gamma": 0.0002,
                    "vega": 1.67,
                    "theta": -7.09,
                    "delta": -0.95,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 710,
                    "iv": 25.61,
                    "price": 711.15,
                    "rho": -1.18
                }
            },
            {
                "strikePrice": 22750,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 3.13,
                    "theta": -29.5,
                    "delta": 0.11,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 33.15,
                    "iv": 37.2,
                    "price": 33.01,
                    "rho": 0.13
                },
                "putOption": {
                    "gamma": 0.0001,
                    "vega": 0.85,
                    "theta": -1.09,
                    "delta": -0.98,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 754.35,
                    "iv": 22.45,
                    "price": 755.53,
                    "rho": -1.22
                }
            },
            {
                "strikePrice": 22800,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 2.81,
                    "theta": -26.35,
                    "delta": 0.1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 27.55,
                    "iv": 37.02,
                    "price": 27.45,
                    "rho": 0.12
                },
                "putOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": 3.77,
                    "delta": -1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 796.85,
                    "iv": 0,
                    "price": 802.56,
                    "rho": -1.25
                }
            },
            {
                "strikePrice": 22850,
                "callOption": {
                    "gamma": 0.0003,
                    "vega": 2.55,
                    "theta": -23.99,
                    "delta": 0.09,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 23.65,
                    "iv": 37.19,
                    "price": 23.54,
                    "rho": 0.1
                },
                "putOption": {
                    "gamma": 0.0001,
                    "vega": 0.93,
                    "theta": -2.33,
                    "delta": -0.98,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 855.2,
                    "iv": 25.93,
                    "price": 856.38,
                    "rho": -1.22
                }
            },
            {
                "strikePrice": 22900,
                "callOption": {
                    "gamma": 0.0002,
                    "vega": 2.29,
                    "theta": -21.55,
                    "delta": 0.07,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 20,
                    "iv": 37.25,
                    "price": 19.9,
                    "rho": 0.09
                },
                "putOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": 3.79,
                    "delta": -1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 894.1,
                    "iv": 0,
                    "price": 902.52,
                    "rho": -1.25
                }
            },
            {
                "strikePrice": 22950,
                "callOption": {
                    "gamma": 0.0002,
                    "vega": 2.07,
                    "theta": -19.64,
                    "delta": 0.07,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 17.3,
                    "iv": 37.53,
                    "price": 17.21,
                    "rho": 0.08
                },
                "putOption": {
                    "gamma": 0,
                    "vega": 0,
                    "theta": 3.8,
                    "delta": -1,
                    "oiPercentage": 0,
                    "oi": 0,
                    "ltp": 936,
                    "iv": 0,
                    "price": 952.5,
                    "rho": -1.26
                }
            }
        ]
    }
}
```
## Error Response (400 / 500)
```json
{
  "status": "error",
  "message": "Invalid input or server error.",
  "error": "Expiry date is required."
}


