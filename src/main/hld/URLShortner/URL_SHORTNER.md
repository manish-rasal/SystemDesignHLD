# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement

Design a scalable URL Shortner capable of supporting:
- URL shortening service that converts long URLs into shorter, manageable links

---

# 2. Functional Requirements

- [ ] Users can create short URLs from original URLs
- [ ] Users can access the original URL by visiting the short URL

---

# 3. Non Functional Requirements
- [ ] Uniqueness of short URLs
- [ ] Low latency
- [ ] Availability >> Consistency
- [ ] Scalable

---

# 4. Core Entities

## User

- Original URL
- Short URL
- User

---

# 6. APIs

### Shorten a URL

```http
POST /urls
```

Request:

```json
{
   "long_url":"https://www.example.com/some/very/long/url"
}
```

Response:

```json
{
   "short_url":"http://short.ly/abc123"
}
```

---

### Redirect to Original URL

```http
GET /{short_code}
```

Response:

```
HTTP 302 Redirect to original long URL
```

---

# 8. Flow

### 1: Users should be able to submit a long URL and receive a shortened version
### 2: Users should be able to access the original URL by using the shortened URL

---
# 9. Storage Choices

## Database (SQL / NoSQL)

### Choice: PostgreSQL / Cassandra

Why?
* Persistent storage for URL mappings
* Fast key-based lookup
* Stores metadata (creation time, expiry, creator)

---
### Redis Cache

Why?
* Extremely fast reads
* Popular URLs repeatedly accessed

---
### Global Counter

Why?
* Generate unique IDs
* Used for Base62 encoding

Alternatives
* Snowflake IDs
* Zookeeper sequence
* Range allocation

---

# 10. Database Schema

```sql
CREATE TABLE urls(
    short_code VARCHAR(20) PRIMARY KEY,
    original_url TEXT,
    created_by BIGINT,
    created_at TIMESTAMP,
    expiry_at TIMESTAMP,
    click_count BIGINT
);
```

---

# 11. Core Design Concepts Used

## API Gateway

Responsibilities:

* Authentication
* Request routing
* Rate limiting

---

### Cache Aside Pattern

Flow:
```
Redis
   ↓ miss
Database
   ↓
Populate Cache
```
---


# 12. Scaling Strategy

### Service Scaling

* Stateless services
* Horizontal scaling behind LB

---

### Database Scaling

* Read replicas
* Sharding
---

### Cache Scaling

* Redis Cluster
* Consistent hashing

