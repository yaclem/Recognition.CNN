# Recognition.CNN

Application web Flask qui reçoit une image et propose les cinq prédictions les plus probables avec le modèle préentraîné InceptionV3 (ImageNet). L'interface permet de déposer une image puis de consulter les résultats.

## Prérequis

- Python 3
- Les dépendances de `requirements.txt` : Flask, TensorFlow et Pillow

## Installation et lancement

```bash
git clone https://github.com/yaclem/Recognition.CNN.git
cd Recognition.CNN
python -m venv .venv
```

Activez l'environnement virtuel, puis installez les dépendances et démarrez Flask :

```bash
# macOS / Linux
source .venv/bin/activate

# Windows : .venv\Scripts\activate

pip install -r requirements.txt
python app.py
```

Ouvrez ensuite http://127.0.0.1:5000 dans votre navigateur. Au premier lancement, TensorFlow peut télécharger les poids ImageNet d'InceptionV3.

## Fonctionnement

Les images envoyées sont stockées dans `uploads/`, puis redimensionnées et traitées avant l'inférence. Le modèle renvoie les cinq classes ImageNet les plus probables.

> `app.py` active le mode debug pour le lancement local. N'utilisez pas le serveur de développement Flask en production ; configurez un serveur WSGI et un stockage adapté pour les images.
