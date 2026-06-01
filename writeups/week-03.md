## Théorie 2.4 — Indicators of Malicious Activity

- IOC (Indicator of Compromise) : artefact observable qui signale une compromission
- Réseau : pic de trafic anormal (DDoS), DNS vers IPs inattendues, latence anormale (MITM)
- Applicatif : balises <script> dans les URLs (XSS), quotes dans les requêtes (SQLi), multiples échecs de login sur comptes différents (password spraying)
- Génériques : account lockout (brute force), impossible travel, concurrent sessions, logs supprimés ou manquants, consommation anormale CPU/RAM/réseau
- Dans le lab : Wazuh (W6) détectera ces indicateurs via des règles personnalisées

## Théorie 2.5 — Mitigation Techniques

- Mitigation = réduire l'impact ET la probabilité d'une menace (pas éliminer)
- Segmentation : diviser le réseau en zones isolées (pfSense LAN/DMZ dans le lab)
- Least privilege : droits minimaux nécessaires (ex : user dvwa limité à la base dvwa)
- Hardening : réduire la surface d'attaque (UFW, fail2ban, SSH config sur Ubuntu Server)
- Patching : appliquer les correctifs régulièrement
- Encryption : chiffrer données au repos et en transit
- Monitoring : SIEM, IDS, logs continus
- Decommissioning : retirer les systèmes inutilisés proprement
- Isolation : séparer un système sensible ou compromis

## Lab W3

- 31 mai : Exploit XSS réussi sur DVWA
  Payload : <script>alert('XSS')</script>
  Mécanisme : balise script interprétée par le navigateur au lieu d'être affichée comme texte
  Risque réel : vol de cookies de session, redirection, keylogging
  Fix : filtrage et encodage des inputs côté serveur

- 31 mai : Hardening Ubuntu Server
  UFW actif : deny incoming par défaut, allow 22/tcp et 80/tcp uniquement
  fail2ban installé et actif : protection brute force SSH
  SSH config : PermitRootLogin no, MaxAuthTries 3

- Screenshots : docs/screenshots/w2-dvwa-xss.png,
  docs/screenshots/w3-ubuntu-hardening-ufw.png,
  docs/screenshots/w3-ubuntu-hardening-fail2ban.png
