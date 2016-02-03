# M101JS: MongoDB for Node.js Developers

Course from [MongoDB University](https://university.mongodb.com/courses/MongoDB/M101JS/2016_January/syllabus)

### HW - Week 1
- hw1-1, hw1-2, hw1-3 done

### HW - Week 2

#### Multiple selectors in a find() command
    db.movieDetails.find({'rated':'PG-13','year':2013, 'awards.wins': 0},{"title":1, "_id":0}).pretty();

#### Arrays with nested documents
    {"awards.oscars.award":"bestPicture"}

#### Simple projection
    {"title":1, "_id":0}

#### Matching a specific array element
    db.movieDetails.find({"countries.1":{$all: ["Sweden"]}}).limit(1).pretty();

#### Equality queries
    db.movieDetails.find(
      {$and: [
        {"genres":{$size: 2}},
        {"genres":{$all: ["Comedy", "Crime"]}},
        {"genres.0": "Comedy"}
      ]}
    ).count();

#### Array operators
    db.movieDetails.find({"genres":{$all: ["Comedy","Crime"]}}).count();

#### Updating based on multiple criteria
    db.movieDetails.updateMany(
      {$and: [
        {
          "imdb.votes": {$lt: 10000},
          year: {$gte:2010, $lte:2013},
          "tomato.consensus": {$exists: true, $eq: null}
        }
      ]
      },
      {$unset: {"tomato.consensus": ""}}
    )

### Week 3

#### Homework 3.2
Import dataset from [grades.json](grades.json)

    db.grades.find().skip(6).limit(2).sort({"grade":1})

    { "_id" : 14, "student" : "Seamus", "grade" : 33, "assignment" : "exam" }
    { "_id" : 13, "student" : "Bob", "grade" : 37, "assignment" : "exam" }

#### Homework 3.3
run [buildingQueryDocuments.js](buildingQueryDocuments.js)

#### Homework 3.4
run [overviewOrTags.js](overviewOrTags.js) 


### Week 4
03.02.2016 - 4.1, 4.2, 4.3 done
