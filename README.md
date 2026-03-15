# UDB-2
Q1. Make a schema first and then insert 6 documents. • Roll_no=[1,2,3,4,5,] • Name=["Ram","Alex","John","Bob","Mukesh",”Danny”] • Age=[20,19,40,55,30,28] • Salary=[546.7,333.4,666.7,678.4,245.6,546.3] • City=["A","B","C","D","E",”F”] • Phone_no=[123,456,122,444,567,892]
Q2. Write a query to update the name of RAM to SAM.
Q3. Write a query to display only the cities present in that collection
Q4. Write a query to update the salary by 101.
Q5. Write a query to display all the documents in ascending and descending order of age
Q6. Display Documents with City A, B, and C .
Q8. Write a query to delete a document with ROLL_NO:5.
Q9. Write a query to display all the documents with AGE greater than 20.
Q10. Write a query to display all the documents with AGE less than 20.
Q12. Write a query to display all the documents with AGE not equals to 20. # distructured-lab-1
 
Q1. Create a database named collegeDB and switch to it.
Ans:use collegeDB.
 
 
Q2. Create a collection named students in the collegeDB database.
Ams:db.createCollection("students")
 
 
Q3. Insert one document into the students collection with the following fields:
• name
• rollNo
• department
• age
Ans:db.students.insertOne({
 name: "Rahul Sharma",
 rollNo: 101,
 department: "CSE",
 age: 20
})
 
Q4. Insert four more documents into the students collection with different
values.
Ans:```js
db.students.insertMany([
 {
   name: "Anita Das",
   rollNo: 102,
   department: "ECE",
   age: 21
 },
 {
   name: "Sourav Paul",
   rollNo: 103,
   department: "CSE",
   age: 22
 },
 {
   name: "Neha Singh",
   rollNo: 104,
   department: "ME",
   age: 20
 },
 {
   name: "Amit Kumar",
   rollNo: 105,
   department: "CSE",
   age: 23
 }
])
Q5. Display all documents present in the students collection.
Ans:db.students.find()
 
Q6. Display only those students who belong to the CSE department.
Ans:db.students.find({ department: "CSE" })
 
Q7. Update the age of one student (any one) to a new value.
Ans:db.students.updateOne(
 { rollNo: 101 },
 { $set: { age: 21 } }
)
 
Q8. Delete one document from the students collection using any condition.
# unstructured-lab-2
Q1. Make a schema first and then insert 6 documents.
• Roll_no=[1,2,3,4,5,]
• Name=["Ram","Alex","John","Bob","Mukesh",”Danny”]
• Age=[20,19,40,55,30,28]
• Salary=[546.7,333.4,666.7,678.4,245.6,546.3]
• City=["A","B","C","D","E",”F”]
• Phone_no=[123,456,122,444,567,892]
 
Ans:Schema (Document Structure):
{
 roll_no: Number,
 name: String,
 age: Number,
 salary: Number,
 city: String,
 phone_no: Number
}
Create Database & Collection:
use studentDB
db.createCollection("students")
Insert 6 Documents:
db.students.insertMany([
 
 { roll_no: 1, name: "Ram", age: 20, salary: 546.7, city: "A", phone_no: 123 },
 { roll_no: 2, name: "Alex", age: 19, salary: 333.4, city: "B", phone_no: 456 },
 { roll_no: 3, name: "John", age: 40, salary: 666.7, city: "C", phone_no: 122 },
 { roll_no: 4, name: "Bob", age: 55, salary: 678.4, city: "D", phone_no: 444 },
 { roll_no: 5, name: "Mukesh", age: 30, salary: 245.6, city: "E", phone_no: 567 },
 { roll_no: 6, name: "Danny", age: 28, salary: 546.3, city: "F", phone_no: 892 }
])
 
View Data:
db.students.find()
 
Q2. Write a query to update the name of RAM to SAM.
Ans:To change the name RAM to SAM, we use the updateOne() command in MongoDB.
db.students.updateOne(
 { name: "Ram" },
 { $set: { name: "Sam" } }
)
 
Q3. Write a query to display only the cities present in that collection.
Ans:To show only the cities from the collection, use this query:
 
db.students.find(
 {},
 { city: 1, _id: 0 }
)
 
Q4. Write a query to update the salary by 10%
Ans:To increase the salary of all students by 10%, use this query:
db.students.updateMany(
 {},
 { $mul: { salary: 1.10 } }
)
 
Q5. Write a query to display all the documents in ascending and descending order of age.
Ans:Ascending order (Age – Low to High):
db.students.find().sort({ age: 1 })
Descending order (Age – High to Low):
db.students.find().sort({ age: -1 })
 
Q6. Display Documents with City A, B, and C
Ans:db.students.find({
 city: { $in: ["A", "B", "C"] }
})
Q7. Write a query to display only two documents from the entire collection.
Ans:db.students.find().limit(2)
 
Q8. Write a query to delete a document with ROLL_NO:5.
Ans:db.students.deleteOne({ roll_no: 5 })
 
Q9. Write a query to display all the documents with AGE greater than 20.
Ans:db.students.find({
 age: { $gt: 20 }
})
 
Q10. Write a query to display all the documents with AGE less than 20.
Ans:db.students.find({
 age: { $lt: 20 }
})
Q11. Write a query to display all the documents with AGE equals to 20.
Ans:db.students.find({
 age: 20
})
 
Q12. Write a query to display all the documents with AGE not equals to 20.
Ans:db.students.find({
 age: { $ne: 20 }
})
Q13. Write a query to display all the documents where AGE is greater than equals to 30
Ans:db.students.find({
 age: { $gte: 30 }
})
