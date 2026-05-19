# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement
Design an online platform that allows users to purchase tickets for concerts, sport events, theatre, and other live entertainment

---

# 2. Functional Requirements

- [ ] View upcoming events
- [ ] Book tickets to upcoming events
- [ ] Search for upcoming events

---

# 3. Non Functional Requirements
- [ ] Availability for searching & viewing events
- [ ] Consistency for booking
- [ ] Low latency search
- [ ] Read >> write

---

# 4. Core Entities

## User

- Event
- User
- Performer
- Venue
- Ticket
- Booking

---

# 5. APIs

### View events and available seats

```http
GET /events/:eventId
```

Response:

```
Event, Venue, Performer, SeatMap
```

---

### Search for an event

```http
GET /events/search?keyword={}
```

---

### Upload a file

```http
POST /bookings/:eventId
```

Response:

```json
{
  "seats": ["seat1", "seat2"],
  "paymentDetails": {
    
  }
}
```

---


# 6. Flow

### 1: Users should be able to view events
### 2: Users should be able to search for events
### 3: Users should be able to book ticket to events

