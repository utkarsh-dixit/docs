---
title: Utiliser High Performance avec Owncloud
slug: s3/owncloud
excerpt: Découvrez comment configurer le stockage dans Owncloud pour utiliser un bucket High Performance
section: Object Storage S3 High Performance
order: 170
---

**Dernière mise à jour le 03/01/2022**

## Objectif

Owncloud est une suite de logiciels client-serveur pour créer et utiliser des services d'hébergement de fichiers.

**Ce guide explique comment configurer le stockage dans Owncloud pour utiliser un bucket High Performance.**

## Prérequis

- Avoir créé un bucket
- Avoir créé un utilisateur et avoir défini les droits d'accès requis sur le bucket
- Connaître vos informations d'identification S3 (access_key et secret_access_key).

Consultez notre guide « [Débuter avec S3 High Performance](https://docs.ovh.com/fr/storage/s3/debuter-avec-s3/) » pour plus de détails.

## En pratique

Si besoin, installez le plugin `External Storage: S3` depuis le `Market`{.action}.

![Owncloud open Market](images/HighPerf-Owncloud-20211209131331778.png){.thumbnail}

Recherchez le plugin `External Storage: S3`.

![Owncloud plugin External Storage S3](images/HighPerf-Owncloud-20211209131556714.png){.thumbnail}

Puis installez le plugin.

![Owncloud install plugin](images/HighPerf-Owncloud-20211209131648711.png){.thumbnail}

Rendez-vous dans les `Paramètres`{.action}.

![Owncloud open Settings](images/HighPerf-Owncloud-20211209131942821.png){.thumbnail}

Puis :

1. dans `Storage`{.action}
2. activez `Enable external storage `{.action}
3. nommez votre dossier
4. ajoutez un stockage de type `Amazon S3 compatible (SDK v3)`{.action}

![Owncloud create AWS S3 storage](images/HighPerf-Owncloud-20211209143008822.png){.thumbnail}

Renseignez les informations suivantes :

1. Indiquez le nom de votre bucket
2. Définissez l'hôte comme tel : `s3.<region>.perf.cloud.ovh.net`
3. Définissez le port : 443
4. Indiquez la région
5. Activez SSL
6. Renseignez votre clé d'accès
7. Renseignez votre clé secrète

![Owncloud complete AWS S3 storage](images/HighPerf-Owncloud-20211209133630272.png){.thumbnail}

Allez dans `Files`{.action}.

![Owncloud open Files](images/HighPerf-Owncloud-20211209133730832.png){.thumbnail}

Puis dans `External storage`{.action}.

![Owncloud Files External Storage](images/HighPerf-Owncloud-2021120913382299.png){.thumbnail}

Voici le résultat que vous devez obtenir :

![Owncloud Bucket listing](images/HighPerf-Owncloud-20211209140757288.png){.thumbnail}

## Aller plus loin

Échangez avec notre communauté d'utilisateurs sur [https://community.ovh.com](https://community.ovh.com){.external}.
