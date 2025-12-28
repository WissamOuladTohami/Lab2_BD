### Livrables :

- *Script SQL lab2_schema.sql contenant toutes les commandes DDL et les index.* **(En-Dessus)**
- *Diagramme ER en image (PNG).* **(En-Dessous)**
- *Rapport succinct (220 mots) expliquant l’intérêt de chaque contrainte pour la cohérence et la prévention des anomalies.* **(En-Dessous)**

---

### Intérêt des contraintes pour la cohérence et la prévention des anomalies :

Les contraintes définies dans la base de données jouent un rôle essentiel dans la garantie de la cohérence, de la fiabilité et de la qualité des données au sein du système de gestion de la bibliothèque.

Les clés primaires assurent l’unicité de chaque enregistrement. Elles empêchent l’existence de doublons et permettent d’identifier de manière fiable chaque auteur, abonné, ouvrage ou emprunt. Dans le cas de la table emprunt, l’utilisation d’une clé primaire composée garantit qu’un même ouvrage ne peut pas être emprunté plusieurs fois par le même abonné à la même date, évitant ainsi des incohérences logiques.

Les clés étrangères assurent l’intégrité référentielle entre les tables. Elles empêchent, par exemple, l’enregistrement d’un emprunt pour un abonné ou un ouvrage inexistant. Les actions associées aux suppressions renforcent cette cohérence : ON DELETE RESTRICT empêche la suppression d’un ouvrage encore emprunté, tandis que ON DELETE CASCADE permet de supprimer automatiquement les ouvrages d’un auteur supprimé, évitant ainsi des données orphelines.

Les contraintes NOT NULL garantissent la présence des informations indispensables, comme la date de début d’un emprunt. À l’inverse, l’optionnalité de la date de fin permet de représenter correctement un emprunt en cours.

Enfin, la contrainte CHECK sur les dates empêche des anomalies temporelles, telles qu’une date de retour antérieure à la date d’emprunt. Les index améliorent les performances des requêtes fréquentes sans altérer la cohérence des données.

Ainsi, l’ensemble de ces contraintes constitue un mécanisme fondamental de prévention des erreurs et d’assurance de la qualité du système.

---

### Le Modèle Conceptuel Des Données : 

<img width="940" height="602" alt="MCD" src="https://github.com/user-attachments/assets/452fa014-63f1-419a-b053-45a4dec06b4c" />
