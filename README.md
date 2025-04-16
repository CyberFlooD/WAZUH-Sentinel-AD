# 🛡️ WAZUH Sentinel AD - Active Directory Ultimate rules for Wazuh

![Wazuh](https://img.shields.io/badge/Wazuh-Compatible-blue) ![MITRE ATT&CK](https://img.shields.io/badge/MITRE-ATT%26CK-red) ![License](https://img.shields.io/badge/license-MIT-green)

> Le pack ultime de détection Active Directory pour Wazuh. Inspiré des techniques offensives réelles, construit pour la défense intelligente.

---

## Description

Ce dépôt contient un ensemble de règles Wazuh avancées, spécialement conçues pour détecter les attaques et comportements suspects sur un environnement **Windows Active Directory**.

🔍 Basées sur le framework [MITRE ATT&CK](https://attack.mitre.org), ces règles couvrent :
- Reconnaissance
- Mouvement latéral
- Dumping de credentials
- Persistences GPO, scheduled tasks, services
- DCSync, Mimikatz, Kerberoasting, Golden Ticket...

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

## MITRE ATT&CK Coverage

Les règles couvrent notamment les techniques :
- `T1003`, `T1558`, `T1059`, `T1078`, `T1543`, `T1055`, `T1105`, `T1560`, etc.

---

## 📸 Aperçu

*Capture écran à venir...*

---

## 📄 Licence

Ce projet est sous licence MIT. Faites-vous plaisir, modifiez, partagez et créditez si vous l'utilisez :)

---

## 🙋 Auteur

**Florian Dudaev (aka Dudix)**  
🔗 [https://github.com/CyberFlooD](https://github.com/CyberFlooD)  
📫 contact [at] dudix-consulting.fr

---
