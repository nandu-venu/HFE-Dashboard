# HFE-Dashboard

The main objective of this project was to help Dr. Radwin, the editor of the Human Factors Journal, to streamline the process of searching for associate editors, editorial board members, and preferred reviewers.

To achieve this, the data provided in the Excel file "Editorial Board.xlsx" was cleaned and transformed using Python libraries such as Pandas and PySQLite. The data was then stored in a SQLite database.

First, the data in the sheet "Associate Editors" was loaded into a Pandas DataFrame called "Current_AE". Similarly, the data in the sheets "Editorial Board" and "Preferred Reviewers" were loaded into DataFrames "Current_EB" and "Current_PR", respectively. The necessary columns were selected from each of these DataFrames and any rows with missing values were removed.

Next, the data in these DataFrames was normalized and stored in the SQLite database. Three tables were created: "User_Data", "Keywords", and "Skill". The "User_Data" table stored personal information about the individuals listed in the Excel file, such as their name, email address, and institution. The "Keywords" table stored a list of keywords and their relationships to each other, such as a keyword being a parent topic of another keyword. The "Skill" table stored the relationships between individuals and keywords, indicating their areas of expertise.

The data in the "Current_AE", "Current_EB", and "Current_PR" DataFrames was then used to populate the "AE", "EB", and "PR" tables, respectively. These tables stored the IDs of the individuals listed in the "User_Data" table who were associate editors, editorial board members, or preferred reviewers.

Finally, a query was written using PySQLite to join the data from the "AE", "EB", and "PR" tables with the data in the "User_Data" and "Keywords" tables. This query produced a DataFrame with the information needed for the Tableau dashboard, such as the names and email addresses of the individuals, their areas of expertise, and their keywords.

The resulting DataFrame was then exported to an Excel file and used to create the Tableau dashboard, which was hosted on the university's web services through WordPress. This dashboard allows Dr. Radwin to easily search for individuals based on their areas of expertise and keywords, making the process of finding the right associate editors, editorial board members, and preferred reviewers more efficient.
