# team-oebs-kafka-manager

Applikasjon for håndtering av Kafka-topics med [kafka-manager](https://github.com/navikt/kafka-manager).

## Lenker til Kafka-manager

- t1: <https://team-oebs-t1-kafka-manager.intern.dev.nav.no>
- q1: <https://team-oebs-q1-kafka-manager.intern.dev.nav.no>
- u1: <https://team-oebs-u1-kafka-manager.intern.dev.nav.no>
- prod: <https://team-oebs-kafka-manager.intern.nav.no>

Hvis du får 404 etter innlogging, slett cookies og prøv igjen.

## Konfigurasjon

Nais-manifestene ligger i `kafka/`:

- [kafka/team-oebs-kafka-manager-t1.yaml](kafka/team-oebs-kafka-manager-t1.yaml)
- [kafka/team-oebs-kafka-manager-q1.yaml](kafka/team-oebs-kafka-manager-q1.yaml)
- [kafka/team-oebs-kafka-manager-u1.yaml](kafka/team-oebs-kafka-manager-u1.yaml)
- [kafka/team-oebs-kafka-manager-prod.yaml](kafka/team-oebs-kafka-manager-prod.yaml)

Siste image-versjoner ligger i GAR:
<https://console.cloud.google.com/artifacts/docker/nais-management-233d/europe-north1/poao/kafka-manager>

## Deploy med GitHub Actions

Repoet har to workflows:

- `.github/workflows/deploy-dev.yaml` deployer t1, q1 og u1
- `.github/workflows/deploy-prod.yaml` deployer prod

Workflowene kjører automatisk ved push til `main` når relevante filer i `kafka/` endres:

- dev-workflow: `team-oebs-kafka-manager-t1.yaml`, `-q1.yaml`, `-u1.yaml`
- prod-workflow: `team-oebs-kafka-manager-prod.yaml`

### Trigge manuelt

Du kan trigge workflowene manuelt på to måter:

1. GitHub UI: Actions -> velg workflow -> **Run workflow**.
2. GitHub CLI:
   `gh workflow run deploy-dev.yaml --ref main`
   `gh workflow run deploy-prod.yaml --ref main`

## Deploy med kubectl

Du kan fortsatt deploye direkte med kubectl:

`kubectl apply -f <filnavn>`

Sjekk status:

- `kubectl get pods -n team-oebs`
- `kubectl get applications -n team-oebs`
