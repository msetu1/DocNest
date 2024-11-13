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
