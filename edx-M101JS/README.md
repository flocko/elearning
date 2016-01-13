# M101JS: MongoDB for Node.js Developers

Course from [MongoDB University](https://university.mongodb.com/courses/MongoDB/M101JS/2016_January/syllabus)

### 09.01.2016
- hw1-1, hw1-2, hw1-3 done

### 13.01.2015

#### Multiple selectors in a find() command
    db.movieDetails.find({'rated':'PG-13','year':2013, 'awards.wins': 0},{"title":1, "_id":0}).pretty();

#### Simple projection
    {"title":1, "_id":0}

#### Matching a specific array element
    db.movieDetails.find({"countries.1":{$all: ["Sweden"]}}).limit(1).pretty();

#### Equality queries
    db.movieDetails.find({$and: [{"genres":{$size: 2}}, {"genres":{$all: ["Comedy", "Crime"]}}, {"genres.0": "Comedy"}]}).count();

#### Array operators
    db.movieDetails.find({"genres":{$all: ["Comedy","Crime"]}}).count();
