# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement
Design a platform for users to answer questions and get feedback on their solutions. The platform also runs periodic coding competitions

---

# 2. Functional Requirements

- [ ] View a list of coding problems
- [ ] View a given problem and code a solution in multiple languages
- [ ] Submit the solution and get instant feedback

---

# 3. Non Functional Requirements
- [ ] Availability > consistency
- [ ] Isolation and security when running user code
- [ ] Low latency
- [ ] Scale to support competition with > 100K users

---

# 4. Core Entities

## User

- Problem
- Submission
- Leaderboard

---

# 5. APIs

### View a list of problems

```http
GET /problems/?page=1?limit=100
```

---

### View a specific problem

```http
GET /problems/{id}
```

---

### Submit a solution

```http
POST /problems/{id}/solution
```

Request body:

```json
{
  "Code": "Code",
  "language": "java"
}
```

---


# 6. Flow

### 1: Users should be able to view a list of coding problems
### 2: Users should be able to view a given problem and code a solution
### 3: Users should be able to submit their solution and get instant feedback
### 4: Users should be able to view a live leaderboard

