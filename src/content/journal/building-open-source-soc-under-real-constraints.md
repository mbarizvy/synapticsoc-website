---
title: "Building an Open-Source SOC Under Real Constraints"
description: "The first Build Journal entry for SynapticSOC, explaining the purpose of the project, the constraints behind it, and why the architecture is being documented openly."
date: 2026-06-07
category: "Project foundation"
stage: "Build Journal"
summary: "SynapticSOC is a practical open-source SOC project built around real hardware, limited resources, and documented engineering decisions rather than ideal lab conditions."
tags:
  - Open-source SOC
  - Wazuh
  - Graylog
  - Zeek
  - n8n
draft: false
---

SynapticSOC began as a practical attempt to build a capable open-source Security Operations Center using realistic hardware, limited resources, and tools that can be studied, deployed, and improved without relying on expensive commercial platforms.

This project is not presented as a perfect enterprise SOC or a polished vendor reference architecture. It is a working engineering build shaped by constraints: storage limits, hardware limits, integration problems, routing decisions, noisy telemetry, dashboard design, and the need to preserve evidence without blindly automating response.

The core idea is simple: useful security operations require more than one dashboard. Firewall telemetry, IDS alerts, endpoint events, passive LAN visibility, search, triage, analyst acknowledgment, and evidence handling all need to connect into a coherent workflow.

The current SynapticSOC architecture uses pfSense, Snort, Suricata, Wazuh, Zeek, Graylog, OpenSearch, Grafana, and n8n to demonstrate how open-source components can be combined into an operational SOC workflow. Each tool has a defined role. Graylog acts as the operational aggregation hub. OpenSearch supports search and storage. n8n supports SOAR-assisted triage. The analyst remains responsible for the final decision.

A major goal of this journal is to document not only what worked, but also what broke and why certain decisions were made. That includes design tradeoffs, mistakes, rebuilds, routing choices, retention planning, evidence handling, and the gradual movement from visibility toward response.

The project is intentionally public at a high level, but it does not expose sensitive implementation details. Internal IP addresses, credentials, workflow logic, firewall rules, tokens, queries, and other operational details are excluded from the public documentation.

The Build Journal will track the project as it develops from a working home-lab SOC into a more complete open-source SOC reference project with stronger retention, RBAC, response procedures, case handling, and compliance-oriented documentation.
