# Devoir2-
Devoir n°2
Microfinance : Identifiant Client Unique & API d’Interopérabilité

1️⃣ Situation actuelle – État existant
L’institution de microfinance dispose de plusieurs systèmes indépendants : un système d’ouverture de comptes, un système de gestion des crédits, un système de recouvrement et un outil de reporting. Chaque système gère ses propres données clients et attribue son propre identifiant client, sans mécanisme de synchronisation ou de communication standardisée. Les données clients sont donc stockées dans plusieurs bases différentes, principalement dans des systèmes opérationnels, tandis que l’outil de reporting joue un rôle décisionnel en consolidant des données parfois incohérentes. Un même client peut avoir plusieurs identifiants différents selon les systèmes, et les échanges entre applications sont inexistants ou manuels.

2️⃣ Problèmes liés à l’absence d’identifiant client unique
•	Création de doublons clients dans plusieurs systèmes
•	Incohérences de données (nom, date de naissance, agence différente selon le SI)
•	Mauvais suivi des crédits et du risque client
•	Difficulté à avoir une vision globale du client
•	Reporting peu fiable et indicateurs erronés
•	Risques de non-conformité réglementaire (KYC, AML)
•	Augmentation des erreurs opérationnelles et du travail manuel

3️⃣ Identification des Master Data concernées
Donnée	Pourquoi c’est une Master Data
Identifiant client unique	Clé de référence commune à tous les systèmes
Nom et prénom	Identification officielle du client
Date de naissance	Vérification d’identité et conformité réglementaire
Numéro de pièce d’identité	KYC et lutte contre la fraude
Type de client	Segmentation et règles métiers
Agence de rattachement	Pilotage opérationnel et reporting
Statut du client	Suivi du cycle de vie client
Ces données doivent être partagées, cohérentes et utilisées par tous les systèmes.

4️⃣ Définition de la Single Source of Truth (SSOT)
La Single Source of Truth client est un référentiel client central dans lequel l’identité du client est créée, validée et maintenue. Ce référentiel est la seule source officielle pour les données clients. Seuls des acteurs autorisés (par exemple le système d’ouverture de comptes ou un service central de gestion client) ont le droit de créer ou modifier un client. Les autres systèmes consomment ces données sans jamais les recréer localement.

5️⃣ Solution d’harmonisation proposée (principe)
🔁 Principe général
Mettre en place un identifiant client unique, partagé par tous les systèmes, via une API centrale d’interopérabilité.

 Étapes logiques
1️⃣ Le client est créé une seule fois dans le référentiel client (SSOT)
2️⃣ Un identifiant client unique est généré
3️⃣ Les systèmes (crédit, recouvrement, reporting) consomment l’API pour accéder aux données client
4️⃣ Les règles de gestion garantissent l’unicité, la qualité et la mise à jour contrôlée des données




•	Schéma logique (simplifié) :


[ Référentiel Client - SSOT ]
            ↓ API
--------------------------------
| Crédit | Recouvrement | Reporting |


6️⃣ Rôle de l’API d’interopérabilité
L’API d’interopérabilité sert de point d’accès unique aux informations clients. Elle permet à tous les systèmes d’utiliser les mêmes données de référence, en temps réel, sans recréer de clients ni dupliquer les informations. Elle évite les doublons, les incohérences et les échanges manuels de fichiers, tout en garantissant une communication standardisée entre les systèmes.

7️⃣ Bénéfices de la solution
•	Vision client 360°
•	Données fiables et cohérentes
•	Réduction des doublons et erreurs
•	Meilleur pilotage des crédits et des risques
•	Reporting fiable et consolidé
•	Conformité réglementaire renforcée
•	Gain de temps opérationnel
•	Meilleure prise de décision stratégique






 
