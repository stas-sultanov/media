# Azure Observability Without Reinventing the Wheel

## 1. Intro

In almost every real-world IT solution, teams eventually face the need to add observability to *already existing* systems or applications.

A common reaction is to build a custom solution: poll telemetry via APIs, store it, evaluate thresholds, and send notifications. While this approach can work, it is rarely efficient. It reinvents components that Azure already provides as managed, scalable building blocks.

The goal of this article is to show how to use Azure-native components to implement observability for existing systems with minimal effort, lower operational overhead, and better long-term reliability.

## 2. How observability should look like

Regardless of technology stack or hosting model implementation of extra observability for already existing system or software is pretty much standard and operates through the following components:

1. **Source** – the application or system to be observed.
2. **Collector** – a mechanism that queries the source, extracts metrics, logs, or state, and transfers it to storage.
3. **Storage** – a durable, queryable repository for collected telemetry.
4. **Alert – a mechanism that evaluates telemetry over time to detect issues using queries.**
5. **Notification** – a mechanism that delivers alerts to relevant stakeholders or downstream systems.

The observability flow is straightforward: the collector periodically collect telemetry from the source and sent to storage, the alert queries storage on a defined schedule; when results match alert conditions, alerts are triggered and notifications are sent to all configured destinations.

The key insight is that only the *collection* step typically requires custom logic. Storage, querying, alerting, and notifications can — and should — rely on platform-native capabilities, reducing maintenance overhead and standardizing observability across systems.

## 3. Implementation on Azure

In Azure, observability can be implemented using a set of native services that map directly to the pipeline components described earlier. These services minimize custom code and leverage platform-native capabilities for collection, storage, alerting, and notifications.

Log Analytics Workspace – a centralized and durable storage for all collected telemetry. It supports large-scale, time-series data and enables powerful queries.

Data Collection Rules (DCRs) – the required mechanism in Azure for ingesting telemetry. DCRs define how incoming data is transformed and routed into Log Analytics Workspace. They provide a unified, reliable ingestion path.

Azure Functions or other compute platforms – host custom code that extracts telemetry from the source systems. Functions are ideal for lightweight, scheduled polling or event-driven data collection.

Alerting – Azure Monitor Alerts evaluate telemetry in Log Analytics Workspace using Kusto Query Language (KQL). Alerts are configured with thresholds and evaluation frequency to detect issues automatically.

Notifier (Action Groups) – responsible for delivering alerts to different channels such as email, Teams, webhooks, or ITSM systems. This decouples alert evaluation from notification delivery, making it easier to manage and extend.

Observability Flow in Azure

Custom telemetry collection code runs periodically on Azure Functions (or another compute platform).

The code pulls data from the source system and pushes it to the Data Collection Rule endpoint.

The Data Collection Rule processes and routes the data into the Log Analytics Workspace.

Alerting queries the workspace at the configured intervals. If conditions are met, an alert is fired to the configured Action Group.

The Notifier (Action Group) delivers the notification to all configured channels.

This approach keeps custom implementation focused on data extraction, while Azure handles ingestion, storage, alerting, and notification delivery. It simplifies maintenance, ensures consistency, and scales easily with the system.

