## MongoDB Exercises
### Instructions 
1. Download Robo 3t and setup it on your machine.
1. Create a new connection
1. Create a new collection (students)
1. Right click on the collection.
1. Select 'insert Document'.
1. Enter image description here
1. Paste your json data
1. Click validate.
1. Click save.
1. Excute your queries on the query bar.
1. Test your queries using robo 3t


1. Insert yourself as a new  student. Example:
`{"fname" : "Ahmad","lname":"Omar","class":"A","age" :25}`

```
db.students.insertOne(
{
  "fname":"Ismail",
  "lname":"Ryan",
  "class":"A",
  "age":36,
  "technologies":["PHP","mySql"]
});

```

2.  Insert the following students.

`{"fname" : "Ahmad","lname":"Omar","class":"A","age" :25,"technologies":["PHP","mySql"]}`
`{"fname" : "Ammar","lname":"Saad","class":"B","age" :23,"technologies":["PHP","MongoDB"]}`
`{"fname" : "Steve","lname":"Rayan","class":"C","age" :18,"technologies":["C#","mySql"]}`
`{"fname" : "Jhon","lname":"williams","class":"A","age" :30, "technologies":["Python","MongoDB"]}`

```
db.students.insertMany([
{
  "fname":"Ahmad",
  "lname":"Omar",
  "class":"A",
  "age":25,
  "technologies":["PHP","mySql"]
},
{
  "fname":"Ammar",
  "lname":"Saad",
  "class":"A",
  "age":23,
  "technologies":["PHP","MongoDB"]
},
{
  "fname":"Steve",
  "lname":"Ryan",
  "class":"A",
  "age":18,
  "technologies":["C#","mySql"]
},
{
  "fname":"Jhon",
  "lname":"Williams",
  "class":"A",
  "age":30,
  "technologies":["PHP","MongoDB"]}]
);

```

3.  Write a MongoDB query to update the data of all students by incrementing their ages one year..

`db.students.updateMany({},{$inc:{age:1}})`

4. Write a MongoDB query to update all the student who has (ADAM) name and make thier classs `A` and thier technolgies `['PHP','mySql']`.

`db.students.updateMany({fname:"Adam"},{$set:{class:"A",technologies:["PHP","MySql"]}})`


5. Write a MongoDB query to delete one student from class `A` .

`db.students.deleteOne({class:"A"})`

6.  Write a MongoDB query to delete All the students from class `C`.

`db.students.deleteMany({class:"C"})`


7. Write a MongoDB query to display all the students that thier age less than 20.

`db.students.find({age:{$lt:20}});`


8. Write a MongoDB query to display all the students that thier age greater than 30.

`db.students.find({age:{$gt:20}});`


9. Write a MongoDB query to get only the students of class `B`.

`db.students.find({class:'B'});`


10.  Sort the faculty details by their age (descending order) and get the details of the first five faculty members only. .

`db.students.find({}).sort({age:-1}).limit(5)`
