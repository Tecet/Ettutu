# LLM Providers

Ettutu V2 uses Large Language Models (LLMs) for intelligent data extraction and analysis. This guide
covers setup, configuration, and optimization of your LLM providers.

<!-- Screenshot: LLM Providers settings page showing provider list -->

---

## Overview

LLMs power several features in Ettutu V2:

| Feature             | LLM Role                                        |
| ------------------- | ----------------------------------------------- |
| **Lead Analysis**   | Extracts business insights, scores lead quality |
| **LLM Crawler**     | Intelligent website content extraction          |
| **Chat Assistant**  | Work and General mode conversations             |
| **Data Enrichment** | Enhances incomplete records                     |

---

## Provider Types

### 🟢 Priority 1: CLI Bridge (Free)

Use existing CLI tools like Gemini CLI or Claude CLI:

| Property    | Value                              |
| ----------- | ---------------------------------- |
| **Cost**    | Free (uses your CLI installations) |
| **Speed**   | 30-90 seconds per request          |
| **Quality** | High (uses full models)            |
| **Setup**   | Requires CLI tool installation     |

**Supported CLIs:**

- **Gemini CLI** - Google's Gemini model
- **Claude CLI** - Anthropic's Claude model

**How it works:**

1. Ettutu sends prompt via subprocess
1. CLI tool processes with STDIN input
1. Response returned without temp files
1. Local execution, no API costs

### 🔵 Priority 2: Ollama (Free)

Run LLMs locally on your machine:

| Property    | Value                             |
| ----------- | --------------------------------- |
| **Cost**    | Free (runs on your hardware)      |
| **Speed**   | 10-120 seconds depending on model |
| **Quality** | Good (varies by model)            |
| **Setup**   | Requires Ollama installation      |

**Supported Models:**

- `llama2` - Meta's Llama 2
- `mistral` - Mistral AI's model
- `codellama` - Code-focused Llama
- `mixtral` - Mixture of experts

**How it works:**

1. Ettutu connects to local Ollama HTTP API
1. Supports streaming responses
1. Model management through Ollama
1. No data leaves your machine

### 🟠 Priority 3: API Providers (Paid)

Cloud-based APIs with usage-based billing:

| Provider      | Models               | Cost          |
| ------------- | -------------------- | ------------- |
| **OpenAI**    | GPT-4, GPT-3.5-Turbo | Per token     |
| **Anthropic** | Claude 3, Claude 2   | Per token     |
| **Google AI** | Gemini Pro           | Per character |

**Features:**

- Token counting for cost tracking
- Fast response times (5-30 seconds)
- Reliable availability
- Rate limit handling

---

## Architecture

```text
┌─────────────────────────────────────────────────────────────────────────┐
│                           LLM ROUTER                                     │
├─────────────────────────────────────────────────────────────────────────┤
│  ✓ Role-based routing (manager, handler, analyst, crawler, chat)       │
│  ✓ Health checks (cached for 5 min)                                    │
│  ✓ Rate limiting (60 req/min per provider)                             │
│  ✓ Usage tracking (requests, tokens, cost, errors)                     │
│  ✓ Automatic fallback chain                                            │
└─────────────────────────────────────────────────────────────────────────┘
                                    │
                    ┌───────────────┼───────────────┐
                    ▼               ▼               ▼
        ┌──────────────┐  ┌──────────────┐  ┌──────────────┐
        │ CLI Bridge   │  │   Ollama     │  │ API Provider │
        │ (Free)       │  │   (Free)     │  │ (Paid)       │
        └──────────────┘  └──────────────┘  └──────────────┘
```

---

## Fallback Chain

When a provider fails, the system automatically tries the next:

```text
1. Try CLI Bridge
   │ (if fails or unavailable)
   ▼
2. Try Ollama
   │ (if fails or unavailable)
   ▼
3. Try API Provider
```

This ensures maximum availability at minimum cost.

---

## Role-Based Routing

Different tasks use different providers based on their role:

| Role        | Purpose                    | Recommended Provider             |
| ----------- | -------------------------- | -------------------------------- |
| **analyst** | Lead analysis and scoring  | High-quality (API or CLI Bridge) |
| **crawler** | Website content extraction | Fast (Ollama or CLI Bridge)      |
| **chat**    | User conversations         | Balanced (any available)         |
| **manager** | System coordination        | Reliable (API)                   |

Configure role assignments in **Settings → LLM Specialists**.

See [Chat System](../Tools/Chat%20System.md) for how providers affect AI chat.

---

## Setting Up CLI Bridge

### Step 1: Install Gemini CLI

```bash
# On Windows (PowerShell as Admin)
npm install -g @anthropic-ai/claude-code-cli
# Or install Gemini CLI from Google
```

### Step 2: Verify Installation

```bash
gemini --version
# or
claude --version
```

### Step 3: Configure in Ettutu

1. Go to **Settings → LLM Providers**
1. Click **Add Provider**
1. Select **CLI Bridge** type
1. Enter CLI path (or leave default)
1. Test connection
1. Save

### CLI Bridge Settings

| Setting      | Description            | Default       |
| ------------ | ---------------------- | ------------- |
| **CLI Path** | Path to CLI executable | Auto-detected |
| **Timeout**  | Max wait time          | 90 seconds    |
| **Model**    | Which CLI model        | gemini        |

---

## Setting Up Ollama

### Step 1: Install Ollama

Download from [ollama.ai](https://ollama.ai) and install.

### Step 2: Pull Models

```bash
ollama pull llama2
ollama pull mistral
```

### Step 3: Start Ollama

```bash
ollama serve
```

### Step 4: Configure in Ettutu

1. Go to **Settings → LLM Providers**
1. Click **Add Provider**
1. Select **Ollama** type
1. Enter URL (default: `http://localhost:11434`)
1. Select model from dropdown
1. Test connection
1. Save

### Ollama Settings

| Setting     | Description           | Default                  |
| ----------- | --------------------- | ------------------------ |
| **URL**     | Ollama server address | `http://localhost:11434` |
| **Model**   | Which model to use    | llama2                   |
| **Timeout** | Max response time     | 120 seconds              |

---

## Setting Up API Providers

### OpenAI

1. Get API key from [platform.openai.com](https://platform.openai.com)
1. Add provider in Settings
1. Enter API key
1. Select model (GPT-4 recommended)

### Anthropic

1. Get API key from [console.anthropic.com](https://console.anthropic.com)
1. Add provider in Settings
1. Enter API key
1. Select model (Claude 3 Opus recommended)

### Google AI

1. Get API key from [makersuite.google.com](https://makersuite.google.com)
1. Add provider in Settings
1. Enter API key
1. Select model (Gemini Pro recommended)

---

## LLM Specialists

Assign providers to specific roles:

<!-- Screenshot: LLM Specialists configuration page -->

### Configuration

1. Go to **Settings → LLM Specialists**
1. For each role, select preferred provider
1. Optionally set fallback provider
1. Save changes

### Example Configuration

| Role    | Primary             | Fallback     |
| ------- | ------------------- | ------------ |
| Analyst | CLI Bridge (Gemini) | OpenAI GPT-4 |
| Crawler | Ollama (Mistral)    | CLI Bridge   |
| Chat    | CLI Bridge (Claude) | Anthropic    |

---

## Usage Tracking

Monitor your LLM usage:

| Metric             | Description          |
| ------------------ | -------------------- |
| **Total Requests** | Number of API calls  |
| **Total Tokens**   | Tokens processed     |
| **Total Cost**     | Estimated USD cost   |
| **Error Count**    | Failed requests      |
| **Last Request**   | Most recent activity |

### Viewing Usage

1. Go to **Settings → LLM Providers**
1. Click provider to expand
1. View usage statistics
1. Click **Reset** to clear stats

---

## Cost Optimization

### Tips for Reducing Costs

1. **Use CLI Bridge first** - Free tier uses no credits
1. **Deploy Ollama locally** - No ongoing costs
1. **Reserve API for high-value tasks** - Analyst role only
1. **Monitor usage regularly** - Catch runaway costs

### Estimated Costs (API Providers)

| Task          | Tokens | Approx Cost    |
| ------------- | ------ | -------------- |
| Lead Analysis | ~2000  | $0.06 (GPT-4)  |
| Website Crawl | ~1000  | $0.03 (GPT-4)  |
| Chat Message  | ~500   | $0.015 (GPT-4) |

---

## Testing Providers

### Test Connection

1. Find provider in list
1. Click **Test** button
1. System sends test prompt
1. Shows success/failure message

### Health Checks

- Run automatically every 5 minutes
- Cached to reduce API calls
- Failed providers temporarily skipped

---

## Troubleshooting

### CLI Bridge Issues

| Problem         | Solution                        |
| --------------- | ------------------------------- |
| "CLI not found" | Check PATH environment variable |
| Timeout errors  | Increase timeout in settings    |
| Empty responses | Update CLI to latest version    |

### Ollama Issues

| Problem            | Solution                              |
| ------------------ | ------------------------------------- |
| Connection refused | Start Ollama with `ollama serve`      |
| Model not found    | Pull model: `ollama pull llama2`      |
| Slow responses     | Try smaller model or upgrade hardware |

### API Issues

| Problem          | Solution                        |
| ---------------- | ------------------------------- |
| 401 Unauthorized | Check API key is correct        |
| 429 Rate Limited | Wait and retry, or upgrade plan |
| 500 Server Error | Provider outage, use fallback   |

---

## Database Schema

Providers are stored in `llm_providers` table:

| Field           | Type    | Description                                   |
| --------------- | ------- | --------------------------------------------- |
| `id`            | Integer | Primary key                                   |
| `name`          | String  | Display name                                  |
| `provider_type` | Enum    | cli_bridge, ollama, openai, anthropic, google |
| `model`         | String  | Model identifier                              |
| `role`          | String  | analyst, crawler, chat, manager               |
| `is_active`     | Boolean | Enabled/disabled                              |
| `api_key`       | String  | Encrypted API key (API providers)             |
| `base_url`      | String  | Custom endpoint URL                           |

---

## API Endpoints

| Endpoint                          | Method | Description            |
| --------------------------------- | ------ | ---------------------- |
| `/api/v2/llm/providers`           | GET    | List all providers     |
| `/api/v2/llm/providers/{id}/test` | GET    | Test specific provider |
| `/api/v2/llm/chat`                | POST   | Chat with LLM          |
| `/api/v2/llm/usage`               | GET    | Get usage statistics   |
| `/api/v2/llm/usage/reset`         | POST   | Reset usage stats      |

See API docs at `/docs` for full reference.
