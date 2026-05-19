# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement
Design Facebook news feed

---

# 2. Functional Requirements

- [ ] Create posts
- [ ] Follow people
- [ ] View feed
- [ ] Page through feed

---

# 3. Non Functional Requirements
- [ ] Post visible in < 1min (Eventual consistency)
- [ ] Posting and viewing post < 500ms
- [ ] Massive number of users
- [ ] Unlimited follows/followers

---

# 4. Core Entities

## User

- User
- Follow
- Post

---

# 5. APIs

### Make a post

```http
POST /posts/
```

Request body:

```json
{
  "content": {}
}
```

Response:

```
200 OK
{
    "postId": 1234
}
```

---

### Follow

```http
PUT /users/follow/{id}
```

---

### Get feed

```http
GET /feed?curson={}
```

Response:

```json
{
  "Posts": ["post1", "post2"],
  "nextCursor": "value"
}
```

---


# 6. Flow

### 1: Users should be able to create a post
### 2: Users should be able to follow people
### 3: Users should be able to view a feed of posts from people they follow
### 4: Users should be able to page through their feeds

