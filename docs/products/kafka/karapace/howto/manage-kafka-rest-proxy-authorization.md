---
title: Manage Apache Kafka® REST proxy authorization
---

Apache Kafka® REST proxy authorization allows you to use the RESTful
interface to connect to Kafka clusters, produce and consume messages
easily, and execute administrative activities using Aiven CLI. This
feature is disabled by default, and you need to
[enable Apache Kafka REST proxy authorization](/docs/products/kafka/karapace/howto/enable-oauth-oidc-kafka-rest-proxy).

When you enable Apache Kafka REST proxy authorization, Karapace sends
the HTTP basic authentication credentials to Apache Kafka®. The
authentication and authorization are then performed by Apache Kafka,
depending on the ACL defined in Apache Kafka. To configure the ACLs for
authorization, see
[Kafka Access Control Lists (ACLs)](/docs/products/kafka/concepts/acl).

When Apache Kafka REST proxy authorization is disabled, the REST Proxy
bypasses the Apache Kafka ACLs, so any operation via REST API call is
performed without any restrictions.
