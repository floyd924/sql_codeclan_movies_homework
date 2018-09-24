# SQL Homework

The local cinema are having a Marvel Movie Marathon! They have asked you to help maintain their database of movies with times and attendees.

## To access the database:

First, create a database called 'marvel'


# terminal
createdb marvel


Next, run the provided SQL script to populate your database:


# terminal
psql -d marvel -f marvel.sql


Use the supplied data as the source of data to answer the questions. Copy the SQL command you have used to get the answer, and paste it below the question, along with the result they gave.









## Questions

1.  Return ALL the data in the 'movies' table.
SELECT * FROM movies
returned

1	Iron Man	2008	15:35
2	The Incredible Hulk	2008	22:05
3	Iron Man 2	2010	18:00
4	Thor	2011	21:20
5	Captain America: The First Avenger	2011	13:10
6	Avengers Assemble	2012	14:30
7	Iron Man 3	2013	21:55
8	Thor: The Dark World	2013	15:20
9	Batman Begins	2005	20:30
10	Captain America: The Winter Soldier	2014	21:10
11	Guardians of the Galaxy	2014	16:20
12	Avengers: Age of Ultron	2015	23:00
13	Ant-Man	2015	13:25
14	Captain America: Civil War	2016	14:45
15	Doctor Strange	2016	22:40
16	Guardians of the Galaxy 2	2017	22:00
17	Spider-Man: Homecoming	2017	18:10
18	Thor: Ragnarok	2017	19:35
19	Black Panther	2018	22:20




2.  Return ONLY the name column from the 'people' table

SELECT name FROM people;

Ana Martinez
Andrew Carracher
Caroline Graves
Genna-Lee Walsh
Graham Stein
Iain Floyd
Iona Wright
Jackie Farr
Jennifer Proctor
Jordan Raitt
Katherine Jeffree
Kris McElhinney
Michael Griffin
Monica Mateiu
Nathan Atkinson
Nyalls Hemingway
Oksana Richards
Rana Akbar
Tavy Fraser
Thomas Gracie
Xavier Godard
Kith Douglas








3.  Oops! Someone at CodeClan spelled Keith's name wrong! Change it to reflect the proper spelling.

UPDATE people
SET name = 'Keith Douglas'
WHERE id = 22

UPDATE 1

#Equally I seem to be able to use this for the same effect:
UPDATE people
SET name = 'Keith Douglas'
WHERE name = 'Kith Douglas'



4.  Return ONLY your name from the 'people' table.

SELECT name FROM people
WHERE name = 'Iain Floyd'

Iain Floyd




5.  The cinema is showing 'Batman Begins', but Batman is DC, not Marvel! Delete the entry from the 'movies' table.

DELETE FROM movies
WHERE id = 9

DELETE 1



6.  Create a new entry in the 'people' table with the name of one of the instructors.

INSERT INTO people(name)
VALUES('Pawel Nedved');
# Pawel I'm aware you never played for Juventus but I missed your last name
INSERT 0 1


7.  Pawel has decided to hijack our movie evening, Remove him from the table of people.

DELETE FROM people
WHERE name = 'Pawel Nedved'
DELETE 1

8.  The cinema has just heard that they will be holding an exclusive midnight showing of 'Avengers: Infinity War'!! Create a new entry in the 'movies' table to reflect this.

INSERT INTO movies(title, year, show_time)
VALUES('Avengers: Infinity War', 2018, '00:00');

INSERT 0 1

9.  The cinema would also like to make the Guardians movies a back to back feature. Find out the show time of "Guardians of the Galaxy" and set the show time of "Guardians of the Galaxy 2" to start two hours later.

SELECT show_time FROM movies
WHERE title = 'Guardians of the Galaxy'
16:20

SELECT show_time FROM movies
WHERE title = 'Guardians of the Galaxy 2'
22:00

UPDATE movies
SET show_time = '18:20'
WHERE title = 'Guardians of the Galaxy 2'
UPDATE 1

#could also have done steps 2 and 3 using ID instead of title

#iain remember it seems like you can add multiple parameters to see certain columns
SELECT year, show_time FROM movies






## Extension

1.  Delete multiple entries from your table in a single command.
#i can delete things that share a value such as '2017'. What about deleting several different things by id?

DELETE from movies
WHERE year = 2017

DELETE 3


2. Select all the movies ordered by year in descending order

SELECT * FROM movies
ORDER by year DESC

20	Avengers: Infinity War	2018	00:00
19	Black Panther	2018	22:20
15	Doctor Strange	2016	22:40
14	Captain America: Civil War	2016	14:45
12	Avengers: Age of Ultron	2015	23:00
13	Ant-Man	2015	13:25
10	Captain America: The Winter Soldier	2014	21:10
11	Guardians of the Galaxy	2014	16:20
8	Thor: The Dark World	2013	15:20
7	Iron Man 3	2013	21:55
6	Avengers Assemble	2012	14:30
5	Captain America: The First Avenger	2011	13:10
4	Thor	2011	21:20
3	Iron Man 2	2010	18:00
2	The Incredible Hulk	2008	22:05
1	Iron Man	2008	15:35











#
