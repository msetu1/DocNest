## Mst.Setu AKther

# MongoDB Practice Task - In-Depth Exploration of MongoDB Queries

This document includes several MongoDB queries to practice working with documents and arrays. Follow each task to explore different query types, from basic retrieval to updates and deletions within MongoDB.

## Table of Contents

- [Task 1](#task-1-find-documents-where-age-is-greater-than-30)
- [Task 2](#task-2-find-documents-with-favorite-color-maroon-or-blue)
- [Task 3](#task-3-find-documents-with-empty-skills-array)
- [Task 4](#task-4-find-documents-with-skills-in-javascript-and-java)
- [Task 5](#task-5-add-new-skill-to-document-with-specific-email)
- [Task 6](#task-6-add-language-to-languages-list)
- [Task 7](#task-7-remove-skill-from-skills-array)

---

### Task 1: Find Documents Where Age is Greater Than 30

**Objective:** Retrieve all documents where the age is greater than 30, returning only the `name` and `email` fields.

**Query:**
```javascript
db.collection.find(
  { age: { $gt: 30 } },
  { name: 1, email: 1, _id: 0 }
)

2. Find Documents with Favorite Color "Maroon" or "Blue"
Description: Find documents where the favoriteColor field is either "Maroon" or "Blue."

Example Query:
db.collection.find(
  { favoriteColor: { $in: ["Maroon", "Blue"] } }
)

3. Find Documents with an Empty Skills Array
Description: Retrieve all documents where the skills array is empty.

Example Query:
db.collection.find(
  { skills: { $size: 0 } }
)


4. Find Documents with Skills in Both "JavaScript" and "Java"
Description: Find documents where the person has skills in both "JavaScript" and "Java."

Example Query:
db.collection.find(
  { skills: { $all: ["JavaScript", "Java"] } }
)


5. Add a New Skill to Document with Specific Email
Description: Add a new skill to the skills array for the document with the email "amccurry3@cnet.com". If the document doesn’t exist, insert it first.

Skill to Add:
name: "Python"
level: "Beginner"
isLearning: true
Example Insert Query (if document is missing):

db.collection.insertOne({
  email: "amccurry3@cnet.com",
  name: "User Name",
  skills: []
})

Example Update Query:

javascript
Copy code
db.collection.updateOne(
  { email: "amccurry3@cnet.com" },
  { $push: { skills: { name: "Python", level: "Beginner", isLearning: true } } }
)

6. Add Language "Spanish" to Languages List
Description: Add "Spanish" to the list of languages spoken by the person.

Example Query:

javascript
Copy code
db.collection.updateOne(
  { email: "amccurry3@cnet.com" },
  { $addToSet: { languages: "Spanish" } }
)

7. Remove Skill with Name "Kotlin" from Skills Array
Description: Remove the skill with the name "Kotlin" from the skills array.

Example Query:

javascript
Copy code
db.collection.updateOne(
  { email: "amccurry3@cnet.com" },
  { $pull: { skills: { name: "Kotlin" } } }
)