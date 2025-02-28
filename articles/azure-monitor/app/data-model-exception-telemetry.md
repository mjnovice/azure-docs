---
title: Azure Application Insights Exception Telemetry Data model
description: Application Insights data model for exception telemetry
ms.topic: conceptual
ms.date: 04/25/2017
ms.reviewer: sergkanz
---

# Exception telemetry: Application Insights data model

In [Application Insights](./app-insights-overview.md), an instance of Exception represents a handled or unhandled exception that occurred during execution of the monitored application.

## Problem Id

Identifier of where the exception was thrown in code. Used for exceptions grouping. Typically a combination of exception type and a function from the call stack.

Max length: 1024 characters

## Severity level

Trace severity level. Value can be `Verbose`, `Information`, `Warning`, `Error`, `Critical`.

## Exception details

(To be extended)

## Custom properties

[!INCLUDE [application-insights-data-model-properties](../../../includes/application-insights-data-model-properties.md)]

## Custom measurements

[!INCLUDE [application-insights-data-model-measurements](../../../includes/application-insights-data-model-measurements.md)]

## Next steps

- See [data model](data-model.md) for Application Insights types and data model.
- Learn how to [diagnose exceptions in your web apps with Application Insights](./asp-net-exceptions.md).
- Check out [platforms](./platforms.md) supported by Application Insights.

