# MCP Client Toolkit

TypeScript client library and utilities for remote Model Context Protocol (MCP) servers.

### Basic Client

```typescript
import { MCPClient, BrowserOAuthHandler } from 'mcp-client-toolkit';

const client = new MCPClient({
  callbackPort: 8090,
  oauthHandler: new BrowserOAuthHandler(8090)
});

await client.connect('http://localhost:3000/mcp');
```

### CLI Utilities

```typescript
import { 
  listTools, 
  showToolDetails, 
  callTool,
  parseToolCallCommand 
} from 'mcp-client-toolkit';

const mcpClient = client.getClient();
if (mcpClient) {
  await listTools(mcpClient);
  await showToolDetails(mcpClient, 'tool-name');
  await callTool(mcpClient, 'tool-name', { param: 'value' });
}
```

## Exports

- **MCPClient**: Main client class
- **BrowserOAuthHandler, CustomOAuthHandler**: OAuth handlers
- **ConnectionManager**: Connection management
- **listTools, showToolDetails, callTool**: CLI utilities
- **formatJsonSchema, generateExampleArgs**: Schema utilities
- **Types**: MCPClientConfig, OAuthHandler, TransportType, etc.

## Features

- OAuth 2.0 authentication support
- Automatic transport fallback (HTTP → SSE)
- Connection management
- Tool discovery and execution
- Real-time notifications
- Reusable CLI command utilities
