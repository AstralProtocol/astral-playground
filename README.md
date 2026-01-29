# Astral Playground

Interactive playground for exploring verifiable geospatial computations with [Astral Protocol](https://astral.global).

## What is this?

Astral Playground lets you experiment with geospatial operations and publish the results as on-chain attestations via [EAS (Ethereum Attestation Service)](https://attest.sh).

**Features:**
- Interactive map with draggable markers and polygon/line drawing
- Real-time preview using Turf.js
- Verified results computed via PostGIS in a Trusted Execution Environment
- Publish attestations to Ethereum, Base, Sepolia, or Base Sepolia
- SDK and cURL code snippets for integration

## Supported Operations

| Operation | Description | Input |
|-----------|-------------|-------|
| **Distance** | Distance between two points | 2 points |
| **Within** | Is point A within radius of point B? | 2 points + radius |
| **Contains** | Does polygon contain point? | polygon + point |
| **Intersects** | Do geometries overlap? | 2 geometries |
| **Area** | Area of a polygon | polygon |
| **Length** | Length of a line | linestring |

## Getting Started

### Prerequisites

- Node.js 18+
- [Mapbox access token](https://account.mapbox.com/access-tokens/)

### Installation

```bash
npm install
```

### Configuration

Copy the example environment file and add your Mapbox token:

```bash
cp .env.example .env
```

Edit `.env`:

```
VITE_MAPBOX_TOKEN=pk.your_mapbox_public_token
VITE_API_URL=https://api.astral.global
```

### Development

```bash
npm run dev
```

Open [http://localhost:5173](http://localhost:5173)

### Build

```bash
npm run build
```

## Usage

### Preview Mode

1. Select an operation from the dropdown
2. Drag markers or draw polygons on the map
3. See real-time preview results (Turf.js approximation)
4. Click "Get Verified Result" for precise PostGIS computation

### Policy Builder Mode

1. Switch to "Policy Builder" tab
2. Connect your wallet
3. Select target chain and schema UID
4. Compute verified result
5. Publish attestation on-chain

## Tech Stack

- [React 19](https://react.dev) + [TypeScript](https://www.typescriptlang.org)
- [Vite](https://vite.dev)
- [Mapbox GL](https://docs.mapbox.com/mapbox-gl-js/) + [react-map-gl](https://visgl.github.io/react-map-gl/)
- [Turf.js](https://turfjs.org) for client-side geospatial operations
- [wagmi](https://wagmi.sh) + [RainbowKit](https://www.rainbowkit.com) for wallet connection
- [viem](https://viem.sh) for Ethereum interactions

## Related

- [Astral Protocol](https://astral.global) - Verifiable location infrastructure
- [Astral API Docs](https://docs.astral.global) - API reference
- [EAS](https://attest.sh) - Ethereum Attestation Service

## License

MIT
