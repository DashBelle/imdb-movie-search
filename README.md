🎬 Movie Search App
A console-based application for searching movies by multiple parameters with poster display and search history tracking.
📌 Project Overview
This project was built as part of a data analytics training program using a dataset of 100,000+ IMDb records stored in a MySQL database.  
The app allows users to interactively filter movies, view posters, and revisit their search history — all from a Jupyter Notebook interface.
✨ Features
🔍 Multi-parameter search — filter by genre, release year, actor name, minimum IMDb rating, and keywords
🎭 Dynamic SQL query builder — conditions are assembled based on user input only
🖼️ Movie poster display — retrieves and renders the poster image for any selected film
📋 Search history log — all queries are saved to a local database table and can be reviewed as a formatted table
🔄 Interactive loop — users can run multiple searches in one session
---
🗂️ Project Structure
```
Project_movies/
│
├── Project_movies.ipynb          # Main entry point — runs the interactive loop
├── search.py                     # Search logic: collects input, builds and executes SQL query
├── poster.py                     # Retrieves and displays movie poster by film ID
├── history.py                    # Fetches and displays search history from the log table
├── front.py                      # Formats and prints search results as a clean table
├── db_utils.py                   # Database utility functions: connect, query, insert
└── db_config.py                  # Database connection config (local / server)
```
---
🛠️ Tech Stack
Tool	Purpose
Python	Core application logic
pandas	Data handling
MySQL + mysql-connector-python	Database storage and querying
IPython.display	Poster image rendering inside Jupyter
tabulate	Formatted table output for search history
---
⚙️ How It Works
User is prompted to enter search parameters (any combination of genre, year, actor, rating, keywords)
A dynamic `WHERE` clause is built based on non-empty inputs only
The SQL query runs against the MySQL database and returns matching films sorted by IMDb rating (descending)
Results are displayed as a formatted table
User can optionally view the poster of any film by entering its ID
User can optionally review the full history of previous searches
The loop repeats until the user exits
---
💾 Database Schema (simplified)
Table: `movies`
Column	Description
id	Unique film identifier
title	Film title
year	Release year
imdb.rating	IMDb rating
genres	Genre(s)
runtime	Duration in minutes
poster_url	Link to poster image
Table: `queries`
Column	Description
id	Auto-increment log ID
query_text	Logged search parameters as a string
---
🚀 Getting Started
Clone the repository
Install dependencies:
```bash
pip install pandas mysql-connector-python tabulate
```
Configure your database connection in `db_config.py`
Open `Project_movies_Zasenko.ipynb` in Jupyter and run all cells
---
📊 Dataset
Source: IMDb movie database (100,000+ records)
Storage: Remote MySQL server (IT Career Hub training environment)
Access: Server credentials required — not included in this repository for security reasons
Local setup: Configure your own MySQL connection in `db_config.py`
---
👩‍💻 Author
Irina Zasenko — Data Analyst  
LinkedIn · GitHub
Completed as part of the IT Career Hub Data Analytics Program, 2025
