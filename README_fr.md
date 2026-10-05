# Open WebUI Slim pour YunoHost

[![Niveau d'intégration](https://dash.yunohost.org/integration/open-webui-slim.svg)](https://ci-apps.yunohost.org/ci/apps/open-webui-slim/)
![Statut de fonctionnement](https://ci-apps.yunohost.org/ci/badges/open-webui-slim.status.svg)
![Statut de maintenance](https://ci-apps.yunohost.org/ci/badges/open-webui-slim.maintain.svg)

> *Ce package vous permet d'installer Open WebUI Slim rapidement et simplement sur un serveur YunoHost.*
> *Si vous n'avez pas YunoHost, consultez [le guide](https://yunohost.org/install) pour apprendre à l'installer.*

## Vue d'ensemble

Open WebUI Slim est le même Open WebUI, mais configuré sans modèles IA locaux. Il requiert un LLM externe : Ollama (auto-hébergé) ou toute API compatible OpenAI. Aucun modèle d'embedding d'~1Go n'est téléchargé au premier démarrage, et la recherche web / génération d'images sont désactivées par défaut.

Même wheel que la version complète — l'économie "slim" vient du fait de ne jamais télécharger les modèles locaux d'embedding/Whisper. L'environnement Python demande quand même ~6Go de disque et 2Go de RAM.

**Version livrée :** 0.11.3~ynh1

## Captures d'écran

Pas encore de captures. Captures upstream : https://openwebui.com/

## Avertissements / informations importantes

- Nécessite un LLM externe pour être utile : installez Ollama depuis le catalogue YunoHost, ou utilisez toute API compatible OpenAI (clé à configurer dans le panneau admin Open WebUI > Connexions).
- Pas de modèle d'embedding local : `RAG_EMBEDDING_ENGINE` doit être `ollama` ou `openai`.
- L'entrée vocale utilise Whisper `tiny` (modèle le plus petit). Changez-le dans `.env` si besoin.
- LDAP activé avec l'annuaire YunoHost. Le premier utilisateur à se connecter devient admin.
- `multi_instance = false` : une seule installation par serveur.

## Documentations et ressources

- Site officiel de l'app : https://openwebui.com/
- Documentation officielle utilisateur : https://docs.openwebui.com/category/-tutorials
- Documentation officielle d'administration : https://docs.openwebui.com/getting-started/
- Dépôt de code officiel de l'app : https://github.com/open-webui/open-webui
- Documentation YunoHost pour cette app : https://yunohost.org/app_open-webui-slim
- Signaler un bug : https://github.com/espilber/open-webui-slim_ynh/issues

## Informations pour les développeurs

Merci de faire vos pull request sur la [branche testing](https://github.com/espilber/open-webui-slim_ynh/tree/testing).

Pour tester la branche testing :

```bash
sudo yunohost app install https://github.com/espilber/open-webui-slim_ynh/tree/testing --debug
# ou
sudo yunohost app upgrade open-webui-slim -u https://github.com/espilber/open-webui-slim_ynh/tree/testing --debug
```

**Plus d'infos sur le packaging d'apps :** https://doc.yunohost.org/packaging_apps
