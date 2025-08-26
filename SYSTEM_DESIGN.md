# Distributed File Storage
DFS is a cloud-based file storage service that allows users to store and share files.
It provides a secure and reliable way to store and access files from anywhere, on any device.

## Requirements
### Functional
- save a file to remote storage
- download a file
- automatically Sync files across devices

**Out of Scope**
- Roll own Blob Storage

### Non Functional
**Availability** > Consistency
- We prefer that evertime a client tries to download a file they get a file even if it's not the most up to date file. In other words, we prefer the system to be available rather than data to remain consistent. 
- low latency uploads and downloads (as low as possible) File size varies
- support large files as high as **50GB**
    - resumable uploads
- high data integrity
    - (sync accuracy is high)


## Core Entities
- File (raw bytes)
    - id
    - raw bytes
- File Metadata
    - name
    - id
    - mimetype
    - size
- Users (Let's keep is simple to not get distracted)
    - id 


## API
```
POST /files
{
    file,
    fileMetaData,
} => 204 NO CONTENT

GET /files?id=:fileId =>
{
    file,
    fileMetaData
} 200 OK

Get /changes?since={timestamp} =>
{
    fileIds[]
}
```

## High Level Design



## Deep Dives