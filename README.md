##### Scraping Amazon data in itself is already against the e-commerce site's terms of service, and using the data for illicit transactions will not only result in your IP being banned but even in legal action being taken against you

And i did get baneed so i scraped other website ;(

walkthrough project:
setup is pretty simple. Just create a folder and install Beautiful Soup, pandas, and requests. To create a folder and install the libraries, enter the commands given below. I am assuming that you have already installed Python.


Now,  set the base URL of the main page because we'll need that when we construct our URLs for each of the individual products.
Also, we will send a user-agent on every HTTP request, because if you make GET request using requests then by default the user-agent is Python which might get blocked.
So, to override that, we will declare a variable which will store our user-agent.



i will write a script to go through each one of these and create a URL for us. To do that we need to make an HTTP call first. Then i will extract the li element using BeautifulSoup.


Next, get the HTML for the items on this page. Now, inside each of these lists there is a link to the individual product page. i will write a script to scrape all those links from the productlist.



then first i have declared an empty list called productlinks. Then we have used a for loop to reach each productlist element to extract the link. i have used the .get() function to get the value of the href attribute. After extracting the link i will store every link inside the list productlinks. Since we have to create a legit  URL, i have added baseurl to the link.



have to cover all five pages of the website. To do so i will introduce a for loop before making the HTTP call.
This will give us all the links available on the website.



now i can loop through each of these links to extract the product information from each page and then store it in csv.

 im going to analyze the pattern in which the information is displayed on the product page. We will extract the name, price, ratings, and about text.
 
 
 
 things are pretty straightforward. i have started a for loop to iterate over every individual link of productlinks and made an HTTP GET call to every link and then extract the price, name, rating and about text.
 
 
 
 then stored them into csv et voila scraper
 
