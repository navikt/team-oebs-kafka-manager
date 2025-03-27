# team-oebs-kafka-manager

Applikasjon for håndtering av Kafka topics. For u1: https://team-oebs-u1-kafka-manager.intern.dev.nav.no/index.html (om man får 404 så slette cookies og logg på igjen)

Kan f.eks brukes for å hente ut meldinger, offsets på consumer, offsets på siste melding eller sette consumer offsets. [kafka-manager](https://github.com/navikt/kafka-manager)

siste versjon av artifacts finnes her:  Per 01.08.2023 så lastes Docker images opp til Google Artifact Registry (GAR) - i skrivende stund er dette URL-en der disse kan finnes https://console.cloud.google.com/artifacts/docker/nais-management-233d/europe-north1/poao/kafka-manager.

[team-oebs-kafka-manager-u1.yaml](team-oebs-kafka-manager-u1.yaml) er konfig for u1 miljø og tilganger til kafka topics må gis. F.eks i team-oebs-iac

deployes med: ```kubectl apply -f <filnavn>```

Skal så komme opp som en pod man ser med ```kubectl get pods -n team-oebs```
Om ikke kan man sjekke med ```kubectl get applications -n team-oebs```
