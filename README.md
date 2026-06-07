# Package/Dependency Ownership & Outreach Automation

**Overview**

The objective of this automation identify internal repositories that resolve vulnerable npm package versions and maps them to the correct owners for remediation outreach. It performs structured code discovery across multiple lockfile formats, validates affected versions against advisory boundaries, expands repository ownership using GitHub and enterprise identity sources, and generates a SOC-ready report that separates confirmed exposure from candidate findings.

The goal is to reduce manual investigation time, improve consistency in vulnerability outreach, and ensure the right teams are engaged quickly with auditable supporting evidence.

**Requirements**

Required tools: Cursor

Required Integrations: SourceGraph MCP, Glean MCP, Email MCP

**System Structure and Flow**

This agent automation takes a package or dependency name and the affected versions as input, then uses the Sourcegraph MCP server to search the codebase for repositories that reference or resolve those versions. For the repositories it finds, it checks the CODEOWNERS file to identify the relevant owners. It then uses the Glean MCP server to resolve those owners to people and their associated teams, helping Security quickly map vulnerable dependencies to the right contacts for outreach and remediation.

<img width="2816" height="1536" alt="image" src="https://github.com/user-attachments/assets/5c3643aa-3809-44f4-9fb0-abf5af649759" />
