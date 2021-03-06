---
title: Istio 0.6
weight: 95
page_icon: /img/notes.svg
---

在平淡无奇的问题修复和性能增强之外，这一版本包含了部分全新的功能，以及对现有功能的改进，具体包括以下内容。

## 网络

- **Custom Envoy Configuration**：现在 Pilot 能够将自定义 Envoy 配置分发给 proxy。[参考资料](https://github.com/mandarjog/istioluawebhook)

## Mixer 适配器

- **SolarWinds**。 Mixer 和 AppOptics 以及 Papertrail 成功对接。[参考资料](/docs/reference/config/policy-and-telemetry/adapters/solarwinds/)

- **Redis Quota**。 Mixer 为速率限制功能提供了基于 Redis 的适配器。[参考资料](/docs/reference/config/policy-and-telemetry/adapters/redisquota/)

- **Datadog**。Mixer 实现了向 Datadog 代理输出指标数据的适配器。[参考资料](/docs/reference/config/policy-and-telemetry/adapters/datadog/)

## 其它

- **分离检查和报告集群**：可以配置 Envoy，使用不同的集群和 Mixer 实例协作，分别完成检查和报告任务。较大规模的部署中，这一功能可能对 Mixer 的伸缩有一定帮助。

- **监控仪表盘**：在 Grafana 中提供了初步的 Mixer 和 Pilot 监控仪表盘。

- **Servicegraph**：Servicegraph 升级了新的可视效果。[参考资料](/zh/docs/tasks/telemetry/servicegraph/)

- **存活和就绪检测**：Istio 组件提供了正式的存活以及就绪检测功能，用于确定服务网格基础设施的健康情况。[参考资料](/zh/docs/tasks/security/health-check/)

- **Egress 策略和遥测**：Mixer 现在可以监控同 `EgressRule` 所定义的外部服务进行通信的流量，并且可以在这些流量中使用 Mixer 策略。
