# Karyna Fotre's SQL Portfolio

## Welcome to my SQL portfolio! This code repository contains examples of SQL I've written. Feel free to take a look and reach out to me via email at kafotre@gmail.com if you have any questions.

# Project 1: Create a Wine Store database

Create TABLE wine (id INTEGER PRIMARY KEY, name TEXT, PRICE INTEGER, rating INTEGER, aisle INTEGER);

INSERT INTO wine VALUES (1, "pinot noir1", 20.05 , 7.6, 1);
INSERT INTO wine VALUES (2, "pinot noir2", 45 , 9.3 , 3 );
INSERT INTO wine VALUES (3, "pinot noir3", 33 , 9.0 , 3 );
INSERT INTO wine VALUES (4, "cabernet1", 50 , 8.8, 1);
INSERT INTO wine VALUES (5, "cabernet2", 20 , 6.5, 1);
INSERT INTO wine VALUES (6, "cabernet3", 27 , 5.8, 1);
INSERT INTO wine VALUES (7, "cabernet4", 48 , 9.5, 1);
INSERT INTO wine VALUES (8, "cabernet5", 22, 7.4, 1);
INSERT INTO wine VALUES (9, "pinot grigio1", 22, 7.4, 4);
INSERT INTO wine VALUES (10, "pinot grigio2", 18, 6.7, 4);
INSERT INTO wine VALUES (11, "pinot grigio3", 15, 5.4, 4);
INSERT INTO wine VALUES (12, "pinot grigio4", 20, 7.0, 4);
INSERT INTO wine VALUES (13, "sauvignon blanc1", 20, 8.2, 2);
INSERT INTO wine VALUES (14, "sauvignon blanc2", 15, 8.7, 2);
INSERT INTO wine VALUES (15, "sauvignon blanc3", 27, 8.1, 2);

--What are the 10 best rated wines in the store?
SELECT name, price, rating FROM wine order by rating desc limit 10; 

--What is the selection of wine that has a rating higher than 7.0 that is not in Aisle 1
SELECT * FROM wine WHERE rating >7.0 ORDER BY aisle;
SELECT * FROM wine WHERE aisle>1;


# Project 2: Create a Karaoke Database

CREATE TABLE songs (
    id INTEGER PRIMARY KEY,
    title TEXT,
    artist TEXT,
    mood TEXT,
    duration INTEGER,
    released INTEGER);
    
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("Bohemian Rhapsody", "Queen", "epic", 60, 1975);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("Let it go", "Idina Menzel", "epic", 227, 2013);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("I will survive", "Gloria Gaynor", "epic", 198, 1978);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("Twist and Shout", "The Beatles", "happy", 152, 1963);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("La Bamba", "Ritchie Valens", "happy", 166, 1958);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("I will always love you", "Whitney Houston", "epic", 273, 1992);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("Sweet Caroline", "Neil Diamond", "happy", 201, 1969);
INSERT INTO songs (title, artist, mood, duration, released)
    VALUES ("Call me maybe", "Carly Rae Jepsen", "happy", 193, 2011);
  
--What are the title of the songs?
SELECT title FROM songs;

--What are the title of songs where the mood is epic or released later than the year 1990.
SELECT title FROM songs WHERE mood= "epic" OR released > 1990; 

--What are the title of songs where the mood is epic and released later than the year 1990 and are less than 4 minutes in duration.
SELECT title FROM songs WHERE mood= "epic" AND released > 1990 AND duration < 240; 



# Project 3:
