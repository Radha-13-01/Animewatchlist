🎬 **Anime Watchlist SQL Project**

A fun and interactive SQL project to manage users, anime series, genres, watchlists, and ratings. Perfect for learning database relationships, queries, and constraints in MySQL.



📁 **Project Structure**

📂 SQL\_Project

├─ 📄 README.md           # Project overview, instructions, and details

├─ 📄 SQL PROJECT.sql  # SQL script to create database, tables, and insert data

└─ 📄 Anime.drawio      # ER diagram showing table relationships



🗂️ **Tables \& Descriptions**

🏷️ **Table**	📝 **Description**

👤 Users	Stores user information: first name, last name, email, join date.

🎥 Anime	Anime series details: title, genre, episodes, season, studio, release year.

🏷️ Genres	Anime genres (Action, Romance, Sci-Fi, etc.).

📋 Watchlist	Tracks which anime a user is watching, completed, or planning.

⭐ Ratings	User ratings and reviews for anime (1-10).



**🔗 Database Relationships (ER Diagram)**



Users → Watchlist / Ratings: A user can track multiple anime and rate them.



Anime → Watchlist / Ratings: An anime can appear in multiple users' watchlists and ratings.



Genres → Anime: Each genre can have multiple anime series.



**ER Diagram Preview:**





**🛠️ SQL Features \& Constraints**



✅ AUTO\_INCREMENT primary keys



✅ FOREIGN KEY relationships



✅ ENUM for watchlist status: Watching, Completed, Plan to Watch



✅ CHECK constraint for ratings (1-10)



✅ Sample data: 100 users, 50 anime series, watchlists, and ratings



**💻 Sample Data \& Queries**



View all records



SELECT \* FROM Users;

SELECT \* FROM Anime;

SELECT \* FROM Ratings;

SELECT \* FROM Watchlist;



**🧠Example Queries**



**Find all anime a user is watching:**



SELECT u.FirstName, u.LastName, a.Title, w.Status

FROM Watchlist w

JOIN Users u ON w.UserID = u.UserID

JOIN Anime a ON w.AnimeID = a.AnimeID

WHERE w.Status = 'Watching';





**Top-rated anime:**



SELECT a.Title, AVG(r.Rating) AS AvgRating

FROM Ratings r

JOIN Anime a ON r.AnimeID = a.AnimeID

GROUP BY a.Title

ORDER BY AvgRating DESC;



**⚡How to Run**



Clone the repository:



git clone <your-repo-url>





Open MySQL Workbench



Run the animewatchlist.sql file to create the database, tables, and insert sample data



Explore the data using the sample queries and create your own

