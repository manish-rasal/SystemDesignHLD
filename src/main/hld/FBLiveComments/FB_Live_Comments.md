# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement
Design a feature that enables viewers to post comments on a live video feed. Viewers can see a continuous stream of comments in near real-time

---

# 2. Functional Requirements

- [ ] Viewers can post comments
- [ ] Viewers can see all comments posted in near realtime
- [ ] Viewers can see all comments posted before they joined

---

# 3. Non Functional Requirements
- [ ] Scale to millions of viewers per video
- [ ] Availability > consistency
- [ ] Low latency comment broacast

---

# 4. Core Entities

## User

- User
- Live video
- Comment

---

# 5. APIs

### Add a comment

```http
POST /comments/:liveVideoID
```

Request body:

```json
{
  "message": "Cool video!"
}
```

---

### Fetch past comments

```http
GET /comments/:liveVideoID?cursor={last_comment_id}
```

---


# 6. Flow

### 1: Viewers can post comments on a live video feed
### 2: Viewers can see new comments being posted while they are watching the live video
### 3: Viewers can see past comments before they joined the video

