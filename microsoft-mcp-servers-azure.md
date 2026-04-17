# Microsoft's MCP Servers for Azure: What They Are and How to Use Them

Microsoft has been building out a solid set of **Model Context Protocol (MCP)** servers that let AI agents work directly with Azure resources. If you're experimenting with AI-driven automation or building agentic workflows on Azure, these tools are worth understanding.

---

## What is MCP?

The **Model Context Protocol (MCP)** is an open standard that allows AI agents — such as GitHub Copilot, Claude, or custom LLM-based tools — to interact with external services through a consistent interface. Instead of building one-off integrations for each service, MCP gives agents a standardized way to call tools and retrieve context from the systems around them.

Microsoft has leaned into this standard across a range of Azure services and developer tools.

---

## Microsoft's MCP Servers for Azure

### 1. Azure MCP Server

This is the main server for Azure resource management via agents. It covers a broad range of Azure services — including AKS, Container Apps, Cosmos DB, and Azure AI — and supports enterprise deployment scenarios.

Key capabilities:
- Remote HTTP deployment for self-hosted setups
- **Entra ID authentication** with On-Behalf-Of (OBO) support — no shared credentials needed
- **Azure RBAC integration** for access control
- Sovereign cloud support, including **Azure US Government**

It's open source and actively maintained: [github.com/Azure/azure-mcp](https://github.com/Azure/azure-mcp)

**Example:** An agent can provision a Cosmos DB instance, configure a Container App, and connect an AI service based on a natural language request.

---

### 2. Azure DevOps MCP Server

This server exposes Azure DevOps capabilities to AI agents — work items, pull requests, builds, test plans, and wikis are all accessible.

It integrates with GitHub Copilot and similar assistants, so agents can trigger builds, create work items, or query pipeline status without custom scripting.

Open source: [github.com/microsoft/azure-devops-mcp](https://github.com/microsoft/azure-devops-mcp)

**Example:** An agent spots a failed deployment, files a work item, and kicks off a rollback pipeline automatically.

---

### 3. Microsoft Fabric MCP Server

Aimed at data-heavy workflows, this server connects agents to Microsoft Fabric — Microsoft's unified data and analytics platform.

It has two modes:
- A **local API context provider** for code generation assistance
- A **real-time intelligence server** that translates natural language into KQL queries

**Example:** An agent converts a business question into a KQL query, runs it against Fabric, and returns formatted results.

---

### 4. Azure AI Foundry MCP Server

This server connects agents to Azure AI Foundry, Microsoft's platform for deploying and managing AI models. Agents can query model deployments, manage AI projects, and retrieve evaluation metrics.

---

### 5. Azure Functions MCP Support

Azure Functions supports hosting MCP servers directly, which means you can run custom MCP logic serverlessly without a dedicated server. It supports .NET, Java, JavaScript, Python, and TypeScript, and existing MCP SDK-based servers can be deployed without code changes.

---

### 6. Other Microsoft MCP Servers

| Server | What it does |
|---|---|
| **SQL MCP Server** | Natural language queries against Azure SQL |
| **Microsoft 365 Agents Toolkit MCP** | M365 app development through agents |
| **Dev Box MCP** | Manage cloud developer workstations |
| **Microsoft Learn MCP** | Pulls documentation for AI assistants |
| **NuGet MCP Server** | Package discovery and management |
| **Clarity MCP** | Web analytics data via agents |

---

## IDE Integration

Azure MCP Server is available as part of Visual Studio's Azure and AI development workload, which means developers can manage Azure resources through natural language conversations with GitHub Copilot directly from the IDE — querying subscriptions, checking resource states, or provisioning infrastructure.

---

## Why This Matters

Most cloud automation still relies on Terraform templates, ARM scripts, or manual portal work. MCP servers shift this by giving agents direct, standardized access to cloud services — with proper authentication and access controls in place.

A few things that stand out:
- **No custom integrations** — one protocol across services
- **Enterprise security** — RBAC and Entra ID support built in
- **Composable** — you can chain multiple MCP servers for multi-step workflows
- **Works in your IDE** — VS Code and Visual Studio both support it

---

## Getting Started

1. Install the Azure MCP Server: [Microsoft Learn Overview](https://learn.microsoft.com/en-us/azure/developer/azure-mcp-server/overview)
2. Integrate with GitHub Copilot: [Quickstart Guide](https://learn.microsoft.com/en-us/azure/developer/azure-mcp-server/how-to/github-copilot-cli)
3. Browse the full MCP server catalog: [github.com/microsoft/mcp](https://github.com/microsoft/mcp)

---

## Sources

- [What is the Azure MCP Server? — Microsoft Learn](https://learn.microsoft.com/en-us/azure/developer/azure-mcp-server/overview)
- [Announcing Azure MCP Server 2.0 Stable Release — Azure SDK Blog](https://devblogs.microsoft.com/azure-sdk/announcing-azure-mcp-server-2-0-stable-release/)
- [Introducing the Azure MCP Server — Azure SDK Blog](https://devblogs.microsoft.com/azure-sdk/introducing-the-azure-mcp-server/)
- [Azure MCP Server Built-In with Visual Studio — Visual Studio Blog](https://devblogs.microsoft.com/visualstudio/azure-mcp-server-now-built-in-with-visual-studio-2026-a-new-era-for-agentic-workflows/)
- [Azure DevOps MCP Server — GitHub](https://github.com/microsoft/azure-devops-mcp)
- [Azure DevOps MCP Server GA — InfoQ](https://www.infoq.com/news/2025/11/microsoft-ado-mcp-server/)
- [Azure Functions MCP Support — InfoQ](https://www.infoq.com/news/2026/01/azure-functions-mcp-support/)
- [Azure/azure-mcp — GitHub](https://github.com/Azure/azure-mcp)
