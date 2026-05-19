# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement
Design WhatsApp

---

# 2. Functional Requirements

- [ ] Start group chats
- [ ] Send/receive messages/media
- [ ] Access messages after they've been offline

---

# 3. Non Functional Requirements
- [ ] Guaranteed delivery of messages
- [ ] Fault tolerance
- [ ] Low latency

---

# 4. Core Entities

## User

- Users
- Chats
- Messages
- Clients (Devices)

---

# 5. APIs

### Create Chat

```http
POST /createChat/
```

Request body
```json
{
  "participants": [],
  "Name": "abc"
}
```

Response
```json
{
  "chatId": ""
}
```

---

### Send message

```http
POST /sendMessage
```

Request body
```json
{
  "chatId": "",
  "message": "",
  "attachments": []
}
```

Response
```json
{
  "status": "SUCCESS | FAILURE",
  "messageId": ""
}
```

---

### Create attachment

```http
POST /createAttachment
```

---

### Modify chat participants

```http
PUT /modifyChatParticipants
```

---


# 6. Flow

### 1: Users should be able to start a group chat
### 2: Users should be able to send/receive messages
### 3: Users should be able to send/receive media

