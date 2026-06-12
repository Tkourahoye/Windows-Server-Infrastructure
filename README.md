# 🖥️ Infrastructure Windows Server — Projet d'entreprise simulée

Déploiement complet d'une infrastructure réseau d'entreprise sous **Windows Server 2019/2025**, en environnement virtualisé (VMware Workstation). Le projet couvre l'annuaire, les services réseau, la sécurité, le déploiement et la haute disponibilité — soit la majorité des briques qu'on retrouve dans une salle serveur de PME.

## 🎯 Objectif du projet

Construire, configurer et tester une infrastructure réseau réaliste avec un domaine Active Directory (`formation.com`), tout en pratiquant la résolution de pannes typiques d'un environnement virtualisé (conflits MAC, configuration réseau, quorum de cluster...).

## 🏗️ Topologie

| VM | Rôle |
|---|---|
| **WSERVER** | Contrôleur de domaine — AD DS, DNS, DHCP, GPO, WDS |
| **SRV-NLB1 / SRV-NLB2** | Cluster NLB (répartition de charge web) |
| **SRV-FC1 / SRV-FC2** | Nœuds du cluster de basculement |
| **SRV-ISCSI** | Cible iSCSI — stockage partagé du cluster |
| **PC-CLIENT1** | Poste client joint au domaine |

## 📋 Modules

| Module | Description | Statut |
|---|---|---|
| [**01 — AD DS / DNS / DHCP**](01-ad-ds-dns-dhcp/) | Contrôleur de domaine, zones DNS, étendue DHCP, jonction d'un poste client | ✅ |
| [**02 — GPO**](02-gpo/) | Stratégies de groupe appliquées par unité d'organisation | ✅ |
| [**03 — WDS**](03-wds/) | Déploiement d'images Windows par le réseau (PXE) | ✅ |
| [**04 — Redondance / Haute disponibilité**](04-redondance-ha/) | NLB (répartition de charge) + Failover Clustering avec stockage iSCSI | ✅ |
| **05 — Partage de fichiers** | Permissions NTFS/partage, dossiers de groupe | 🔄 À venir |
| **06 — Accès distant / VPN** | RRAS, VPN | 🔄 À venir |
| **07 — Exchange Server** | Messagerie d'entreprise | 🔄 En cours |

## 🧰 Environnement technique

`Windows Server 2019` `Windows Server 2025` `VMware Workstation` `Active Directory` `DNS` `DHCP` `GPO` `WDS` `NLB` `Failover Clustering` `iSCSI`

## 👤 Auteur

**Thierno Ibrahima Kourahoye Diallo** ([@Tkourahoye](https://github.com/Tkourahoye))
Étudiant en Génie Informatique (L3) — Université Barrack Obama, Conakry, Guinée
Projet réalisé sous la supervision de **Pr. Bilo**
