# RAFT-Distributed-Network-System

## go local sort practice:
  This project will read, write, and sort files consisting of zero or more records. A record is a 100 byte binary key-value pair, consisting of a 10-byte key and a 90-byte value. Each key is interpreted as an unsigned 10-byte (80-bit) integer. The sort is ascending, meaning that the output should have the record with the smallest key first, then the second-smallest, etc.
  
## distributed sort:
  This is an extension of the sort programto a distributed peer-to-peer framework. In this project, we will have multiple servers instead of one server. Each server has its own single input file. At the end of the netsort process, each server will have a portion of the sorted output dataset. The distributed sorting program will concurrently run on all servers. In particular, this
netsort program has the ability to sort a data set that is larger than any one server can hold.

<img width="641" alt="image" src="https://github.com/user-attachments/assets/d215a070-7dd3-44da-8959-0e1ce4e58e6f">

## HTTP server:
  This repository contains the implementation of a simple web server called TritonHTTP. This server implements a subset of the HTTP/1.1 protocol specification, providing basic web server functionality for handling HTTP GET requests and serving static files.
  
<img width="471" alt="image" src="https://github.com/user-attachments/assets/61ff7bc8-c6f6-478b-a56f-9923f856242a">

## Surfstore: [multi blockstore & multi metadata store]

<img width="711" alt="image" src="https://github.com/user-attachments/assets/98b778e7-8301-4e6c-84c5-86b6b94c1ae8">

  This project implements a fault-tolerant metadata server for a DropBox-like system called "SurfStore." The metadata server uses the RAFT protocol to ensure consistency and availability, even in the presence of server failures. 
  The core of this system is the metadata server, which maintains the metadata for the files stored in SurfStore. The server is designed to handle basic file operations, such as updating file information and retrieving file metadata. To achieve fault tolerance, multiple instances of the metadata server run concurrently, with one server acting as the leader. The leader is responsible for handling client requests and replicating the operations to the other servers, known as followers.

Key Features:
- Fault Tolerance: The metadata server remains operational even if some of the servers fail. This is achieved through the RAFT protocol, which ensures that the servers agree on the operations to be performed.
- Consistency: All servers in the system maintain a consistent view of the metadata. This means that clients will see the same file metadata regardless of which server they connect to.
- Log Replication: The leader server replicates the operations to the follower servers. Only when a majority of the servers have acknowledged an operation does it get committed and applied to the metadata.
- Leader Election: In case the leader server fails, the remaining servers will automatically elect a new leader to continue handling client requests.
The RAFT protocol is central to this implementation. It handles the leader election process and ensures that the operations are replicated and committed across all servers consistently. This way, the system can tolerate failures and maintain the integrity of the metadata.

<img width="750" alt="image" src="https://github.com/user-attachments/assets/b2f0d8dd-9dea-4554-b201-f962519c0575">

