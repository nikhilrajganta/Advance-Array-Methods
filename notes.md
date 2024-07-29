Task 1: Consolidating Event Attendees
Description: Given arrays of attendees for different events, create a single array of unique attendees (no duplicates) sorted alphabetically by name.

```js
const eventAttendees = [
  ...event1Attendees,
  ...event2Attendees,
  ...event3Attendees,
];

const unique = [...new Set(eventAttendees)].sort();

console.log(uniqueAttendees);
// Output: ['Alice', 'Bob', 'Charlie', 'Dave', 'Eve', 'Frank']
```

Task 2: Analyzing Survey Responses
Description: Find the average rating of each topic from survey responses.

```js
const topicRatings = surveyResponses.reduce((acc, { topics, rating }) => {
  topics.forEach((topic) => {
    if (!acc[topic]) {
      acc[topic] = { total: 0, count: 0 };
    }
    acc[topic].total += rating;
    acc[topic].count += 1;
  });
  return acc;
}, {});

const avgRatings = Object.fromEntries(
  Object.entries(topicRatings).map(([topic, { total, count }]) => [
    topic,
    total / count,
  ])
);

console.log(avgRatings);
// Output: { 'Environment': 4.5, 'Economy': 3.5, 'Health': 3, 'Politics': 5 }
```

Task 3: Filtering and Mapping Book Data
Description: Select books published after 2000 and create an array of their titles and authors in the format "Title by Author".

```js
const filteredBooks = books
  .filter((book) => book.year > 2000)
  .map((book) => `${book.title} by ${book.author}`);

console.log(filteredBooks);
// Output: ['Book B by Author 2', 'Book C by Author 3']
```

Task 4: Complex Product Inventory Analysis
Description: Find products that are available in all stores. A product is available in a store if its inventory is more than 0.

```js
const availableInAllStores = products
  .filter((product) => product.stores.every((store) => store.inventory > 0))
  .map((product) => product.name);

console.log(availableInAllStores);
// Output: ['Product 2']
```

Task 5: Creating a Nested Comment Thread
Description: Structure an array of comments into a nested comment thread based on the replyTo field.

```js
const commentMap = new Map();
const commentsInfo = [];

comments.forEach((comment) => {
  comment.replies = [];
  commentMap.set(comment.commentId, comment);
});

comments.forEach((comment) => {
  if (comment.replyTo) {
    const parent = commentMap.get(comment.replyTo);
    if (parent) {
      parent.replies.push(comment);
    }
  } else {
    commentsInfo.push(comment);
  }
});

console.log(commentsInfo);
// Output:
// [
//   { commentId: 'c1', text: 'Comment 1', replies: [{ commentId: 'c2', text: 'Comment 2', replies: [] }] },
//   { commentId: 'c3', text: 'Comment 3', replies: [] }
// ]
```
