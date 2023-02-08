

This is an shame-less wrapper for 3rd-party [Library Charts](https://helm.sh/docs/topics/library_charts/),
it allows by code structure (values.yml) to define the deployment with almost any content.

I use this for [kluctl.io](https://kluctl.io) + Kustomize deployment.


### Usage

Pre-set is BJW-S library, originally part of k8s-at-home (as I do understand).

Common values:
- https://github.com/k8s-at-home/library-charts/tree/main/charts/stable/common/values.yaml

Alternatives:
- https://github.com/buttahtoast/helm-charts/tree/master/charts/library
- https://helmize.dev/


Example:
```
image:
  # -- image repository
  repository: esphome/esphome
  # -- image pull policy
  pullPolicy: IfNotPresent
  # -- image tag
  tag: 1.18.0

# -- environment variables.
# @default -- See below
env: {}
  # ESPHOME_DASHBOARD_USE_PING: true
  # ESPHOME_DASHBOARD_RELATIVE_URL: "/"
  # ESPHOME_QUICKWIZARD:
  # ESPHOME_IS_HASSIO:
  # DISABLE_HA_AUTHENTICATION:
  # USERNAME:
  # PASSWORD:

# -- Configures service settings for the chart.
# @default -- See values.yaml
service:
  main:
    ports:
      http:
        port: 6052

ingress:
  # -- Enable and configure ingress settings for the chart under this key.
  # @default -- See values.yaml
  main:
    enabled: false

# -- Configure persistence settings for the chart under this key.
# @default -- See values.yaml
persistence:
  config:
    enabled: false
```

#### BJW-S

Some info is at source: https://bjw-s.github.io/helm-charts/docs/app-template/introduction.html

Otherwise k8s-at-home are good examples: https://github.com/k8s-at-home/charts/tree/master/charts/stable (even deprecated now)


### Other

Alternative Helm Library charts:
- https://github.com/bjw-s/helm-charts/tree/main/charts/library/common 
- https://artifacthub.io/packages/helm/buttahtoast/library
- https://artifacthub.io/packages/helm/bitnami/common
- https://artifacthub.io/packages/search?ts_query_web=library&sort=relevance&page=1
- https://github.com/k8s-at-home/library-charts (deprecated now, use bjw-s)
