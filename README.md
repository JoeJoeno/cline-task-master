## AI Model Provider Configuration

You can use Anthropic (Claude), OpenAI, or Perplexity as your AI model provider.  
Set the `MODEL` environment variable in your `.env` file to select which provider to use:

- `MODEL=anthropic` (default, uses Claude via Anthropic)
- `MODEL=openai` (uses OpenAI GPT models)
- `MODEL=perplexity` (uses Perplexity via OpenAI-compatible API)

### Required API Keys

Depending on your selected provider, set the corresponding API key in your `.env` file:

- For Anthropic: `ANTHROPIC_API_KEY=your_anthropic_api_key_here`
- For OpenAI: `OPENAI_API_KEY=your_openai_api_key_here`
- For Perplexity: `PERPLEXITY_API_KEY=your_perplexity_api_key_here`

Example `.env` configuration:
```
MODEL=anthropic
ANTHROPIC_API_KEY=sk-ant-...
OPENAI_API_KEY=sk-...
PERPLEXITY_API_KEY=pplx-...
```

If you switch providers, be sure to set the correct API key for the provider you select.

See `.env.example` for a full list of configuration options.
