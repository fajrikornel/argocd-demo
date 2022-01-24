# Argo CD demo
Argo CD demo to research about high availability GitOps workflow for Kubernetes.

It uses the dummy dashboard app from this [repository](https://github.com/fajrikornel/dummydashboard). The app consists of Laravel dashboard backend(s) and MySQL database(s).

To deploy the app manually:

1. Create the Kubernetes namespace for the app:

        kubectl create namespace <namespace>

2. Apply the manifests in the /app folder:

        cd app && kubectl apply -f . -n <namespace>

## File descriptions:

| File                | Description                                                        |
| ------------------- | ------------------------------------------------------------------ |
| /app/config.yaml    | ConfigMap object to be consumed by the dashboard and database pods |
| /app/dashboard.yaml | Deployment and Service objects for the Laravel dashboard app       |
| /app/database.yaml  | Deployment and Service objects for the MySQL database              |
| /application.yaml   | Application CRD object for Argo CD                                 |

## To-do list

* Deploy Argo CD and analyze its high availability feature
