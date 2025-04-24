## AI Model Provider Configuration

You can use Anthropic (Claude), OpenAI, or Perplexity as your AI model provider.  
Set the `MODEL` environment variable in your `.env` file or in your MCP server configuration JSON to select which provider to use.

### Example MCP Server Configuration (`mcp.json`)

To configure the MCP server to use a specific provider, set the environment variables in the `env` block of your `mcp.json` file as shown below:

#### Anthropic (Claude) Example
```json
{
  "env": {
    "MODEL": "anthropic",
    "ANTHROPIC_API_KEY": "sk-ant-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  }
}
```

#### OpenAI Example
```json
{
  "env": {
    "MODEL": "openai",
    "OPENAI_API_KEY": "sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx"
  }
}
```

#### Perplexity Example
```json
{
  "env": {
    "MODEL": "perplexity",
    "PERPLEXITY_API_KEY": "pplx-xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx",
    "PERPLEXITY_MODEL": "sonar-pro"
  }
}
```

**Key Points:**
- Set the `"MODEL"` key to `"anthropic"`, `"openai"`, or `"perplexity"` to select the provider.
- Provide the corresponding API key for the provider you select.
- For Perplexity, you should also set `"PERPLEXITY_MODEL"` to the desired model (e.g., `"sonar-pro"`).

If you are running the MCP server in an environment where it reads from a `.env` file, you can set these variables in `.env` instead. The MCP server will use the values from either the environment or the `env` block in your configuration JSON.

See `.env.example` for a full list of configuration options.
