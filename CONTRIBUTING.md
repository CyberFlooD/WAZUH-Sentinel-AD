# 🤝 Guide de contribution

Bienvenue dans le projet **WAZUH-SENTINEL-AD : Ultimate Rules** !  
Merci de votre intérêt pour contribuer à améliorer ce pack de détection avancée pour Active Directory.

---

## 📌 Objectif du projet

Ce dépôt contient un ensemble de règles Wazuh axées sur la détection des attaques et abus liés à l’environnement **Windows Active Directory**, basées sur le framework **MITRE ATT&CK**.  
Nous visons à créer une **base communautaire robuste, testée et réutilisable**.

---

## 🛠️ Comment contribuer

### 1. 💡 Proposer une règle

Si vous souhaitez ajouter une nouvelle règle :

- 🆕 Créez un fichier XML dans `rules/` (ou éditez-en un existant)
- Utilisez un `id` unique (commencez par `410xxx` ou demandez-en un)
- Ajoutez une `description` claire et concise
- Incluez le mapping **MITRE ATT&CK** si possible
- Respectez le format suivant :

```xml
<rule id="410099" level="12">
  <field name="win.system.eventID">^4688$</field>
  <field name="win.eventdata.CommandLine" type="pcre2">mimikatz</field>
  <description>Exécution suspecte de Mimikatz</description>
  <group>windows,correlation,credential_access</group>
  <mitre>
    <id>T1003.001</id>
  </mitre>
  <options>no_full_log</options>
</rule>
```

### 2. 🐞 Signaler un bug ou un faux positif

Ouvrez une **Issue GitHub** en utilisant le modèle suivant :

```markdown
## Règle concernée
ID : 410015 – Accès à ntds.dit

## Problème observé
Une alerte a été déclenchée alors qu’aucune activité malveillante n’était présente.

## Contexte
- Agent OS : Windows Server 2019
- Utilisateur : backupsvc
- Fichier accédé : C:\Backup\ntds.dit
```

---

## ✅ Checklist avant pull request

- [ ] La règle a un `id` unique et cohérent
- [ ] Elle inclut une description, une tactique MITRE, un groupe et un `level`
- [ ] Elle est testée avec un faux log (facultatif mais recommandé)
- [ ] Elle respecte la logique de corrélation si nécessaire (`if_sid`, `if_matched_sid`)
- [ ] Elle ne génère pas de faux positifs dans un contexte AD typique

---
