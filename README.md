# Start api platform

`docker-compose up -d`

####Open https://localhost in your favorite web browser:

![alt text](https://api-platform.com/static/fd7617555c903bebe52c68d1d39e2e61/d4def/api-platform-2.2-welcome.png)

####Click on the POST operation of the Book resource type, click on "Try it out" and send the following JSON document as request body:

![alt text](https://api-platform.com/static/ca25984c95450f4e5b78a6265adf3658/d4def/api-platform-2.2-bookshop-api.png)

`{
   "isbn": "9781782164104",
   "title": "Persistence in PHP with the Doctrine ORM",
   "description": "This book is designed for PHP developers and architects who want to modernize their skills through better understanding of Persistence and ORM.",
   "author": "Kévin Dunglas",
   "publicationDate": "2013-12-01"
 }`
 
 
 ####Now, add a review for this book using the POST operation for the Review resource:
 `{
      "book": "/books/1",
      "rating": 5,
      "body": "Interesting book!",
      "author": "Kévin",
      "publicationDate": "September 21, 2016"
  }`


####This demo entity isn't useful anymore. Finally, tell Doctrine to sync the database tables structure with our new data model:

`docker-compose exec php bin/console doctrine:schema:update --force`

#### POSTGRES 
       - POSTGRES_DB=api
       - POSTGRES_USER=root
       - POSTGRES_PASSWORD=root

#### Getting Started with API Platform: Hypermedia and GraphQL API, Admin and Progressive Web App
https://api-platform.com/docs/distribution/
