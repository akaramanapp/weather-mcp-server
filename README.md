# Weather MCP Server

A Model Context Protocol (MCP) server that provides weather information and alerts for US locations using the National Weather Service (NWS) API. This server is designed to be used by AI agents through the Model Context Protocol.

## Features

- Tool for getting weather alerts for any US state
- Tool for getting detailed weather forecasts for any US location using coordinates
- Supports temperature, wind conditions, and short forecast descriptions
- Real-time data from the National Weather Service

## Prerequisites

- Node.js (v16 or higher)
- npm or yarn package manager

## Installation

1. Clone the repository:
```bash
git clone https://github.com/akaramanapp/weather-mcp-server.git
cd weather-mcp-server
```

2. Install dependencies:
```bash
npm install
```

3. Build the application:
```bash
npm run build
```

## MCP Tools

The server provides two MCP tools that can be used by AI agents:

### get-alerts

Get weather alerts for a specific US state.

Parameters:
- `state`: Two-letter state code (e.g., CA, NY)

Example response:
```json
{
  "content": [
    {
      "type": "text",
      "text": "Active alerts for CA: ..."
    }
  ]
}
```

### get-forecast

Get weather forecast for a specific location using coordinates.

Parameters:
- `latitude`: Latitude of the location (-90 to 90)
- `longitude`: Longitude of the location (-180 to 180)

Example response:
```json
{
  "content": [
    {
      "type": "text",
      "text": "Morning: Temperature: 72°F, Wind: 5mph NW, Partly cloudy..."
    }
  ]
}
```

## Project Structure

```
weather/
├── src/
│   └── index.ts    # Main server code with MCP tool implementations
├── build/          # Compiled JavaScript files
├── package.json    # Project dependencies and scripts
└── tsconfig.json   # TypeScript configuration
```

## Technical Details

- Built with TypeScript
- Implements Model Context Protocol (MCP) server
- Uses @modelcontextprotocol/sdk for MCP server implementation
- Interfaces with the National Weather Service (NWS) API
- ES2022 target with Node16 module resolution

## Development

To modify or extend the server:

1. Make changes in the `src/index.ts` file
2. Rebuild the application:
```bash
npm run build
```

## Dependencies

- @modelcontextprotocol/sdk: MCP server implementation framework
- zod: Runtime type checking and validation for tool parameters
- TypeScript: Development dependency for type safety

## License

ISC

## Notes

- This server only works for US locations as it uses the National Weather Service API
- API requests are rate-limited and require a User-Agent header
- All coordinates should be in decimal degrees format
- This is not a standalone CLI application, but rather a server that provides tools for AI agents through the Model Context Protocol 