# @sabbour/adaptive-ui-google-flights-pack

An [Adaptive UI](https://github.com/sabbour/adaptive-ui-framework) component pack for **Google Flights** integration. Provides live flight search results and styled flight link cards with protobuf-encoded Google Flights URLs.

## Components

| Component | Props | Description |
|-----------|-------|-------------|
| `flightSearch` | `from`, `to`, `date`, `returnDate?`, `trip?`, `seat?`, `adults?`, `bind?` | Interactive flight results panel. Shows live results via CORS proxy, or falls back to a "Search on Google Flights" link. Users can click a flight to select it. |
| `flightCard` | `from`, `to`, `date`, `returnDate?`, `trip?`, `seat?`, `adults?` | Styled link card that opens Google Flights with the exact search query. Use for quick flight references in itinerary summaries. |

## Tools

| Tool | Description |
|------|-------------|
| `search_flights` | Search Google Flights for real flight options. Returns prices, airlines, times, stops, and carbon emissions. Requires a CORS proxy. |

## How It Works

The pack builds protobuf-encoded URLs that match Google Flights' internal query format, enabling direct deep links to specific searches. When a CORS proxy is configured, it can also fetch and parse live flight results from Google Flights HTML.

### Flight parameters

- `from` / `to`: 3-letter IATA airport codes (e.g., `JFK`, `NRT`, `CDG`)
- `date` / `returnDate`: `YYYY-MM-DD` format
- `trip`: `"one-way"` or `"round-trip"` (auto-detects if `returnDate` is provided)
- `seat`: `"economy"`, `"premium-economy"`, `"business"`, or `"first"`

## Installation

```bash
npm install @sabbour/adaptive-ui-google-flights-pack
```

```typescript
import { createGoogleFlightsPack } from '@sabbour/adaptive-ui-google-flights-pack';

const flightsPack = createGoogleFlightsPack();
// Register with your AdaptiveApp
```

## Prerequisites

- A CORS proxy URL (configured via the settings panel) for live flight search results
- Without a proxy, components fall back to direct Google Flights links

## License

MIT
