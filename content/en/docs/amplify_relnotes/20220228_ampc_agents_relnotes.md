---
title: Amplify agents February 2022 Release Notes
linkTitle: Amplify agents February 2022
weight: 90
date: 2022-02-25
---

Traceability and Discovery agents for Amplify Gateway / AWS / Azure / Istio provide better visibility into your multi-type gateway eco system. These agents collect data from the Gateway (API / traffic) and expose it in Amplify Central, providing you with a global vision of your eco system from a single interface.

## Versioning

Currently, version 1.1.12 is available. It is based on Amplify Agents SDK v1.1.15.
To display version information in the agents, use command `agentName --version`.

This version is compatible with:

* Axway API Management 7.6.2 SPx and 7.7 SPx
* AWS Gateway using SDK 2.0
* Azure latest release

## New features and enhancements

The following new features and enhancements are available in this update.

* Agent technical tags and attributes are now stored under `x-agent-details` sub-resources on the APIService / APIService revision and are no longer visible in Central WebUI.
* `TRACEABILITY_EXCEPTION_LIST` now supports regex expression based on [RE2 Syntax](https://github.com/google/re2/wiki/Syntax).

### Amplify Gateway agents enhancements

* None

### Amplify AWS Gateway agents enhancements

* None

### Amplify Azure agents enhancements

* None

### Amplify Istio agents enhancements

Latest helm chart version: 0.62.0

Latest agent version: 2.0.23

* None

### Amplify Apigee agents

Current release (0.0.4) of the Amplify Apigee agent is available on [Axway GitHub](https://github.com/Axway/agents-apigee) repository.

Known limitations:

* No traffic is reported as other agents to Amplify Analytics. A third-party library, such as Loggly, is required to do this.
* The API Usage will appear with the proxy name, not with the product name, in Amplify Analytics.

For more information, see the [Axway GitHub](https://github.com/Axway/agents-apigee) repository.

## Fixed issues

The following agent issues are fixed in this update:

* None

## Known limitations

The following limitations exist in this update.

### Amplify Gateway agents

* When an API is renamed in API Manager, Discovery Agent cannot recognize the API name change. This results in the API displaying in Amplify Central with dual entries of both the originally discovered name and the newly changed name.

### Amplify AWS Gateway agents

* Discovery Agent is working with only one AWS Region (the one used when installing the agent).
* Discovery Agent can discover APIs having ANY method only, but consumers will not be able to subscribe to it from Unified Catalog.
* Discovery Agent does not associate the usage plan and API when a subscriber chooses a usage plan that is not already linked to the chosen API.
* The Usage report is not scalable, as the agent relies on AWS Simple Queue Service and cannot have more than 10 consumers per queue. It is possible to increase the number of workers on the agent side.

### Amplify Azure agents

* Discovery Agent does not manage revision and version.
* Discovery Agent does not remove API Service and Catalog item when Azure API is removed.

### Amplify Istio agents

* Discovery Agent requires manual setup to report APIs correctly.
