# Cahier de charges du projet de données Cumbia


Ce projet consiste à créer une application de véhicules partagés. Nous allons réaliser un modèle de données simplifié où la partie la plus importante est la recherche et la réservation d'une voiture par un client. 

Notre système **Cumbia** possède de nombreuses stations, et chacune d'elles dispose de plusieurs véhicules. Les clients utilisent une application ou un site web pour réserver une voiture d'un certain type dans une station spécifique pendant une période de temps fixe (jour, heure de début, heure de fin). 

Le client effectue une recherche selon ses besoins et l'application lui indique si la réservation est possible. Souvent, des indisponibilités surviennent car la voiture choisie n'est pas disponible à la station sélectionnée durant la période choisie. 

Dans le cas d'indisponibilité, une application réele proposerai une liste de toutes les combinaisons possibles proches de la demande de le client (proposer une autre station pour le type de voiture et horaire choisi, proposer un autre horaire pour le type et la station choisie, etc...).

Dans notre projet, en raison des contraintes de temps, nous nous limiterons à montrer la disponibilité des voitures dans la station pour n'importe quel horaire et type de voiture (le formateur peut choisir un autre critère s'il le veut). 

Une fois que le client a trouvé ce qu'il lui convient, il acceptera la réservation et celle-ci sera enregistrée dans le système. 

Dans le système réel, le client paie en fonction des heures réservées et du nombre de kilomètres parcourus, ainsi que du type de contrat et du type de véhicule reservé. Pour simplifier le système on pourrait fixer un prix par heure fixe pour chaque voiture et stocker le prix de la reservation dans la classe Reservation (pour avoir un historique au cas où le prix par heure d'une voiture change).

C'est au formateur de choisir s'il veut implementer ou pas cette fonctionnalité.

## Informations à stocker

Dans ce projet, nous ne conserverons que les données nécessaires au fonctionnement du système : 

**Clients** (nom, email, mot de passe) 

**Réservations** (date de début, date de fin, heure de début, heure de fin prévue, heure de fin réelle, prix final) 

**Stations** (nom, adresse) 

**Véhicules** (identifiant, type, kilomètres parcourus)

Dans **Cumbia**, les dommages de chaque véhicule sont également enregistrés, signalés par le client qui réserve avant de pouvoir démarrer la voiture.

    Exemple: vous louez une voiture et il manque un rétroviseur à votre prend la voiture. Vous devez appeler Cumbia et signaler cette situation 
 
Ce système est simplifié mais constitue un bon entraînement pour un projet réel. Une réservation concerne un seul véhicule dans une station donnée et sur un intervalle de temps donné. Une station contient plusieurs véhicules et chaque véhicule est associé uniquement à une station (à la fin de la réservation, le client doit le retourner à sa station et non à une autre). Pour chaque voiture, une liste de dommages est conservée.

Créez un diagramme de classes pour ces besoins (ou utilisez celui qui est fourni si vous voulez implementer diréctement les fonctionnalités)

**Note oncernant les indisponibilités**: vu qu'une voiture est disponible toujours sauf quand elle est reservée on n'a pas considéré la création d'une class contenant des créneaux horaires.