# messagebroker-service

Repo de configuration/tests pour le broker de messages **RabbitMQ** de la plateforme **DREAMHOUSE237**.

## Rôle

Ce repo ne contient pas de code applicatif : en production, le broker est déployé directement depuis l'image officielle `rabbitmq:3-management` (voir `infrastructure/docker-compose.prod.yml`), et ce dépôt sert de point d'ancrage pour la documentation et d'éventuels tests de connectivité aux queues.

RabbitMQ assure la communication asynchrone entre les microservices : inscriptions (`user_created`, `user_verified`, `user_auth_ack`), notifications (`user-email-queue`), et paiements (`payment-queue`, `payment-status`).

## Accès

- Port AMQP : `5672`
- Console de management : `15672`

Les identifiants (`RABBITMQ_USER` / `RABBITMQ_PASSWORD`) sont injectés via les secrets GitHub Actions au déploiement.

## Déploiement

Via **Docker Swarm** (voir [`infrastructure`](https://github.com/DREAMHOUSE-237/infrastructure)).
