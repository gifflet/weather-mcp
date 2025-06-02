# Weather MCP 🌤️

A modern weather service built with MCP (Multi-Cloud Platform) that provides real-time weather data and alerts.

## 🌟 Features

- 🌡️ Real-time weather forecasts
- ⚠️ Weather alerts by state
- 📍 Location-based weather information
- 🔄 Easy-to-use API endpoints

## 🚀 Getting Started

### Prerequisites

- Node.js (v18 or higher)
- MCP Server
- Git

### Installation

1. Clone the repository:
```bash
git clone https://github.com/gifflet/weather-mcp.git
cd weather-mcp
```

2. Install dependencies and build the project:
```bash
npm install && npm run build
```

## 💻 Local Development with MCP Server

### Configuring MCP Server

1. Create a `.cursor/mcp.json` file in your project directory with the following content:

```json
{
  "mcpServers": {
    "weather-service": {
      "command": "node",
      "args": ["/ABSOLUTE/PATH/TO/PARENT/FOLDER/weather/build/index.js"],
    }
  }
}
```

Where `/ABSOLUTE/PATH/TO/PARENT/FOLDER/weather/build/index.js` is the path to the `index.js` file in the `build` folder of the weather-mcp project.

Alternatively, for global configuration, you can create the file at the root of your home directory: `.cursor/mcp.json`.

### Starting the MCP Server

1. Open the project in Cursor IDE
2. Go to `Cursor Settings > Features > MCP`
3. Your weather service should appear in the list of available MCP servers
4. If needed, click the refresh button in the top right corner to populate the tool list

### Using the Weather Service

After configuring and starting the MCP server in Cursor, you can interact with the weather service using natural language queries. Here are some examples:

#### Example Queries
- "What's the weather in Sacramento?"
- "Are there any active weather alerts in Texas?"
- "What's the forecast for San Francisco?"
- "Show me weather alerts for CA"

Note: Since this service uses the US National Weather Service API, queries will only work for locations within the United States.

#### Under the Hood
When you make a query:
1. Your question is sent to the LLM
2. The LLM analyzes the available tools and decides which one(s) to use
3. The client executes the chosen tool(s) through the MCP server
4. The results are sent back to the LLM
5. A natural language response is formulated and displayed to you

#### Troubleshooting Common Issues

If the tools are not working as expected:
- Verify your server builds and runs without errors
- Check that the path in your `.cursor/mcp.json` is correct and absolute
- Restart Cursor IDE if needed
- For coordinates outside the US, you'll receive an error as the service only supports US locations
- During high traffic, the weather service API might have rate limits

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.