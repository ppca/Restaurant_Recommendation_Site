# Restaurant Recommendation Site

This is a website that recommends restaurants to its users using Yelp data. The users can search and like restaurants on the 
site and the site will take these requests, query/update the backend database for relevant info and supply the info to the responses.

## API

####RpcParser: 
formatting of request and response

####SearchRestaurant: 
takes the search request from users and show all nearby restaurants the user hasn't visited

####VisitHistory:
take get request from site/history and show all visited restaurants of a user

####RecommendRestaurants:
recommend restaurants based on a user's past activities


## db
This is the backend part that connects to a database, MySQLDBConnection and MongoDBConnection both implements DBConnection interface. The key API's to interact with databse are setVisitedRestaurant(), searchRestauran(), getVisited() etc. MySql jdbc driver is utilized so that java can query/update database by passing SQL statements.

## Yelp
This part authorize the server to fetch data using Yelp API. TwoStepOauth is implemented.

## model
the data model of the restaurant object. A restaurant would have location, city, state, name, business_id, stars, categories.
