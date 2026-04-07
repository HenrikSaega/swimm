---
title: Comments
---
<SwmSnippet path="/comments/index.js" line="13">

---

&nbsp;

```javascript
app.get('/posts/:id/comments', (req, res) => {

    res.send(commentsByPostId[req.params.id] || []);
    
}
);
```

---

</SwmSnippet>

<SwmSnippet path="/comments/index.js" line="20">

---

&nbsp;

```javascript
app.post('/posts/:id/comments', (req, res) => {
    const commentId = randomBytes(4).toString('hex');
    const { content } = req.body;
    const comments = commentsByPostId[req.params.id] || [];
    comments.push({ id: commentId, content });

    commentsByPostId[req.params.id] = comments;

    res.status(201).send(comments);

});
```

---

</SwmSnippet>

<SwmMeta version="3.0.0" repo-id="Z2l0aHViJTNBJTNBc3dpbW0lM0ElM0FIZW5yaWtTYWVnYQ==" repo-name="swimm"><sup>Powered by [Swimm](https://app.swimm.io/)</sup></SwmMeta>
