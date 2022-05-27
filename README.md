# HAProxy Pacakge

HAProxy is a TCP proxy and a HTTP reverse proxy. It supports SSL termination and offloading, TCP and HTTP normalization, traffic regulation, caching and protection against DDoS attacks.

## Configuration Reference

You can configure the following:

### Traffic Exposure Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|service.type|haproxy service type|string|LoadBalancer|
|service.clusterIP|haproxy service Cluster IP|string|" "|
|service.loadBalancerIP|haproxy service Load Balancer IP|string|" "|
|service.externalTrafficPolicy|haproxy service external traffic policy|string|cluster|
|service.annotations|Additional custom annotations for haproxy service|string|{}|
|service.sessionAffinity|Session Affinity for Kubernetes service, can be "None" or "ClientIP"|string|none|
|service.sessionAffinityConfig|Additional settings for the sessionAffinity|string|{}|
|service.labels|Additional custom labels for haproxy service|string|{}|

### HAProxy Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|image.registry|HAProxy image registry|string|docker.io|
|image.repository|HAProxy image repository|string|bitnami/haproxy|
|image.tag|HAProxy image tag (immutable tags are recommended)|string|2.5.1-debian-10-r0|
|image.pullPolicy|HAProxy image pull policy|string|IfNotPresent|
|replicaCount|Number of haproxy replicas to deploy|integer|1|
|startupProbe.enabled|Enable startupProbe on haproxy nodes|string|false|
|startupProbe.initialDelaySeconds|Initial delay seconds for startupProbe|integer|15|
|startupProbe.periodSeconds|Period seconds for startupProbe|integer|10|
|startupProbe.timeoutSeconds|Timeout seconds for startupProbe|integer|5|
|startupProbe.failureThreshold|Failure threshold for startupProbe|integer|5|
|startupProbe.successThreshold|Success threshold for startupProbe|integer|1|
|livenessProbe.enabled|Enable livenessProbe on haproxy nodes|string|true|
|livenessProbe.initialDelaySeconds|Initial delay seconds for livenessProbe|integer|15|
|livenessProbe.periodSeconds|Period seconds for livenessProbe|integer|10|
|livenessProbe.timeoutSeconds|Timeout seconds for livenessProbe|integer|5|
|livenessProbe.failureThreshold|Failure threshold for livenessProbe|integer|5|
|livenessProbe.successThreshold|Success threshold for livenessProbe|integer|1|
|readinessProbe.enabled|Enable readinessProbe on haproxy nodes|string|true|
|readinessProbe.initialDelaySeconds|Initial delay seconds for readinessProbe|integer|15|
|readinessProbe.periodSeconds|Period seconds for readinessProbe|integer|10|
|readinessProbe.timeoutSeconds|Timeout seconds for readinessProbe|integer|5|
|readinessProbe.failureThreshold|Failure threshold for readinessProbe|integer|5|
|readinessProbe.successThreshold|Success threshold for readinessProbe|integer|1|
|customStartupProbe|Custom startupProbe that overrides the default one|string|{}|
|customLivenessProbe|Custom livenessProbe that overrides the default one|string|{}|
|customReadinessProbe|Custom readinessProbe that overrides the default one|string|{}|
|resources.limits|The resources limits for the haproxy containers|string|{}|
|resources.requests|The requested resources for the haproxy containers|string|{}|
|podSecurityContext.enabled|Enabled haproxy pods' Security Context|string|true|
|podSecurityContext.fsGroup|Set haproxy pod's Security Context fsGroup|integer|1001|
|containerSecurityContext.enabled|Enabled haproxy containers' Security Context|string|true|
|containerSecurityContext.runAsUser|Set haproxy containers' Security Context runAsUser|integer|1001|
|containerSecurityContext.runAsNonRoot|Set haproxy container's Security Context runAsNonRoot|string|true|
|pdb.create|Enable a Pod Disruption Budget creation|string|false|
|pdb.minAvailable|Minimum number/percentage of pods that should remain scheduled|integer|1|
|pdb.maxUnavailable|Maximum number/percentage of pods that may be made unavailable|string|""|
|autoscaling.enabled|Enable Horizontal POD autoscaling for HAProxy|string|false|
|autoscaling.minReplicas|Minimum number of HAProxy replicas|integer|1|
|autoscaling.maxReplicas|Maximum number of HAProxy replicas|integer|11|
|autoscaling.targetCPU|Target CPU utilization percentage|integer|50|
|autoscaling.targetMemory|Target Memory utilization percentage|integer|50|
|podLabels|Extra labels for haproxy pods|string|{}|
|podAnnotations|Annotations for haproxy pods|string|{}|
|podAffinityPreset|Pod affinity preset. Ignored if affinity is set. Allowed values: soft or hard|string|""|
|podAntiAffinityPreset|Pod anti-affinity preset. Ignored if affinity is set. Allowed values: soft or hard|string|soft|
|nodeAffinityPreset.type|Node affinity preset type. Ignored if affinity is set. Allowed values: soft or hard|string|""|
|nodeAffinityPreset.key|Node label key to match. Ignored if affinity is set|string|""|
|configuration|haproxy configuration|string|""|
|existingConfigmap|configmap with HAProxy configuration|string|""|
|affinity|Affinity for haproxy pods assignment|string|{}|
|nodeSelector|Node labels for haproxy pods assignment|string|{}|
|schedulerName|Name of the k8s scheduler (other than default)|string|""|
|updateStrategy.type|haproxy statefulset strategy type|string|RollingUpdate|
|priorityClassName|haproxy pods' priorityClassName|string|""|
|lifecycleHooks|for the haproxy container(s) to automate configuration before or after startup|string|{}|
|extraEnvVarsCM|Name of existing ConfigMap containing extra env vars for haproxy nodes|string|""|
|extraEnvVarsSecret|Name of existing Secret containing extra env vars for haproxy nodes|string|""|
|Ports.containerPort|ports of the container port|integer|8080|
|ports.http|ports of HTTP|integer|80|

### Other Parameters

|Parameter|Description|Type|Default|
|---------|-----------|----|-------|
|serviceAccount.create|Specifies whether a ServiceAccount should be created|string|true|
|serviceAccount.name|Name of the service account to use. If not set and create is true, a name is generated using the fullname template.|string|""|
|serviceAccount.automountServiceAccountToken|Automount service account token for the server service account|string|true|
|serviceAccount.annotations|Annotations for service account. Evaluated as a template. Only used if create is true.|string|{}|



