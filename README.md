# 🔐 MySudo — Unix Privilege Escalation Tool

[![Academic Year](https://img.shields.io/badge/Epitech-Tek1-blue?style=for-the-badge&logo=epitech&logoColor=white)](https://www.epitech.eu/)
[![Module](https://img.shields.io/badge/Module-B--PSU--100-informational?style=for-the-badge)](#)
[![Language](https://img.shields.io/badge/Language-C-00599C?style=for-the-badge&logo=c&logoColor=white)](#)

## 📘 Description
**MySudo** réimplémente le mécanisme d'élévation de privilèges de la commande Unix `sudo`. Il permet à un utilisateur autorisé d'exécuter une commande avec les privilèges d'un autre utilisateur (ou de `root`), en contrôlant les permissions via `/etc/sudoers` et les mécanismes d'authentification PAM / shadow.

## 🔨 Compilation & Utilisation
```bash
make
./my_sudo -u root whoami
```
