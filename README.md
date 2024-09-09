# Description

A Chart project for uniovi-avib-morphingprojections-backend-job microservice

# Deploye steps

**STEP01**: create a helm chart projection

```
$ helm create uniovi-avib-morphingprojections-backend-job-chart
```

**STEP02**: build chart package

This command will generate zip file locally with our chart configuration. The name depends on the  chart name and version configured

```
$ helm package .
```

**STEP03**: publish chart package in Azure Container Registry

This command will publish our chart package inside our ACR repository

```
$ helm push uniovi-avib-morphingprojections-backend-job-chart-1.1.0.tgz oci://avibdocker.azurecr.io/helm
```

```
docker build --build-arg ARG_SPRING_PROFILES_ACTIVE=avib --build-arg ARG_ARGO_TOKEN=eyJhbGciOiJSUzI1NiIsImtpZCI6Ikd4Mkl0WkxDbzR6UzN2LXpPQXZ6WUgxMWlScWtiZFUyQkhPRUp5NjRUbFkifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJhcmdvIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQubmFtZSI6ImFyZ28uc2VydmljZS1hY2NvdW50LXRva2VuIiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZXJ2aWNlLWFjY291bnQubmFtZSI6ImFyZ28iLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC51aWQiOiJjY2M3YTk3My00OTQyLTRjMmEtOWIwZi1hMzA1MTQzYjI3ZjMiLCJzdWIiOiJzeXN0ZW06c2VydmljZWFjY291bnQ6YXJnbzphcmdvIn0.K-nSZfJf3RByESepEyyMFFEaRcCjMMjHI3mZOaaaI6ZyoK7oPQ25ZoP4JZ_asF9BDKoefOcTpEtH7ZewhJZdvTjsvllSL6AKuSd1nIxjDKTR23uUGNrxB8YFTHdQGsk2lRondUud15J6BwmEp7zht8-zhUv24IX8Pr87_5OLIx3KyPpz9jcXD3k2FOBLjSxz3Tp4kaLQ5h7PncHzQ-Ne9vEW26GRtMUOYF34ejx9omCykNUMXXsE7yajd3TRePZ5CPMXkQsciiWuaw3CLmruFp8vqdsN7rvPqyoHV9ybbFNy-wHCiwn_2pHOGA676gss7AAno9tw-dAVLIYzLooxrA -t uniovi-avib-morphingprojections-backend-job:1.3.0 .
```