# Task Master [![GitHub stars](https://img.shields.io/github/stars/eyaltoledano/claude-task-master?style=social)](https://github.com/eyaltoledano/claude-task-master/stargazers)

[![CI](https://github.com/eyaltoledano/claude-task-master/actions/workflows/ci.yml/badge.svg)](https://github.com/eyaltoledano/claude-task-master/actions/workflows/ci.yml) [![npm version](https://badge.fury.io/js/task-master-ai.svg)](https://badge.fury.io/js/task-master-ai) [![Discord Follow](https://dcbadge.limes.pink/api/server/https://discord.gg/2ms58QJjqp?style=flat)](https://discord.gg/2ms58QJjqp) [![License: MIT with Commons Clause](https://img.shields.io/badge/license-MIT%20with%20Commons%20Clause-blue.svg)](LICENSE)

### By [@eyaltoledano](https://x.com/eyaltoledano) & [@RalphEcom](https://x.com/RalphEcom)

[![Twitter Follow](https://img.shields.io/twitter/follow/eyaltoledano?style=flat)](https://x.com/eyaltoledano)
[![Twitter Follow](https://img.shields.io/twitter/follow/RalphEcom?style=flat)](https://x.com/RalphEcom)

A task management system for AI-driven development, now supporting Anthropic (Claude), OpenAI, and Perplexity as AI providers. Designed to work seamlessly with Cursor AI and the Model Control Protocol (MCP).

---

## Requirements

- API key for your chosen provider (Anthropic, OpenAI, or Perplexity)
- Node.js (v18+ recommended)
- (Optional) OpenAI SDK (for Perplexity or OpenAI integration)

---

## Quick Start

### Option 1 | MCP (Recommended):

MCP (Model Control Protocol) provides the easiest way to get started with Task Master directly in your editor.

#### 1. Add the MCP config to your editor (Cursor recommended, but works with others):

```json
{
  "mcpServers": {
    "taskmaster-ai": {
      "command": "npx",
      "args": ["-y", "--package=task-master-ai", "task-master-ai"],
      "env": {
        "MODEL": "anthropic", // or "openai" or "perplexity"
        "ANTHROPIC_API_KEY": "YOUR_ANTHROPIC_API_KEY_HERE",
        "OPENAI_API_KEY": "YOUR_OPENAI_API_KEY_HERE",
        "PERPLEXITY_API_KEY": "YOUR_PERPLEXITY_API_KEY_HERE",
        "PERPLEXITY_MODEL": "sonar-pro", // required for Perplexity
        "MAX_TOKENS": "64000",
        "TEMPERATURE": "0.2",
        "DEFAULT_SUBTASKS": "5",
        "DEFAULT_PRIORITY": "medium"
      }
    }
  }
}
```

- Set `"MODEL"` to `"anthropic"`, `"openai"`, or `"perplexity"` depending on your provider.
- Provide the corresponding API key(s) for your provider.
- For Perplexity, set `"PERPLEXITY_MODEL"` (e.g., `"sonar-pro"`).

#### 2. Enable the MCP in your editor

#### 3. Prompt the AI to initialize Task Master:

```
Can you please initialize taskmaster-ai into my project?
```

#### 4. Use common commands directly through your AI assistant:

```txt
Can you parse my PRD at scripts/prd.txt?
What's the next task I should work on?
Can you help me implement task 3?
Can you help me expand task 4?
```

---

### Option 2: Using Command Line

#### Installation

```bash
# Install globally
npm install -g task-master-ai

# OR install locally within your project
npm install task-master-ai
```

#### Initialize a new project

```bash
# If installed globally
task-master init

# If installed locally
npx task-master-init
```

This will prompt you for project details and set up a new project with the necessary files and structure.

#### Common Commands

```bash
# Initialize a new project
task-master init

# Parse a PRD and generate tasks
task-master parse-prd your-prd.txt

# List all tasks
task-master list

# Show the next task to work on
task-master next

# Generate task files
task-master generate
```

---

## AI Provider Configuration

Task Master now supports Anthropic (Claude), OpenAI, and Perplexity as AI providers.  
You can configure your provider using either a `.env` file or the `env` block in your MCP server configuration (`mcp.json`).

### Example MCP Server Configuration (`mcp.json`)

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

---

## Documentation

For more detailed information, check out the documentation in the `docs` directory:

- [Configuration Guide](docs/configuration.md) - Set up environment variables and customize Task Master
- [Tutorial](docs/tutorial.md) - Step-by-step guide to getting started with Task Master
- [Command Reference](docs/command-reference.md) - Complete list of all available commands
- [Task Structure](docs/task-structure.md) - Understanding the task format and features
- [Example Interactions](docs/examples.md) - Common Cursor AI interaction examples

---

## Troubleshooting

### If `task-master init` doesn't respond:

Try running it with Node directly:

```bash
node node_modules/claude-task-master/scripts/init.js
```

Or clone the repository and run:

```bash
git clone https://github.com/eyaltoledano/claude-task-master.git
cd claude-task-master
node scripts/init.js
```

---

## Contributors

<a href="https://github.com/eyaltoledano/claude-task-master/graphs/contributors">
  <img src="https://contrib.rocks/image?repo=eyaltoledano/claude-task-master" alt="Task Master project contributors" />
</a>

---

## Star History

[![Star History Chart](https://api.star-history.com/svg?repos=eyaltoledano/claude-task-master&type=Timeline)](https://www.star-history.com/#eyaltoledano/claude-task-master&Timeline)

---

## Licensing

Task Master is licensed under the MIT License with Commons Clause. This means you can:

✅ **Allowed**:

- Use Task Master for any purpose (personal, commercial, academic)
- Modify the code
- Distribute copies
- Create and sell products built using Task Master

❌ **Not Allowed**:

- Sell Task Master itself
- Offer Task Master as a hosted service
- Create competing products based on Task Master

See the [LICENSE](LICENSE) file for the complete license text and [licensing details](docs/licensing.md) for more information.
