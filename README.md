# Web Scraper for transfermarkt.co.uk
This web scraper scrapes data from www.transfermarkt.co.uk. 
The program gathers data about footballers for a given league, based on the URL the user enters. Data includes: name, age, height, position, preferred foot, club, country and player photo. 
Then, the program stores the data within a MongoDB database.

The purpose of the web scraper, was to bypass issues with gathering data from API's. Whilst looking for a suitable API for my Footballer Guessing Game, Footle, I discovered that many API's had low rate limits, and many cost money to use. To combat this, I decided to create a web scraper which gathered data from a reliable website with up to date information about players, whilst also covering a vast amount of leagues.

The program takes advantage of jsDOM, a JavaScript library used to take HTML files from websites, and allow them to be accessed and manipulated using Document Object Model manipulation.
Beautiful Soup is an alternative library for web scraping, but as the code was written in JavaScript, I opted to go with jsDOM.

Whilst coding this project, many obstacles had to be overcome. 
A major challenge was handling errors within the program. As there are many requests made, it was important that 1 bad request for a player would not result in the whole program crashing. To solve this, default player stats were added, as well as try and except statements to ensure the smooth running of the code.

## Executing the code
Once the code has been added to Visual Studio, you will need to alter the code in places. First of all, you need to change the ```const uri``` variable. This is on line 6 of the crawl.js file
You *may* also change the database name and collection name within the run function on line 30 of crawl.js This is not mandatory, however.

Once complete, you will need to access a new terminal. This can be done with *CRTL-SHIFT-'*
From here, ensure you are in the correct directory. 
Then, type ```npm start LINK```, where ```LINK``` is a link to the ```www.transfermarkt.co.uk``` league.
For example, running ```npm start https://www.transfermarkt.co.uk/premier-league/startseite/wettbewerb/GB1``` will scrape ALL data from the Premier League teams.
Running ```npm start https://www.transfermarkt.co.uk/serie-a/startseite/wettbewerb/IT1``` will scrape ALL data from Serie A teams.

Enjoy!
