# Totoro PWA — Prototype jouable V0.1

Application web installable, en français, sans dépendances externes. Totoro est immortel.

## Lancer

Sur PC : dans ce dossier, `python -m http.server 8000`, puis ouvrir `http://localhost:8000`.
Sur Android : héberger le dossier sur un serveur HTTPS (par exemple GitHub Pages), ouvrir l'URL dans Chrome puis choisir « Ajouter à l'écran d'accueil » ou « Installer l'application ».
Un fichier HTML ouvert directement depuis le gestionnaire de fichiers ne suffit pas à installer une PWA.

## Fonctionnalités présentes

- Interface responsive, scènes dessinées en Canvas 2D : table blanche avec tipi, hamac, gamelles et litière ; canapé ; pommier.
- Totoro stylisé (dessin vectoriel temporaire), yeux bleus louchants, 3 tailles selon stade.
- Cycle jour/nuit local, activités autonomes, faim/énergie/bonheur sans punition ni mort.
- Caresses tactiles, repas, jeu, repos, audio synthétique facultatif.
- Évolution automatique : bébé 0–2 jours, jeune 2–6 jours, adulte ensuite.
- Apparition illustrée occasionnelle de la fille sur le canapé (placeholder), tenue selon stade.
- Sauvegarde locale, export/import JSON, veille simulée après inactivité, fonctionnement hors ligne après première visite.

## Limites assumées de cette V0.1

Il s'agit d'un prototype jouable, **pas encore de la V1.0 complète** : pas de véritables sprites dessin animé, ni d'animations frame par frame ; pas de météo API, géolocalisation, profils Wi-Fi maison/travail, OTA, mini-jeux distincts, personnalisation de décor, visiteurs autonomes ou scènes familiales scénarisées. Les sons sont synthétiques et la veille est un écran noir logiciel. Les horaires dépendent de l'heure du téléphone. L'activité autonome ne s'exécute pas en arrière-plan quand Android suspend la PWA ; au retour, les besoins sont recalculés sans pénalité.

## Architecture prévue

- `app.js` contient encore les modules en un fichier pour faciliter les tests : état/simulation, sauvegarde, scène Canvas, interactions, paramètres.
- Étape suivante : séparer `core/`, `render/`, `scenes/`, `assets/`, `services/`, `ui/`, ajouter tests et sprites cohérents.
- JSON versionné, destiné à servir de base au format commun Android/ESP32 (migration à prévoir).

## Sécurité des données

La sauvegarde reste dans le stockage local du navigateur, susceptible d'être effacé par Android ou l'utilisateur. Exporter régulièrement le fichier JSON. Aucun serveur, compte ou collecte de données n'est utilisé dans ce prototype.
