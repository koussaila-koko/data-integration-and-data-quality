# data-integration-and-data-quality
Scénario
Le scénario choisi est basé sur la base de données du site IMDb https ://www.imdb.com/interfaces/ ainsi
que sur les films et séries disponibles sur Netflix, nous souhaitons créer une nouvelle base qui peut regrouper
tous les films qui ne sont pas disponibles sur Netflix et répondre aux besoins des utilisateurs.
2.1 Les Sources
— Source 1 :
— Acteurs.csv(nconst, primaryName, birthYear, deathYear ,#knownForTitles, email, age).
— FilmSource1.csv(tconst, titleType, originalTitle, isAdult, startYear, endYear, runtimeMinutes,
genres).
— NoteFilm.xml(#tconst, averagerating, numVotes).
— Source 2 :
— FilmNetflix.json(show_id, type, title, director, cast, country, date_added, release_year, rating,
duration, listed_in).
— Source 3
— FilmSource3.csv(tconst, titleType, primaryTitle, isAdult, startYear, endYear, runtTimeSecondes,
genres).
2.2 Objectif
L’objectif principal est d’avoir un catalogue de films non disponibles sur Netflix, ainsi que plusieurs autres
possibilités :
— Rechercher des films bien notés.
— Trouver les films où un acteur particulier a joué.
— Rechercher tous les films sortis en une année donnée.
— Rechercher des films par genre.
2.3 Les Cibles
— Film(IdFilm, Title, Annee, runtimeMin, Note).
— Acteur(IdActeur, Nom, BirthYear, Age, Email).
— Genres(NomGenre).
— Posseder(#NomGenre,#IdFilm).
— Jouer(#IdFilm, #IdActeur).
Facteurs de qualité
3.1 Conformité à un format, une codification
1. Niveau : Colonne email.
2. Source : Fichier Acteurs de la source 1.
3. Métrique : Le taux des adresses mail fausses dans la colonne.
3.1.1 Méthode de détection
Certains champs ne respectent pas le format standard d’une adresse email donc on utilise le tExtractRegexFields
pour les détecter à l’aide de l’expression régulière suivante :
"[a 􀀀 zA 􀀀 Z][a 􀀀 zA 􀀀 Z0 􀀀 9 􀀀 _:] + @[a 􀀀 z] + :[a 􀀀 z]":
On stocke dans la table Facteur_Qualite le pourcentage des adresses email conformes.
3.2 Processus d’amélioration 
....
....
la suite est dans le rapport 
