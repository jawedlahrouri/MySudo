[![Academic Year](https://img.shields.io/badge/Epitech-Tek1-blue?style=for-the-badge&logo=epitech&logoColor=white)](https://www.epitech.eu/)
[![Language: C](https://img.shields.io/badge/Language-C-00599C.svg?style=for-the-badge&logo=c)](https://en.wikipedia.org/wiki/C_(programming_language))
[![Module](https://img.shields.io/badge/Module-B--PSU--100-informational?style=for-the-badge)](#)

# 🔐 MySudo — Reconstitution Sécurisée de la Commande 'sudo'

**MySudo** est une implémentation en C du mécanisme d'élévation de privilèges Unix `sudo`. Ce projet permet à un utilisateur autorisé d'exécuter des commandes système sous l'identité d'un autre utilisateur ou du superutilisateur (`root`), tout en vérifiant l'authentification et les autorisations.

---

## ⚙️ Fonctionnalités & Sécurité

- **Résolution des Utilisateurs & Groupes** :
  - Parsing précis des fichiers d'administration système `/etc/passwd` et `/etc/group`.
  - Résolution des identifiants UID et GID cibles.
- **Authentification par Mot de Passe** :
  - Lecture masquée du mot de passe sur l'entrée standard (sans écho terminal).
  - Validation cryptographique via `crypt()` en confrontant le sel et le hash stocké dans `/etc/shadow`.
- **Exécution sous Identité Cible** :
  - Modification des identifiants réels et effectifs via les appels système `setuid()` et `setgid()`.
  - Préservation ou assainissement des variables d'environnement.
  - Lancement du binaire cible via `execvp()`.

---

## 💻 Options Disponibles

```bash
./my_sudo [-u user] [-g group] [-s] command [args...]
```

| Option | Description |
|---|---|
| `-u <user>` | Exécute la commande sous l'identité de l'utilisateur spécifié (par défaut : `root`). |
| `-g <group>` | Exécute la commande avec le groupe spécifié. |
| `-s` | Lance le shell par défaut de l'utilisateur (défini par `SHELL` ou `/bin/sh`). |
| `-h` | Affiche l'aide et la syntaxe d'utilisation. |

---

## 🛠️ Compilation

```bash
make        # Génère le binaire 'my_sudo'
make clean  # Nettoie les fichiers objets (.o)
make fclean # Supprime les binaires et fichiers intermédiaires
make re     # Recompile le projet
```

> [!NOTE]
> Pour tester l'élévation réelle de privilèges, le binaire doit appartenir à root et posséder le bit SetUID activé :  
> `sudo chown root:root my_sudo && sudo chmod 4755 my_sudo`
