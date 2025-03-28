# Weather CLI Application

A command-line interface application that provides weather information and alerts for US locations using the National Weather Service (NWS) API.

## Features

- Get weather alerts for any US state
- Get detailed weather forecasts for any US location using coordinates
- Supports temperature, wind conditions, and short forecast descriptions
- Real-time data from the National Weather Service

## Prerequisites

- Node.js (v16 or higher)
- npm or yarn package manager

## Installation

1. Clone the repository:
```bash
git clone https://github.com/akaramanapp/weather-cli.git
cd weather-cli
```

2. Install dependencies:
```bash
npm install
```

3. Build the application:
```bash
npm run build
```

## Usage

The application provides two main commands:

### Get Weather Alerts

Retrieve active weather alerts for a specific US state using the two-letter state code:

```bash
weather get-alerts --state CA
```

### Get Weather Forecast

Get the weather forecast for a specific location using latitude and longitude coordinates:

```bash
weather get-forecast --latitude 37.7749 --longitude -122.4194
```

## Project Structure

```
weather/
├── src/
│   └── index.ts    # Main application code
├── build/          # Compiled JavaScript files
├── package.json    # Project dependencies and scripts
└── tsconfig.json   # TypeScript configuration
```

## Technical Details

- Built with TypeScript
- Uses the Model Context Protocol SDK for CLI interface
- Interfaces with the National Weather Service (NWS) API
- ES2022 target with Node16 module resolution

## Development

To modify or extend the application:

1. Make changes in the `src/index.ts` file
2. Rebuild the application:
```bash
npm run build
```

## Dependencies

- @modelcontextprotocol/sdk: CLI interface framework
- zod: Runtime type checking and validation
- TypeScript: Development dependency for type safety

## License

ISC

## Notes

- This application only works for US locations as it uses the National Weather Service API
- API requests are rate-limited and require a User-Agent header
- All coordinates should be in decimal degrees format 