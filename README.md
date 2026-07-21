# 🛡️ Automated SOC & SOAR Workflow

Une plateforme d'automatisation de la réponse aux incidents (SOAR) intégrant la détection d'intrusions, la surveillance d'infrastructure et l'analyse décisionnelle par IA.

---

## 📑 Sommaire
- [Présentation](#-présentation)
- [Architecture & Composants](#-architecture--composants)
- [Cas d'Usage & Automatisation](#-cas-dusage--automatisation)
- [Technologies Utilisées](#-technologies-utilisées)
---

## 🎯 Présentation
Ce projet vise à réduire le temps de réponse aux incidents (**MTTR**) en automatisant le flux complet :
`Détection (SIEM/Monitoring) ➡️ Orchestration (n8n) ➡️ Analyse IA ➡️ Remédiation ➡️ Notification`.

---

## 🏗️ Architecture & Composants

* **Wazuh (SIEM/XDR)** : Détection des menaces (Brute Force, FIM - File Integrity Monitoring, etc.).
* **Zabbix** : Surveillance des métriques système et de la disponibilité.
* **n8n** : Moteur d'orchestration et d'automatisation des workflows SOAR.
* **AI Agent** : Analyse contextuelle des alertes et prise de décision/enrichissement automatique.
* **Slack** : Canal centralisé pour l'envoi de notifications et d'alertes en temps réel.

---

## 🚀 Cas d'Usage Traités

1. **Détection Brute Force (Wazuh)** :
   - Capture de l'alerte SIEM par webhook n8n.
   - Analyse par l'Agent IA et exécution de scripts de blocage/remédiation automatique.
2. **Détection Malware (Wazuh & FIM)** :
   - Détection de la création/modification d'un fichier suspect ou de signatures de malware.
   - Déclenchement du workflow de remédiation n8n.
   - Évaluation du risque/contexte par l'**Agent IA**.
   - Suppression sécurisée du fichier infecté sur l'agent cible via SSH et privilèges appliqués.
3. **Surveillance des Ressources (Zabbix)** :
   - Remontée des pics de charge CPU / RAM.
4. **Notifications d'Équipe** :
   - Restitution synthétique des événements et actions prises directement sur Slack.

---

## 💻 Technologies Utilisées

| Composant | Rôle |
| :--- | :--- |
| **Wazuh** | SIEM / Agent-based Security Monitoring |
| **Zabbix** | Infrastructure & Performance Monitoring |
| **n8n** | Workflow Automation / SOAR Platform |
| **LLM / AI Agent** | Intelligent Alert Analysis |
| **Linux / SSH** | Remote Target Remediation |

---

## ⚙️ Installation & Configuration

1. **Cloner le projet** :
   ```bash
   git clone [https://github.com/ferdaousmejhed/SOC.git](https://github.com/ferdaousmejhed/SOC.git)
