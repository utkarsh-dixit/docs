---
title: Quelles sont les adresses IP du monitoring OVHcloud ?
slug: monitoring-ip-ovh
excerpt: Retrouvez ici les adresses IP a renseigner lors de la mise en place d’un firewall, afin que le monitoring OVHcloud continue de fonctionner sur votre serveur.
section: Réseau & IP
---

**Dernière mise à jour le 17/08/2021**

## Objectif

Le service de monitoring permet de suivre l’état de votre machine et de déclencher automatiquement l’intervention d’un technicien dans le datacentre.

Tous les serveurs de nos clients ainsi que l'ensemble du réseau sont surveillés 24h/24 et 7j/7 par les équipes techniques d'OVHcloud.

OVHcloud intervient dès le déclenchement d'une alerte (non réponse aux pings) afin de limiter au maximum le temps d'indisponibilité des serveurs et du réseau.

Pour mettre en place un firewall restrictif, notamment sur l'ICMP, et continuer de bénéficier du monitoring OVHcloud, il est nécessaire d'autoriser les adresses IP que vous trouverez ci-après.

## Prérequis

- Un produit OVHcloud sur lequel vous avez installé un Firewall.
- Avoir accès aux règles du Firewall.

## En pratique

### Adresses IP à autoriser

|Reverse|IP|Protocole|
|---|---|---|
|mrtg-rbx-100|37.187.231.251|icmp|
|mrtg-sbg-100|37.187.231.251|icmp|
|mrtg-gra-100|37.187.231.251|icmp|
|mrtg-bhs-100|37.187.231.251|icmp|
|mrtg-rbx-101|151.80.231.244|icmp|
|mrtg-rbx-102|151.80.231.245|icmp|
|mrtg-rbx-103|151.80.231.246|icmp|
|mrtg-gra-101|151.80.231.247|icmp|
|a2.ovh.net|213.186.33.62|icmp|
|---|---|---|
|netmon-rbx-probe|92.222.184.0/24|icmp|
|netmon-sbg-probe|92.222.185.0/24|icmp|
|netmon-gra-probe|92.222.186.0/24|icmp|
|netmon-bhs-probe|167.114.37.0/24|icmp|
|netmon-sgp-probe|139.99.1.144/28|icmp|
|---|---|---|
|proxy.p19.ovh.net|213.186.45.4|icmp|
|proxy.rbx.ovh.net|213.251.184.9|icmp|
|proxy.sbg.ovh.net|37.59.0.235|icmp|
|proxy.bhs.ovh.net|8.33.137.2|icmp|
|ping.ovh.net|213.186.33.13|icmp|
|proxy.ovh.net|213.186.50.98|icmp|
|---|---|---|
||xxx.xxx.xxx.250 (xxx.xxx.xxx.aaa étant l'IP du serveur)|icmp|
||xxx.xxx.xxx.251 (xxx.xxx.xxx.aaa étant l'IP du serveur)|icmp + port surveillé par le service monitoring|

**La communication entre le service RTM et votre serveur nécessite également que vous autorisiez les connexions entrantes et sortantes sur les ports UDP 6100 à 6200.**

> [!primary]
>
> Si votre serveur est situé à Roubaix 3, il faut récupérer la dernière IP via tcpdump.
>
> ```
> tcpdump host ip.fixe.du.serveur | grep ICMP
> ```
>

### Activer ou désactiver le monitoring

Tout d’abord, connectez-vous à votre [espace client OVHcloud](https://ca.ovh.com/auth/?action=gotomanager&from=https://www.ovh.com/ca/fr/&ovhSubsidiary=qc){.external} et sélectionnez l'onglet `Bare Metal Cloud`{.action}. Dans le menu de gauche, sélectionnez le serveur concerné dans le menu déroulant `Serveurs dédiés`{.action} .

Dans l'onglet `Informations générales`{.action} puis le cadre **État des services**, cliquez sur le bouton `...`{.action} à côté de « Monitoring ». Cliquez alors sur `Activer`{.action} ou `Désactiver`{.action} . Cliquez sur `Valider`{.action} dans la fenêtre qui apparaît pour confirmer les modifications.

![monitoring](images/monitoring1.png){.thumbnail}

### Activer le monitoring de services spécifiques

En plus du monitoring standard, vous pouvez autoriser à OVHcloud de surveiller des services spécifiques comme le HTTP, le SSH et d’autres protocoles.

 Pour ce faire, dans l'onglet `Informations générales`{.action} puis le cadre **État des services**, cliquez sur le bouton `...`{.action} à côté de « Services Monitorés ». Cliquez sur `Monitorer mes services`{.action}.

![monitoring](images/monitoring2.png){.thumbnail}

 Vous serez redirigé vers l'écran ci-dessous. Cliquez sur `Monitorer un service`{.action} puis renseignez l'adresse IP, le protocole, le numéro de port, la réponse du serveur et l'intervalle de temps entre les vérifications de votre service. Cliquez sur le symbole de validation (**V**) pour confirmer les modifications.

![monitoring](images/monitoring3.png){.thumbnail}

## Aller plus loin

[Configurer le Firewall Network](../firewall-network/)

Rejoignez notre communauté d'utilisateurs sur <https://community.ovh.com/>.
