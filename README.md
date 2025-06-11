# 🛡️ WAZUH-Sentinel-AD : Active Directory Ultimate rules for Wazuh

<img src="./img/wazuh_sentinel_ad4.png"/>

![Wazuh](https://img.shields.io/badge/Wazuh-Compatible-blue) ![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red) ![License](https://img.shields.io/badge/license-MIT-green)

## Description

Ce dépôt contient un ensemble de règles Wazuh avancées, spécialement conçues pour détecter les attaques et comportements suspects sur un environnement **Windows Active Directory**.

🔍 Basées sur le framework [MITRE ATT&CK](https://attack.mitre.org), ces règles couvrent :
- Reconnaissance
- Mouvement latéral
- Dumping de credentials
- Persistences GPO, scheduled tasks, services
- DCSync, Mimikatz, Kerberoasting, Golden Ticket...
---

## Structure MITRE couverte

| Tactic              | Techniques incluses                                        |
|---------------------|-------------------------------------------------------------|
| Credential Access   | `T1003`, `T1558`, `T1078`, `T1115`, `T1055`                |
| Execution           | `T1059`, `T1140`, `T1218`, `T1543`                         |
| Persistence         | `T1053`, `T1484`, `T1543`, `T1047`                         |
| Discovery           | `T1069`, `T1087`, `T1482`                                  |
| Lateral Movement    | `T1021`, `T1075`                                           |
| Defense Evasion     | `T1070`, `T1107`, `T1055`                                  |
| Exfiltration        | `T1560`, `T1071`                                           |
| Privilege Escalation| `T1136`, `T1098`, `T1222`                                  |
| Command and Control | `T1105`                                                    |
| Impact              | `T1485`, `T1107`           

---


## Fonctionnalités principales

- Détection en temps réel via logs Windows + Sysmon
- Corrélation entre événements pour alerter uniquement sur les séquences suspectes
- Mapping MITRE intégré pour enrichir vos dashboards Kibana / Wazuh
- Format propre et modulaire : facile à adapter à vos besoins

---

## Installation

1. Copiez le fichier XML dans le répertoire des règles Wazuh :
```bash
sudo cp AD_Ultimate_Rules.xml /var/ossec/etc/rules/
```

2. Ajoutez cette ligne dans `/var/ossec/etc/ossec.conf` :
```xml
<rule_file>rules/AD_Ultimate_Rules.xml</rule_file>
```

3. Redémarrez le manager :
```bash
sudo systemctl restart wazuh-manager
```

---

## 📄 Licence

Ce projet est sous licence MIT. Faites-vous plaisir, modifiez, partagez et créditez si vous l'utilisez :)

---

## 🙋 Auteur

**Florian Dudaev (aka Dudix)**  
🔗 [https://github.com/CyberFlooD](https://github.com/CyberFlooD)

---
