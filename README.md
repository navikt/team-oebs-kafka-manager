# team-oebs-kafka-manager

Applikasjon for håndtering av Kafka topics. For u1: https://team-oebs-u1-kafka-manager.intern.dev.nav.no/index.html (om man får 404 så slette cookies og logg på igjen)

Kan f.eks brukes for å hente ut meldinger, offsets på consumer, offsets på siste melding eller sette consumer offsets. [kafka-manager](https://github.com/navikt/kafka-manager)

[team-oebs-kafka-manager-u1.yaml](team-oebs-kafka-manager-u1.yaml) er konfig for u1 miljø og tilganger til kafka topics må gis. F.eks i team-oebs-iac

```deployes med kubectl apply -f team-oebs-kafka-manager-u1.yaml```

Skal så komme opp som en pod man ser med ```kubectl get pods -n team-oebs```
Om ikke kan man sjekke med ```kubectl get applications -n team-oebs```
