# Open WebUI Slim for YunoHost

[![Integration level](https://dash.yunohost.org/integration/open-webui-slim.svg)](https://ci-apps.yunohost.org/ci/apps/open-webui-slim/)
![Working status](https://ci-apps.yunohost.org/ci/badges/open-webui-slim.status.svg)
![Maintenance status](https://ci-apps.yunohost.org/ci/badges/open-webui-slim.maintain.svg)

> *This package allows you to install Open WebUI Slim quickly and simply on a YunoHost server.*
> *If you don't have YunoHost, please consult [the guide](https://yunohost.org/install) to learn how to install it.*

## Overview

Open WebUI Slim is the same Open WebUI, but configured without local AI models. It requires an external LLM: Ollama (self-hosted) or any OpenAI-compatible API. No ~1GB embedding model is downloaded on first start, and web search / image generation are off by default.

Same wheel as the full version — the "slim" saving comes from never downloading local embedding/Whisper models. The Python environment still needs ~6GB disk and 2GB RAM.

**Shipped version:** 0.11.3~ynh1

## Screenshots

No screenshots yet. Upstream screenshots: https://openwebui.com/

## Disclaimers / important information

- Requires an external LLM to be useful: install Ollama from the YunoHost catalog, or use any OpenAI-compatible API (key configured in Open WebUI admin panel > Connections).
- No local embedding model: `RAG_EMBEDDING_ENGINE` must be `ollama` or `openai`.
- Voice input uses Whisper `tiny` (smallest model). Set another model in `.env` if needed.
- LDAP is enabled against YunoHost directory. First user to log in becomes admin.
- `multi_instance = false`: only one install per server.

## Documentation and resources

- Official app website: https://openwebui.com/
- Official user documentation: https://docs.openwebui.com/category/-tutorials
- Official admin documentation: https://docs.openwebui.com/getting-started/
- Upstream app code repository: https://github.com/open-webui/open-webui
- YunoHost documentation for this app: https://yunohost.org/app_open-webui-slim
- Report a bug: https://github.com/espilber/open-webui-slim_ynh/issues

## Developer info

Please send your pull request to the [testing branch](https://github.com/espilber/open-webui-slim_ynh/tree/testing).

To try the testing branch, please proceed like that:

```bash
sudo yunohost app install https://github.com/espilber/open-webui-slim_ynh/tree/testing --debug
# or
sudo yunohost app upgrade open-webui-slim -u https://github.com/espilber/open-webui-slim_ynh/tree/testing --debug
```

**More info regarding app packaging:** https://doc.yunohost.org/packaging_apps
