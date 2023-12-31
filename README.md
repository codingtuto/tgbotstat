# tgbotstat

**tgbotstat** est un package Python qui vous permet de suivre et d'enregistrer des statistiques d'utilisation de votre bot Telegram. Il peut enregistrer le nombre d'utilisations de chaque commande, les utilisateurs qui ont utilisé ces commandes, les heures auxquelles les commandes sont utilisées, et plus encore.

## Installation

Vous pouvez installer **tgbotstat** à l'aide de `pip`. Assurez-vous d'avoir `pip` installé, puis exécutez la commande suivante :

```bash
pip install tgbotstat
```

# Utilisation

Une fois que vous avez installé **tgbotstat**, vous pouvez l'importer dans votre code Python pour suivre et enregistrer des statistiques d'utilisation. Voici comment vous pouvez l'utiliser dans votre projet :

```python
from tgbotstat import *

# Charger les statistiques existantes
statistiques = charger_statistiques()

# Mettre à jour les statistiques pour une commande
commande = "/start"
user_id = 12345
heure_commande = "14"
jour_semaine = "Lundi"
mettre_a_jour_statistiques_commande(statistiques, commande, user_id, heure_commande, jour_semaine)

# Enregistrer de nouvelles statistiques
sauvegarder_statistiques(statistiques)

# Afficher les données d'utilisation
stats_text = "Statistiques d'utilisation des commandes:\n"
for date, commands in statistiques['commands'].items():
    stats_text += f"\nDate: {date}\n"
    for command, data in commands.items():
        nombre_utilisations = data['nombre_utilisations']
        utilisateurs_commande = len(data['utilisateurs'])
        heures = data.get('heures', {})
        heures_text = ', '.join([f"{heure}: {utilisations} utilisations" for heure, utilisations in heures.items()])
        stats_text += f"- {command} : {nombre_utilisations} utilisations par {utilisateurs_commande} utilisateurs ({heures_text})\n"

print(stats_text)
```

Vous pouvez également utiliser d'autres fonctions et classes exposées par le package, telles que **charger_utilisateurs**, **enregistrer_utilisateur**, **suivre_commandes_populaires**, etc., pour personnaliser vos statistiques en fonction de vos besoins.

# Contribution

Les contributions sont les bienvenues ! Si vous souhaitez améliorer tgbotstat ou ajouter de nouvelles fonctionnalités, n'hésitez pas à ouvrir une demande d'extraction (Pull Request) ou à signaler des problèmes (Issues) sur https://github.com/codingtuto/tgbotstat.

## Travail prévu

Nous prévoyons d'ajouter plusieurs fonctionnalités et améliorations à `tgbotstat` dans les futures versions. Voici un aperçu des travaux prévus :

- Ajout d'un système de génération de statistiques sous forme de graphiques pour une visualisation plus conviviale des données d'utilisation.
- Extension des données analytiques pour fournir des informations plus détaillées sur l'utilisation des commandes.
- Prise en charge de la personnalisation des statistiques, notamment la possibilité de définir des plages de dates personnalisées pour l'analyse.
- Améliorations de la gestion des utilisateurs, y compris la possibilité de suivre les comportements individuels des utilisateurs.
- Documentation étendue avec des exemples d'utilisation avancés.
- Correction de bugs et optimisations de performances.

Nous sommes ouverts aux suggestions de la communauté et aux contributions. Si vous avez des idées d'améliorations ou de nouvelles fonctionnalités que vous aimeriez voir dans `tgbotstat`, n'hésitez pas à ouvrir une issue ou à proposer une pull request sur notre [repository GitHub](https://github.com/codingtuto/tgbotstat).

N'hésitez pas à suivre notre développement et à contribuer à l'amélioration de ce package. Nous sommes impatients de voir comment `tgbotstat` évoluera à l'avenir !

# License

Ce projet est sous licence MIT. Pour plus d'informations, consultez le fichier LICENSE.