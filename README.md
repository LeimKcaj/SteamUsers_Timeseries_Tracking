# SteamUsers_Timeseries_Tracking

Projet en Analyse séquentielle de données

# Setup Instructions

Ce projet contient plusieurs notebooks ayant des dépendances lourdes différentes (TensorFlow, Prophet, etc.).
Pour éviter d'installer des centaines de Mo inutilement, **chaque notebook utilise son propre environnement Python**.

## Cloner le projet

git clone https://github.com/LeimKcaj/SteamUsers_Timeseries_Tracking.git
cd SteamUsers_Timeseries_Tracking
---

## Prérequis généraux

* Avoir une installation Python (plusieurs versions si besoin). Sur Windows, le lanceur `py` est pratique (`py -3.10` par ex.).
* Python 3.10 et 3.12 (ou plus selon notebook)
* Git installé
* Ne **committez jamais** les dossiers `.venv` dans le dépôt.
* Toujours installer les paquets via `python -m pip` pour être sûr d'utiliser le bon interpréteur.

---

## TensorFlow Notebook

### 1. Créer et activer l'environnement

```powershell
# Windows
py -3.10 -m venv .venv_tf
.\.venv_tf\Scripts\Activate.ps1
# macOS / Linux
#python3.10 -m venv .venv_tf
#source .venv_tf/bin/activate
```

### 2. Installer les dépendances
```powershell
python -m pip install --upgrade pip
python -m pip install -r envs/tf_requirements.txt
```
### 3. Ajouter le kernel Jupyter (optionnel mais recommandé)
``` powershell
python -m pip install ipykernel
python -m ipykernel install --user --name=venv_tf --display-name "Python (TF)"
```

> Ouvrez le notebook TensorFlow et sélectionnez le kernel **Python (TF)**.

---

## Prophet Notebook

### 1. Créer et activer l'environnement
```powershell
# Windows
py -3.12 -m venv .venv_prophet
.\.venv_prophet\Scripts\Activate.ps1
# macOS / Linux
# python3.12 -m venv .venv_prophet
# source .venv_prophet/bin/activate
```
### 2. Installer les dépendances
```powershell
python -m pip install --upgrade pip
python -m pip install -r envs/prophet_requirements.txt
```
### 3. Ajouter le kernel Jupyter
```powershell
python -m pip install ipykernel
python -m ipykernel install --user --name=venv_prophet --display-name "Python (Prophet)"
```
> Ouvrez le notebook Prophet et sélectionnez le kernel **Python (Prophet)**.

---

## Structure recommandée du dépôt

repo/
├─ notebooks/
│  ├─ tf_notebook.ipynb
│  ├─ prophet_notebook.ipynb
├─ envs/
│  ├─ tf_requirements.txt
│  ├─ prophet_requirements.txt
├─ README.md

---

## Conseils et troubleshooting rapides

* Si `pip` n'est pas trouvé, utilisez toujours `python -m pip ...`.
* Vérifiez la version de Python utilisée pour créer le venv :

  * `py --list` (Windows) ou `python --version`.
* Si PowerShell bloque l'activation des scripts :

  * `Get-ExecutionPolicy`
  * Si nécessaire : `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned`
* Pour convertir à conda, fournis un `environment.yml` au lieu de `requirements.txt`.

Si tu veux que je génère aussi les fichiers `envs/tf_requirements.txt` et `envs/prophet_requirements.txt` de base (proposition), dis-le — je les crée et tu pourras copier-coller pareil.
