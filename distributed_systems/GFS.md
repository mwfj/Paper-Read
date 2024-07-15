# [The Google File System](https://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf)

## Brief Summary

The Google File System(GFS)  is a real world distribution file system example deployed in Google. It provide fault tolerance for supporting large-scale data processing workloads while running on inexpensive commodity hardware, and it delivers high aggregate performance to a large number of clients.

The Google File System deliver high aggregate throughput to many concurrent readers and writers performing a variety of tasks, achieving by separating file system control: 

- master for common operations and deliver chunk lease
- chuncksever for data transfer

It widely deployed within Google as the storage platform(It replaced by [**Colossus**](https://cloud.google.com/blog/products/storage-data-transfer/a-peek-behind-colossus-googles-file-system) and still using **Colossus** in 2024) for the generation and processing of data used by their service as well as research and development efforts that require large data set.



## What is the addressed problem and why is it important to address?

### Importance of Addressing the Problem:

For the practical perspective, Google need to distribution system to help them processing large-scale data set, like MapReduce module.

They need a file system with high availability, fault tolerant, data integration and also the data can be viewed globally.

### The problem need to address:

1. How to regard and handle the component failure?
2. How to store large file efficiently?
3. How to handle multiple clients append data to files efficiently?



## What has been done? what do previous studies fail to do and why?

This paper give some of difference assumptions for designing distribution file system compared with the previous work:

1. Component failure as the norm rather than the exception. The system is built from many inexpensive commodity components that often fail.
2. Expect Multi-GB files are the common case and should be managed efficiently.
3. The workload consist of two types of read:
   - Small random read
   - Large streaming read
4. The workload have many large, sequential writes that **append data to files**
5. The system must efficiently implement well-defined semantics for **multiple clients that concurrently append to the same file.**



**Compared with some of the previous work:**

- Unlike [AFS](https://dl.acm.org/doi/pdf/10.1145/35037.35059), GFS spreads a file's data across storage servers in a way that deliver aggregate performance and increase fault tolerance
- GFS dose not provide any caching below the file system interface, because GFS dose not require stream through large data set or randomly seek within it and read small amount s data each time.
- GFS use the centralized server approach in order to simplify the design, increase its reliability, and gain flexibility. 
  In particular, a centralized master make it much easier to implement sophisticated chunk placement and replication policies since the master already has most of the relevant information and control how it change.
- GFS use the commodity machines as chunk servers, instead of disk drivers.
- While using memory based queue, GFS use the atomic record to solve the similar problem related to the producer-consumer problem



## What is novelty or main contribution of this work?

In GFS, it introduce the architecture of **single master + chunk server + lease order**, which is a kind of novelty design at that time. The primary/secondary replication design is quite interesting as well.

GFS is a system applied in the Google's real production, which give us a good example of distribution file system in the real Google production

Unlike focus on large steaming insert and search and assume failure is a tricky case, GFS uses the commodity machine, mainly focus on large append write and assumes component failure is a common case.

## What is the technical method and approach of this work?



## How is the work evaluated? Are the evaluation method concrete? Does the evaluation cover all the aspects of consideration? Do the evaluation results support the claims?



## What are impacts of this work?

