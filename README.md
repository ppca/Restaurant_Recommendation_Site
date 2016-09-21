# Restaurant Recommendation Site (HTML, CSS, JavaScript, MySQL, MongoDB, Apache Tomcat)

This is a website that recommends restaurants to its users using Yelp data. The users can search and like restaurants on the 
site and the site will take these requests, query/update the backend database for relevant info and supply the info to the responses.

This project consists of both frontend (HTML, CSS, JavaScript) code and backend (Java Servlet) code. 

In the frontend JavaScript is used to control the CSS to show and hide different components in the page, and html has all of the text contents and sets the structure of the website. 

In the backend the code provides three endpoint to support the frontend, and for each of the endpoit, they query the databases behind them. This website utilizes both MySQL and MongoDB database as storage for the data fetched from Yelp's API, as well as the changes user posts to the website. 

# Frontend

![Alt Text](https://github.com/ppca/Restaurant_Recommendation_Site/raw/master/pics/homepage.png)

### Main Features

#### NearBy: http://localhost:8080/Dashi/restaurants
This calls the Yelp's api and get the restraunts nearby based on your GPS location, and show them here as well as store them in the mysql database. 

#### My Favorite: http://localhost:8080/Dashi//history
This calls history end point in the backend, which query the history table and get the restaurant that certain user has marked at starred. 

#### Recommendation: http://localhost:8080/Dashi//recommendation
This calls the recommend end point in the backend, which uses a collaborative filtering algorithm to determine which restaurant to based on user's history. 


# Backend

### End points

####SearchRestaurant: http://localhost:8080/Dashi/restaurants
takes the search request from users and show all nearby restaurants the user hasn't visited

####VisitHistory: http://localhost:8080/Dashi//history
take get request from site/history and show all visited restaurants of a user

####RecommendRestaurants: http://localhost:8080/Dashi//recommendation
recommend restaurants based on a user's past activities


# DataBase

This website utilizes two databases, one sql database and one nosql database. 

### MySQL
This database has three tables:
business, user, history

### MongoDB
This database has two tables:
business, user(history is contained in this table to form a denormalized table)

# Connection to Yelp's Api
This part connects to the Yelp's API with a TwoStep OAuth example provided by Yelp, and fetches restaurants bases on a certain location. 
