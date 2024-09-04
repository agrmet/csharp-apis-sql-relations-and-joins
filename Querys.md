# Core
## Show the title and director name for all films
```sql
SELECT films.title, directors.name
FROM films
INNER JOIN directors ON films.directorid = directors.id;
```
## Show the title, director and star name for all films
```sql
SELECT films.title, directors.name, stars.name
FROM films
INNER JOIN directors ON films.directorid = directors.id
INNER JOIN stars ON films.starid = stars.id;
```
## Show the title of films where the director is from the USA
```sql
SELECT films.title
FROM films
INNER JOIN directors ON directors.id = films.directorid
WHERE directors.co LIKE 'USA';
```
## Show only those films where the writer and the director are the same person
```sql
SELECT films.title, directors.name, writers.name
FROM films
INNER JOIN directors ON directors.id = films.directorid
INNER JOIN writers ON writers.id = films.writerid
WHERE writers.name LIKE directors.name;
```
## Show directors and film titles for films with a score of 8 or higher
```sql
SELECT films.title, directors.name, films.score
FROM films
INNER JOIN directors ON directors.id = films.directorid
WHERE films.score >= 8;
```
## Make at least 5 more queries to demonstrate your understanding of joins, and other relationships between tables.
### Lists titles and writer emails for films with a score of 9 or higher.
```sql
SELECT films.title, writers.email
FROM films
INNER JOIN writers ON films.writerid = writers.id
WHERE films.score >= 9;
```` 
### Provides the film titles, writer emails, and director's country.
```sql
SELECT films.title, writers.email, directors.co AS director_country
FROM films
INNER JOIN writers ON films.writerid = writers.id
INNER JOIN directors ON films.directorid = directors.id;
```` 
### Retrieves titles of films where the star's name is "Mark Hamill".
```sql
SELECT films.title
FROM films
INNER JOIN stars ON films.starid = stars.id
WHERE stars.name LIKE '%Mark Hamil%';
```` 
### Finds unique star names appearing in films directed by "James Cameron".
```sql
SELECT DISTINCT stars.name
FROM films
INNER JOIN directors ON films.directorid = directors.id
INNER JOIN stars ON films.starid = stars.id
WHERE directors.name LIKE '%James Cameron%';
```` 
### Displays film titles, director names, and writer emails specifically for "Historical" genre films.
```sql
SELECT films.title, directors.name AS director, writers.email AS writer_contact
FROM films
INNER JOIN directors ON films.directorid = directors.id
INNER JOIN writers ON films.writerid = writers.id
WHERE films.genre LIKE '%Historical%';
```` 

# Extension 1

# Extension 2