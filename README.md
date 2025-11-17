🎬 **Anime Watchlist SQL Project**

A fun and interactive SQL project to manage users, anime series, genres, watchlists, and ratings. Perfect for learning database relationships, queries, and constraints in MySQL.



----------------------------------------------------------------------------------------------------------------------------------------------------------------

📁 **Project Structure**

                                                           📂 SQL Project


➡️ 📄 README.md -----------------> (Project overview, instructions, and details.)

🔷 📄 SQL_PROJECT.sql -----------------> (SQL script to create database, tables, and insert sample data.)

🟣 📄 Anime.drawio --------------->  (ER diagram showing table relationships.)

-------------------------------------------------------------------------------------------------------------------------------------------------------------------


🗂️ **Tables \& Descriptions**


                       👤 Users                                                                    🎥 Anime
                 Stores user information                                                       Anime series details
           (first name, last name, email, join date.)                          ( title, genre, episodes, season, studio, release year.)



                                                        🏷️ Genres
                                                         Anime genres
                                               (Action, Romance, Sci-Fi, etc.)


                    
                     
                     📋 Watchlist	                                                                ⭐ Ratings	
(Tracks which anime a user is watching, completed, or planning.)                   ( User ratings and reviews for anime (1-10).)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


**🔗 Database Relationships (ER Diagram)**

Users ➡️ Watchlist

     Relationship Type: One-to-Many
     
     Description: A single User can have multiple entries in their Watchlist.
     
     Foreign Key (FK): The Watchlist table uses UserID as a Foreign Key to reference the Users table.

Users ➡️ Ratings

    Relationship Type: One-to-Many
    
    Description: A single User can provide multiple Ratings (and reviews) for different anime.
    
    Foreign Key (FK): The Ratings table uses UserID as a Foreign Key to reference the Users table.

Anime ➡️ Watchlist

    Relationship Type: One-to-Many
    
    Description: A single Anime title can appear in multiple users' Watchlists.
    
    Foreign Key (FK): The Watchlist table uses AnimeID as a Foreign Key to reference the Anime table.

Anime ➡️ Ratings

    Relationship Type: One-to-Many
    
    Description: A single Anime title can receive multiple Ratings from different users.
    
    Foreign Key (FK): The Ratings table uses AnimeID as a Foreign Key to reference the Anime table.

Genres ➡️ Anime

    Relationship Type: One-to-Many
    
    Description: A single Genre can be associated with multiple Anime titles.
    
    Foreign Key (FK): The Anime table uses GenreID as a Foreign Key to reference the Genres table.

-------------------------------------------------------------------------------------------------------------------------------------------------------------------


**🛠️ SQL Features \& Constraints**

✅ AUTO\_INCREMENT primary keys

✅ FOREIGN KEY relationships

✅ ENUM for watchlist status: Watching, Completed, Plan to Watch

✅ CHECK constraint for ratings (1-10)


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


**💻 Sample Data \& Queries**

View all records

^^  SELECT * FROM Users;

^^ SELECT * FROM Anime;

^^ SELECT * FROM Ratings;

^^ SELECT * FROM Watchlist;


-------------------------------------------------------------------------------------------------------------------------------------------------------------------


**🧠Example Queries**


**Find all anime a user is watching:**

--------> SELECT u.FirstName, u.LastName, a.Title, w.Status

          FROM Watchlist w

          JOIN Users u ON w.UserID = u.UserID

          JOIN Anime a ON w.AnimeID = a.AnimeID

          WHERE w.Status = 'Watching';



**Top-rated anime:**

--------> SELECT a.Title, AVG(r.Rating) AS AvgRating

          FROM Ratings r

          JOIN Anime a ON r.AnimeID = a.AnimeID

          GROUP BY a.Title

          ORDER BY AvgRating DESC;


-------------------------------------------------------------------------------------------------------------------------------------------------------------------

**⚡How to Run**


-----------> Clone the repository:  git clone <your-repo-url>

---------->  Open MySQL Workbench

---------->  Run the animewatchlist.sql file to create the database, tables, and insert sample data

---------->  Explore the data using the sample queries and create your own

-------------------------------------------------------------------------------------------------------------------------------------------------------------------
