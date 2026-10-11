# Laboratoire personnel de réseau et de cybersécurité
## Présentation
J'ai conçu et déployé un laboratoire personnel reproduisant certains éléments de l'infrastructure réseau d'une petite entreprise afin d'étudier concrètement l'administration réseau, la sécurité et la détection d'événements.
Ce projet me permet de mettre en pratique plusieurs compétences : configuration d'un pare-feu, contrôle des flux réseau, accès distant sécurisé, centralisation des journaux et analyse des événements de sécurité.
## Architecture principale :
L’infrastructure du lab est constituée des équipements et solutions suivants :
-	OPNsense : pare-feu et passerelle réseau fonctionnant sur un mini-pc firewall Intel N150.
-	WireGuard : accès distant sécurisé à l'infrastructure (VPN).
-	Raspberry Pi 3B+ : serveur hébergeant les solutions de gestion et d'analyse des journaux.
-	Promtail : collecte et transmission des journaux.
-	Loki : stockage et interrogation des journaux.
-	Grafana : organiser visuellement les logs sur un tableau de bord.

## Mise en œuvre de l'architecture réseau et des services de sécurité
### Administration réseau et sécurisation des équipements
- Configuration et administration d'OPNsense.
- Mise en place d'un tunnel VPN chiffré via WireGuard.
- Configuration de règles de filtrage réseau.
- Étude de la segmentation réseau et de l'isolation des équipements grâce à une DMZ.
### Centralisation et analyse des journaux
J'ai mis en place une chaîne de centralisation des journaux d'OPNsense vers un Raspberry Pi :
# OPNsense -> Syslog -> Promtail -> Loki -> Grafana
Le tableau de bord Grafana permet de visualiser :
-	Le volume des logs et son évolution.
-	Les événements détectés comme des erreurs.
-	Les événements liés au DHCP.
-	Les requêtes DNS et les réponses DNS sans erreur.
-	Les événements récents du pare-feu.
J'ai également diagnostiqué et corrigé un problème de compatibilité de Loki avec l'architecture ARM 32 bits du Raspberry Pi, puis vérifié son fonctionnement.

## Tests de sécurité
Je réalise aussi des tests de pénétration à différentes échelle contre mon laboratoire afin de mieux comprendre les mécanismes de protection et leurs limites, ainsi que de tester la sécurité de mes installations. J'effectue différents types d'attaques comme de l'analyse réseau (à l'aide de wireshark). J'étudie la vulnérabilité des différents système connecté et je réalise aussi des captures de handshake wifi (échange d'authentification Wi-Fi en utilisant le monitor mode de mon antenne wifi.
Les tests sont réalisés sur mon propre laboratoire, dans un environnement que je contrôle.

## Évolutions prévues
-	Ajouter la supervision des ressources système d'OPNsense et du Raspberry Pi : processeur, mémoire, stockage, température et interfaces réseau.
-	Segmentation du LAN sous la forme de VLAN lorsque je disposerai d'un switch manageable.
-	Concevoir une architecture réseau sur AWS.
-	Utiliser Terraform pour versionner et déployer l'infrastructure cloud de mon propre lab.
-	Étudier le fonctionnement de la journalisation, de la gestion des identités/accès (IAM) et des mécanismes de détection d'intrusion dans le cloud.

## Objectifs de ce projet
Je fais constamment évoluer ce laboratoire au fur et à mesure que j'acquiers de nouvelles compétences. Ce laboratoire constitue un environnement d'expérimentation permettant de mettre en œuvre et de consolider mes compétences en administration réseau, systèmes, cybersécurité et principalement l'architecture cloud. Il s'inscrit très largement dans la continuité de mon projet de poursuite d'études en BTS CIEL, (option A, informatique et réseau). Mais aussi de mon orientation vers la cybersécurité et les architectures sécurité cloud.

