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

--What is the selection of wine that has a rating higher than 7.0 that is not in Aisle 1?
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



# Project 3: Create a playlist

REATE TABLE artists (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    country TEXT,
    genre TEXT);

INSERT INTO artists (name, country, genre)
    VALUES ("Taylor Swift", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Led Zeppelin", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("ABBA", "Sweden", "Disco");
INSERT INTO artists (name, country, genre)
    VALUES ("Queen", "UK", "Rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Celine Dion", "Canada", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Meatloaf", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Garth Brooks", "US", "Country");
INSERT INTO artists (name, country, genre)
    VALUES ("Shania Twain", "Canada", "Country");
INSERT INTO artists (name, country, genre)
    VALUES ("Rihanna", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Guns N' Roses", "US", "Hard rock");
INSERT INTO artists (name, country, genre)
    VALUES ("Gloria Estefan", "US", "Pop");
INSERT INTO artists (name, country, genre)
    VALUES ("Bob Marley", "Jamaica", "Reggae");

CREATE TABLE songs (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    artist TEXT,
    title TEXT);

INSERT INTO songs (artist, title)
    VALUES ("Taylor Swift", "Shake it off");
INSERT INTO songs (artist, title)
    VALUES ("Rihanna", "Stay");
INSERT INTO songs (artist, title)
    VALUES ("Celine Dion", "My heart will go on");
INSERT INTO songs (artist, title)
    VALUES ("Celine Dion", "A new day has come");
INSERT INTO songs (artist, title)
    VALUES ("Shania Twain", "Party for two");
INSERT INTO songs (artist, title)
    VALUES ("Gloria Estefan", "Conga");
INSERT INTO songs (artist, title)
    VALUES ("Led Zeppelin", "Stairway to heaven");
INSERT INTO songs (artist, title)
    VALUES ("ABBA", "Mamma mia");
INSERT INTO songs (artist, title)
    VALUES ("Queen", "Bicycle Race");
INSERT INTO songs (artist, title)
    VALUES ("Queen", "Bohemian Rhapsody");
INSERT INTO songs (artist, title)
    VALUES ("Guns N' Roses", "Don't cry");
    
--What are the title of the songs from the band Queen?
SELECT title FROM SONGS WHERE artist= 'Queen';

--What are the names of the artists in the Pop genre? 
SELECT name FROM ARTISTS WHERE genre= "Pop";
SELECT title FROM songs WHERE artist IN (
    SELECT name FROM artists WHERE genre= 'Pop');
   
   
   
# Project 4: The Wordiest Author

CREATE TABLE books (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    author TEXT,
    title TEXT,
    words INTEGER);
    
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Philosopher's Stone", 79944);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Chamber of Secrets", 85141);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Prisoner of Azkaban", 107253);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Goblet of Fire", 190637);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Order of the Phoenix", 257045);
    

INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Half-Blood Prince", 168923);
INSERT INTO books (author, title, words)
    VALUES ("J.K. Rowling", "Harry Potter and the Deathly Hallows", 197651);

INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Twilight", 118501);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "New Moon", 132807);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Eclipse", 147930);
INSERT INTO books (author, title, words)
    VALUES ("Stephenie Meyer", "Breaking Dawn", 192196);
    
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "The Hobbit", 95022);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Fellowship of the Ring", 177227);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Two Towers", 143436);
INSERT INTO books (author, title, words)
    VALUES ("J.R.R. Tolkien", "Return of the King", 134462);
 
 
 --Who are the author(s) whose sum of words from all their written books are greater than 1000000 words?
 Select author, Sum(words) AS total_words FROM books
 GROUP BY author
 HAVING total_words > 1000000;
 
 --Who are the author's whose average words from their books are greater than 150000 words?
 Select author, AVG(words) AS avg_words FROM books
 GROUP BY author
 HAVING avg_words> 150000;
 
 
 
 # Project 5:  Gradebook Database****** COME BACK TO IT
CREATE TABLE student_grades (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT,
    number_grade INTEGER,
    fraction_completed REAL);
    
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winston", 90, 0.805);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winnefer", 95, 0.901);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winsteen", 85, 0.906);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Wincifer", 66, 0.7054);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winster", 76, 0.5013);
INSERT INTO student_grades (name, number_grade, fraction_completed)
    VALUES ("Winstonia", 82, 0.9045);
    
SELECT name, number_grade, ROUND (fraction_completed*100) AS percent_completed FROM student_grades;SELECT COUNT (*),

  CASE 

  WHEN number_grade > 90 THEN "A"

  WHEN number_grade > 80 THEN "B"

  WHEN number_grade > 70 THEN "C"

  ELSE "F"

  END as "letter_grade" FROM student_grades

  GROUP BY "letter_grade";



# Project 6: Donut Log

CREATE TABLE winstons_donut_logs (
    id TEXT PRIMARY KEY,
    status TEXT,
    years_old INTEGER,
    donuts_eaten INTEGER,
    reason TEXT
    );
INSERT INTO winstons_donut_logs VALUES (0, "new born winston lvl 0", 0, 0, "");
INSERT INTO winstons_donut_logs VALUES (1, "baby winston lvl1", 1, 10, "(Gummed)");
INSERT INTO winstons_donut_logs VALUES (2, "baby winston lvl2", 2, 40, "(Gummed)");
INSERT INTO winstons_donut_logs VALUES (3, "baby winston lvl3", 3, 50, "(Gummed)");
INSERT INTO winstons_donut_logs VALUES (4, "toddler winston lvl1", 4, 300, "");
INSERT INTO winstons_donut_logs VALUES (5, "toddler winston lvl2", 5, 400, "");
INSERT INTO winstons_donut_logs VALUES (6, "kid winston lvl1", 6, 1200, "");
INSERT INTO winstons_donut_logs VALUES (7, "kid winston lvl2", 7, 1000, "");
INSERT INTO winstons_donut_logs VALUES (8, "kid winston lvl3", 8, 1000, "");
INSERT INTO winstons_donut_logs VALUES (9, "kid winston lvl4", 9, 1000, "");
INSERT INTO winstons_donut_logs VALUES (10, "winstween lvl1", 10, 1500, "");/** tween means someone between 10 and 12 so I did winstween- tween not teen**/
INSERT INTO winstons_donut_logs VALUES (11, "winstween lvl2", 11, 500, "Braces");
INSERT INTO winstons_donut_logs VALUES (12, "winstween lvl3", 12, 300, "Braces");
INSERT INTO winstons_donut_logs VALUES (13, "winsteen lvl1", 13, 400, "Braces");
INSERT INTO winstons_donut_logs VALUES (14, "winsteen lvl2", 14, 1300, "No Braces");
INSERT INTO winstons_donut_logs VALUES (15, "winsteen lvl3", 15, 2000, "");
INSERT INTO winstons_donut_logs VALUES (16, "winsteen lvl4", 16, 2000, "");
INSERT INTO winstons_donut_logs VALUES (17, "winsteen lvl5", 17, 2000, "");
INSERT INTO winstons_donut_logs VALUES (18, "winsteen lvl6", 18, 2000, "");
INSERT INTO winstons_donut_logs VALUES (19, "winsteen lvl7", 19, 2000, "");
INSERT INTO winstons_donut_logs VALUES (20, "young adult winston lvl1", 20, 2000, "");
INSERT INTO winstons_donut_logs VALUES (21, "young adult winston lvl2", 21, 2500, "");
INSERT INTO winstons_donut_logs VALUES (22, "young adult winston lvl3", 22, 2500, "");
INSERT INTO winstons_donut_logs VALUES (23, "young adult winston lvl4", 23, 2500, "");
INSERT INTO winstons_donut_logs VALUES (24, "young adult winston lvl5", 24, 2500, "");
INSERT INTO winstons_donut_logs VALUES (25, "young adult winston lvl6", 25, 2500, "");
INSERT INTO winstons_donut_logs VALUES (26, "young adult winston lvl7", 26, 2500, "");
INSERT INTO winstons_donut_logs VALUES (27, "young adult winston lvl8", 27, 2500, "");
INSERT INTO winstons_donut_logs VALUES (28, "young adult winston lvl9", 28, 2500, "");
INSERT INTO winstons_donut_logs VALUES (29, "young adult winston lvl10", 29, 2500, "");
INSERT INTO winstons_donut_logs VALUES (30, "mature adult winston lvl1", 30, 2500, "");
INSERT INTO winstons_donut_logs VALUES (31, "mature adult winston lvl2", 31, 2500, "");
INSERT INTO winstons_donut_logs VALUES (32, "mature adult winston lvl3", 32, 2500, "");
INSERT INTO winstons_donut_logs VALUES (33, "mature adult winston lvl4", 33, 2500, "");
INSERT INTO winstons_donut_logs VALUES (34, "mature adult winston lvl5", 34, 2500, "");
INSERT INTO winstons_donut_logs VALUES (35, "mature adult winston lvl6", 35, 1500, "Healthier Eating");
INSERT INTO winstons_donut_logs VALUES (36, "mature adult winston lvl7", 36, 1500, "Healthier Eating");
INSERT INTO winstons_donut_logs VALUES (37, "mature adult winston lvl8", 37, 1500, "Healthier Eating");
INSERT INTO winstons_donut_logs VALUES (38, "mature adult winston lvl9", 38, 1500, "Healthier Eating");
INSERT INTO winstons_donut_logs VALUES (39, "mature adult winston lvl10", 39, 1500, "Healthier Eating");
INSERT INTO winstons_donut_logs VALUES (40, "middle-aged adult winston lvl1", 40, 2500, "Non-healthy eating");
INSERT INTO winstons_donut_logs VALUES (41, "middle-aged adult winston lvl2", 41, 2500, "");
INSERT INTO winstons_donut_logs VALUES (42, "middle-aged adult winston lvl3", 42, 2500, "");
INSERT INTO winstons_donut_logs VALUES (43, "middle-aged adult winston lvl4", 43, 2500, "");
INSERT INTO winstons_donut_logs VALUES (44, "middle-aged adult winston lvl5", 44, 300, "Diet");
INSERT INTO winstons_donut_logs VALUES (45, "middle-aged adult winston lvl6", 45, 200, "Diet");
INSERT INTO winstons_donut_logs VALUES (46, "middle-aged adult winston lvl7", 46, 150, "Diet");
INSERT INTO winstons_donut_logs VALUES (47, "middle-aged adult winston lvl8", 47, 150, "Diet");
INSERT INTO winstons_donut_logs VALUES (48, "middle-aged adult winston lvl9", 48, 150, "Diet");
INSERT INTO winstons_donut_logs VALUES (49, "middle-aged adult winston lvl10", 49, 150, "Diet");
INSERT INTO winstons_donut_logs VALUES (50, "old-ish adult winston lvl1", 50, 2500, "No diet");
INSERT INTO winstons_donut_logs VALUES (51, "old-ish adult winston lvl2", 51, 2500, "");
INSERT INTO winstons_donut_logs VALUES (52, "old-ish adult winston lvl3", 52, 2500, "");
INSERT INTO winstons_donut_logs VALUES (53, "old-ish adult winston lvl4", 53, 1436, "Current age");

--What is the average age of Winston's Donut consumption?
--What is the maximum age of Winston's Donut consumption?
--What is the minimum age of Winston's Donut consumption?
SELECT * FROM winstons_donut_logs;
SELECT avg(years_old) AS average_age FROM winstons_donut_logs;
SELECT MAX(years_old) as maxmimum_age FROM winstons_donut_logs;
SELECT MIN(years_old) AS minimum_age FROM winstons_donut_logs;

--How to select years of Winston's donut logs between the age of 2 and 47 years hold
SELECT years_old AS age FROM winstons_donut_logs
WHERE age > 2 AND years_old < 47;

----How to select number of donuts eaten of Winston's donut logs between the age of 2 and 47 years hold
SELECT donuts_eaten FROM winstons_donut_logs
WHERE years_old > 2 OR years_old < 47;

--How to group the ages (years) in which Winston's donut consumption is over 1000?
SELECT years_old
FROM winstons_donut_logs
GROUP BY years_old
HAVING MAX(ID) > 1000;

--How to filter the years 1-19 grouped by status
SELECT years_old
FROM winstons_donut_logs
WHERE years_old < 20
GROUP BY status;
 

    
