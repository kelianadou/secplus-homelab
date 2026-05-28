## Théorie 2.1 — Threat Actors

- 6 types :
        Nation-state (espionnage, ressources élevées)
        Unskilled attacker (script kiddie, outils existants)
        Hacktivist (motivations idéologiques/politiques)
        Insider threat (accès légitime, vengeance ou négligence)
        Organized crime (gain financier, ransomware)
        Shadow IT (employés internes, outils non approuvés, vulnérabilités involontaires)

- 3 attributs : Internal vs external, Resources/funding, Level of sophistication
- Insider threat = le plus dangereux pour une PME : accès légitime déjà en place

## Théorie 2.2 — Attack Surfaces

- Vecteurs principaux :
        message-based (phishing, smishing) 
        file-based (macros, PDFs) 
        removable device (USB)
        unsecure networks (Wi-Fi public)
        open service ports
        default credentials
        vulnerable/unsupported software
        supply chain

- Principe clé : réduction de la surface d'attaque : fermer ports inutiles, changer credentials par défa>
- Unsupported systems : les mises à jour ne suffisent pas si end-of-life, il faut remplacer ou isoler

## Théorie 2.3 — Vulnérabilités

- Catégories :
        Application (SQLi, XSS, buffer overflow)
        OS-based, Hardware (firmware) 
        Virtualization (VM escape)
        Cloud-specific (mauvaise config S3, IAM trop large)
        Supply chain (SolarWinds)
        Cryptographic
        Misconfiguration
        Zero-day
        Mobile

- Misconfiguration = vulnérabilité #1 en production (pas les zero-days)
- Zero-day vs non patchée : zero-day = inconnue du fabricant, pas de patch possible.
  Non patchée = fabricant a sorti le correctif, admin ne l'a pas appliqué.

## Lab W2

- 27 mai : Kali Linux déployé sur lab-lan, IP DHCP 10.0.10.103
- 27 mai : DVWA déployé sur Ubuntu Server (Apache2, PHP, MariaDB)
- 27 mai : Problème DNS pfSense résolu — DNS servers 8.8.8.8/1.1.1.1 ajoutés,
  WAN Adapter 1 corrigé en NAT (était en Internal Network par erreur)
- 27 mai : Premier exploit SQLi réussi sur DVWA
        Payload : 1' OR '1'='1 → retourne tous les utilisateurs
        Mécanisme : condition toujours vraie contourne le WHERE de la requête SQL
        Fix : requêtes préparées (prepared statements)
