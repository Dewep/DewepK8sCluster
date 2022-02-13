# DewepK8sCluster

Kubernetes Cluster

## Questions

- Cert-manager, ingress, ... dans leur propre namespace ? -> cert-manager & ingress-controller oui, les ingress non, même namespace que les services / pods / autre ressources de ton microservice
- Migrer un ingress/lb, sans perdre son IP ? -> Je pense que tu peux déclarer l'ip dans le yaml du LB et si cette IP t'appartient, il l'attache ? A tester je dirais
- Split en plusieurs sous-fichiers, plusieurs commandes pour sync ? -> Que veux tu dire par sync ?
- Commande pour tout voir ce que l'on utilise ? -> Si tu veux dire toutes le ressources déclarées, je ne sais pas, il y a kubectl get all mais c'est très succin. Le problème c'est que certaines choses que tu installes dans ton cluster peuvent être ce qu'on appelle des CRD (CustomResourceDefinitions) et comme leur nom l'indique c'est des trucs custom. Si tu veux voir les ressources allouée sur les nodes, tu peux faire un describe dessus et ça va te donner le CPU / RAM limit / requested
- Multi-dépôts, helm chart, avec build, et custom registry ? -> Pas compris
- yml ou yaml ? -> Je pense qu'osef
- apply vs create ? -> Aucun des deux, go helm ou Kustomize (peut être que Kustomize utilise utilise apply ou create en fait, je ne sais pas). Si vraiment nécessaire (genre sur cert-manager par exemple), si tu veux être sûr de jamais override un truc déjà créé (genre pour être sûr de pas changer la config / autre), create, car il me semble qu'il throw si la ressource existe déjà. Si tu t'en fous, apply
- service, services, Service, svc, WTF BRO -> Tu as des alias, par exemple po pour pod, pv pour persistentvolumes, pvc pour persistentvolumeclaims
- les NAME dans les get sont pas les mêmes que dans mes yml :cry: -> Tu as un exemple?
- Devoir delete un pod, pour update sa config ? -> Si c'est un configmap monté dans le pod, possible que ce soit nécessaire oui. C'est là tout l'intéret d'avoir plusieurs pods dans ton deployment, car tu peux faire un rolling update et t'as 0 downtime pour peu que tu aies des liveness probes correctes.
- Perturbant de pas savoir tout ce qu'il se passe derrière -> CàD?
- disque dur ? -> PersistantVoume / PersistantVolumeClaim
- Secret dans les chart_values ? --set ne marche pas -> Un exemple?
- Registry, osef pour une réplication, osef de self-hosted, osef si sur k8s ? Pas critique je dirai -> Pas compris
- Renew auto avec cert-manager ? Comment voir les "jobs" ? `certificaterequests.cert-manager.io`. D'autres ressources cool à regarder pour débug les certificates `orders.acme.cert-manager.io` & `challenges.acme.cert-manager.io`
- Next step, helm chart/build ? -> Pas compris :D
- Docker WSL ? -> Pas compris :D
- Review of what I did
