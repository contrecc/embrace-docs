---
title: Grafana Cloud Integration
description: Learn about the Embrace <> Grafana Cloud integration
sidebar_position: 4
---

# Grafana Cloud Integration

## Prerequisites

- Have an active Grafana Cloud account.

## Pulling your Grafana Cloud API Key or Access Policy / Token

Grafana Cloud migrated from [API Keys to Access Policies](https://grafana.com/docs/grafana-cloud/account-management/authentication-and-permissions/access-policies/#grafana-cloud-migration-from-api-keys-to-access-policies). 
It depends on your Grafana Cloud version the information that you need to share with us.

> Only Grafana administrators can create or delete API Keys and Access Policies. See [Grafana Cloud roles and permissions](https://grafana.com/docs/grafana-cloud/authentication-and-permissions/cloud-roles/) for more information.

### Access Policy/Token

<img src={require('@site/static/images/data-destinations/grafana_cloud_access_policies.png').default} alt="Image showing Grafana cloud access policy tab" />

1. Log into your [Grafana Cloud account](https://grafana.com/auth/sign-in) to access the **Cloud Portal**.
2. Select the organization that you want to add an Access Policy Token to, by selecting from the dropdown in top left.
3. Click **Access Policies** from the SECURITY section on the left.
4. Click **Create Access Policy**.
<img src={require('@site/static/images/data-destinations/grafana_cloud_access_policy.png').default} alt="Image showing Grafana cloud access policy tab" />
5. In **Display Name** and **Name**, enter a name for your Access Policy.
6. In **Realms**, choose the organization in which you want the metrics.
7. In **Scopes**, select `write` for Metrics, Logs and Traces. (this only gives permission to send metric, log and trace data to Grafana Cloud).
8. In **Add Scope**, choose `api-keys-metrics-publisher`.
9. Click **Create** when finished.
<img src={require('@site/static/images/data-destinations/grafana_cloud_token.png').default} alt="Image showing Grafana cloud token tab" />
10. Click **Add token** to generate it associated with the access policy.
11. In **Token Name**, enter a name for the token.
12. In **Expiration Date**, select `No expiry`.

### API Key

<img src={require('@site/static/images/data-destinations/grafana_cloud_api_keys.png').default} alt="Image showing Grafana cloud api key tab" />

1. Log into your [Grafana Cloud account](https://grafana.com/auth/sign-in) to access the **Cloud Portal**.
2. Select the organization that you want to add an API key to, by selecting from the dropdown in top left.
3. Click **API Keys** from the SECURITY section on the left.
4. Click **+Add API Key**.
5. In **API Key Name**, enter a name for your API key.
6. In **Role**, select  `MetricsPublisher` (is only given permission to send metric, log, and trace data to Grafana Cloud).
7. Click **Create API Key**.
8. A token is created and displayed. Copy the token and store it in a safe place, because it will not be displayed again.
9. Share the token with an Embrace onboarding specialist.
10. Click **Close** when finished.

## Pulling your Instance ID and Zone

1. Log into your [Grafana Cloud account](https://grafana.com/auth/sign-in) to access the **Cloud Portal**.
2. Select the organization you want the instance ID and zone, by selecting from the dropdown in the top left.
3. Click **Details** from the Grafana stack and copy the instance ID and zone.
4. Share the instance ID and zone with an Embrace onboarding specialist.

<img src={require('@site/static/images/grafana_cloud_details.png').default} alt="Image showing Grafana Cloud fields needed" />

## Selecting the Correct Data Source for Embrace Metrics

:::tip
If you are using the Embrace Metrics API, ensure that you configure Grafana to treat the Embrace Metrics API as a data source, rather than setting up your own Prometheus instance. You can reference this <a href="/docs/embrace-api/grafana_integrations#setting-up-embrace-as-a-data-source" target="_blank">guide</a>.
:::

Embrace provides two main options for viwing metrics within Grafana: using the **Embrace Metrics API** (pull method) or setting up a **Data Destination** (push method).

For Data Distination ensure that you are selecting the correct prometheus datasource. Ex: 

<img src={require('@site/static/images/data-destinations/grafana_cloud_prometheus_data_source.png').default} alt="Image showing Grafana Cloud datasource" />

<img src={require('@site/static/images/data-destinations/grafana_cloud_prometheus_data_source_selection.png').default} alt="Image showing the Prometheus data source selection" />

### Embrace Metrics API vs. Data Destination

- **Embrace Metrics API**: Alternatively, you can configure Grafana to pull metrics from Embrace using PromQL queries via the Embrace Metrics API. However, this method requires Grafana to be set up with the Embrace API as a data source and is typically only used if you have specific requirements for on-demand metrics retrieval.

- **Data Destination**: Embrace can push metrics directly to your Grafana Cloud instance as a data destination. This setup leverages Grafana Cloud's managed Prometheus services, enabling seamless integration without the need for an additional Prometheus instance. This method is ideal for most users who prefer a simple, automated approach to access Embrace metrics within Grafana Cloud.
