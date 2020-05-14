# BlogPostApi
Rest API NetCore Mysql


CREATE SCHEMA blog;
USE blog;

CREATE TABLE IF NOT EXISTS `BlogPost` (
  Id INT NOT NULL AUTO_INCREMENT,
  Content LONGTEXT CHARSET utf8mb4,
  Title LONGTEXT CHARSET utf8mb4,
  PRIMARY KEY (`Id`)
) ENGINE=InnoDB;



The following API Endpoints should work. Note to set Content-Type: application/json headers on POST and PUT methods.

POST https://localhost:5001/api/blog
{ "Title": "One", "Content": "First Blog Post!" }

POST https://localhost:5001/api/blog
{ "Title": "Two", "Content": "Second Blog Post!" }

POST https://localhost:5001/api/blog
{ "Title": "Three", "Content": "Third Blog Post!" }

GET https://localhost:5001/api/blog
// Output:
[
    { "id": 3, "title": "Three", "content": "Third Blog Post!" },
    { "id": 2, "title": "Two", "content": "Second Blog Post!" },
    { "id": 1, "title": "One", "content": "First Blog Post!"}
]

DELETE https://localhost:5001/api/blog/1
// blog post 1 is gone

PUT https://localhost:5001/api/blog/2
{ "Title": "Two", "Content": "Second Blog Post Revised" }

GET https://localhost:5001/api/blog
// Output:
[
    { "id": 3, "title": "Three", "content": "Third Blog Post!" },
    { "id": 2, "title": "Two", "content": "Second Blog Post Revised" },
]

DELETE https://localhost:5001/api/blog
// all blog posts are gone

GET https://localhost:5001/api/blog
// Output:
