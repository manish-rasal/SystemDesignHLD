# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement

Design a service which delivers goods typically found in a convenience store via rapid delivery and multiple micro distribution centres (DCs).

---

# 2. Functional Requirements

- [ ] Query Availability by location
- [ ] Order items

---

# 3. Non Functional Requirements
- [ ] connect to nearby DC
- [ ] Fast for availability
- [ ] Ordering is strongly consistent

---

# 4. Core Entities

## User

- Item
- Inventory
- Distribution Centre
- Order
- Order Item

---

# 5. APIs

### Upload a file

```http
GET /availability?keyword={}
```

Response:

```json
{
  "items": {
    "name": "name",
    "Quantity": 1
  }
}
```

---

### Upload a file

```http
POST /order
```

Request:

```json
{
  "items": ["item1", "item2"]
}
```

---


# 6. Flow

### 1: Customers should be able to query availability of items
### 2: Customers should be able to order items

