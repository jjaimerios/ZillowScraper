# ZillowScraper
Hacky scraper to get available property results from Zillow.
This was completed as a practicum project for Regis class MSDS-692.

Files consist of:
* installPyPackages.sh.txt
  * Linux bash shell script that can be executed command line to install needed Python packages
* createDirs.sh.txt
  * Linux bash shell script that can be executed command line to create needed data and application directories
* config.props.txt
  * Configuration / property file
  * I should have utilized this a lot more - but just wanted to demonstrate use of a property file
  * Property as in application variables - not real estate (didn't want to confuse anyone with this projects subject matter)
* zillowScraper.Step1.py.txt
  * Python script using Beautiful Soup to get raw html for Zillow property search results
* parseZillowHtml.Step2.pl.txt
  * Hacky Perl script reading in the raw html files and pulling out valid property info for each search item returned
    * ...from a big glob of data at the bottom of the search results page hidden within a script tag
* loadToMongo.Step3.py.txt
  * Python script that takes the semi-formatted data output from the Perl script
  * Converts data into a dictionary of dictionaries and loads to MongoDB
  
After running the above scripts - you can open something like MongoDB compass to view/query the data and to generate charts and visualizations. I am not committing anything for that here - but it will be included in the write-up to my professor.

Zillow proved very tricky to scrape. They really go to great lengths to curb bots and scraping and make sure only humans can search thei results. I had to get around captchas, get creative pulling property info and find ways to get all 40 hits per page (most scrapers I saw only return the first 10 hits - if they work at all - as that is all Zillow presents by default - again to make sure only a human can scrape to get results).

If you download this code and try using the scraper - Zillow will catch it and block you. Was very hard getting what results I did. Had to switch locations, IPs, etc - and in the end - still had to settle for Zillow catching on and blocking me before being able to download all the pages of results for a given city.

![image](https://user-images.githubusercontent.com/77909180/222933023-ec678d94-105a-4c9f-b7ca-5d3ce10ef44f.png)


