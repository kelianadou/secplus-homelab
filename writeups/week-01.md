## Théorie 1.1

- 4 catégories : Technical (pare-feu, chiffrement), Managerial (politiques, audits), 
  Operational (revue de logs, sauvegardes), Physical (serrures, caméras, badges)
- 6 types : Preventive (bloque physiquement), Deterrent (dissuade psychologiquement), 
  Detective (détecte et alerte), Corrective (répare après incident), 
  Compensating (remplace un contrôle manquant), Directive (oriente par instruction)
- Piège clé : Preventive bloque concrètement. Deterrent dissuade sans bloquer.
  Test : si je désactive le contrôle, l'attaque devient-elle automatiquement possible ? 
  Oui = Preventive. Non = Deterrent.

## Théorie 1.2

- CIA : Confidentiality (accès réservé aux autorisés), Integrity (données non altérées 
  sans autorisation), Availability (service accessible quand nécessaire)
- Ransomware viole les 3 : Confidentiality (exfiltration), Integrity (chiffrement = 
  modification), Availability (accès bloqué)
- AAA : Authentication (qui es-tu ?), Authorization (que peux-tu faire ?), 
  Accounting (qu'as-tu fait ? — logs, audit trail, SIEM)
- Zero Trust : never trust, always verify. Même les utilisateurs internes connus 
  doivent être vérifiés à chaque accès. Opposé du modèle périmétrique.


## Lab W1
- 12 mai : VM pfSense déployée (WAN em0 NAT 10.0.2.15, LAN em1 lab-lan 10.0.10.1/24, DHCP 10.0.10.100-200)
- 18 mai : VM Ubuntu Server déployé sur lab-lan. IP DHCP reçue 10.0.10.100/24, confirme que pfSense distribue correctement les adresses IP.
- Screenshots : docs/screenshots/w1-pfsense-console-post-install.png, 
  docs/screenshots/w1-ubuntu-srv-dhcp.png
