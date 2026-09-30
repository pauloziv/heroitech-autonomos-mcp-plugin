# Autonomos by HeroiTech

Grok Bot plugin for the Autonomos remote Model Context Protocol (MCP) service.

This repository contains only the marketplace manifest, remote MCP connection, product/publisher logos, and connector documentation. It does not contain the Autonomos application or MCP server source code.

## Brand assets

- `assets/logo.png` is the Autonomos product icon, based on the approved RA mark.
- `assets/heroitech-publisher.png` is a square publisher logo using the official HeroiTech mark published at `https://heroitech.ia.br`.

## What it provides

- `get_task_context` reads the context for a task assigned to the authenticated customer account.
- `submit_task_result` submits structured findings for that task. Autonomos validates the task, tenant, operation, targets, and allowed state changes.
- `poll_manager_directive` retrieves an available internal manager directive for the authenticated account.
- `acknowledge_directive` records receipt of a directive. It does not claim that the directive was followed or completed.

The plugin has no general company-edit, tenant-selection, agent-dispatch, or prospect-messaging tool. The bearer determines the tenant and customer account; tool arguments cannot select another tenant. A Grok Bot account shares its connector with the Bots running under that account, and the MCP service does not attest the identity of an individual named Bot.

## Configure access

HeroiTech must issue a tenant/account-scoped, expiring MCP bearer. Set it in the plugin configuration as `AUTONOMOS_MCP_TOKEN`. The value is never stored in this repository. Do not paste it into chat, source files, or logs.

## Service availability

The configured URL is `https://autonomos.heroitech.ia.br/api/mcp`. An unauthenticated MCP POST to that public URL returned HTTP 404 on 2026-09-30. The plugin cannot connect until HeroiTech deploys the MCP route and makes the service available. This repository is the public connector package for review; it does not claim that a live Grok connection has been validated.

The MIT license applies to `.cursor-plugin/plugin.json`, `mcp.json`, and this documentation. Logo files and the HeroiTech/Autonomos marks are excluded and remain the property of HeroiTech.

## License

MIT. See [LICENSE](LICENSE).
