# URL Shortner High Level Design (HLD)

---

# 1. Problem Statement

Design a cloud-based file storage service that allows users to store and share files
- It provides a secure and reliable way to store and access files from anywhere, on any device.

---

# 2. Functional Requirements

- [ ] Upload a file
- [ ] Download a file
- [ ] share files

---

# 3. Non Functional Requirements
- [ ] Support Large Files
- [ ] secure and reliable
- [ ] Availability > Consistency
- [ ] Low latency

---

# 4. Core Entities

## User

- File
- File Metadata
- User

---

# 5. APIs

### Upload a file

```http
POST /files
```

Request:

```
{
   File,
   FileMetadata
}
```

---

### Download a file

```http
GET /files/{fileId}/
```

Response:

```
File & Metadata
```

---

# 6. Flow

### 1: Users should be able to upload file from any device
### 2: Users should be able to download file from any device
### 3: Users should be able to share a file with other users

