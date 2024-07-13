# [The Google File System](https://static.googleusercontent.com/media/research.google.com/en//archive/gfs-sosp2003.pdf)

## Brief Summary

The Google File System(GFS)  is a real world distribution file system example deployed in Google. It provide fault tolerance for supporting large-scale data processing workloads while running on inexpensive commodity hardware, and it delivers high aggregate performance to a large number of clients.

The Google File System deliver high aggregate throughput to many concurrent readers and writers performing a variety of tasks, achieving by separating file system control: 

- master for common operations and deliver chunk lease
- chuncksever for data transfer

It widely deployed within Google as the storage platform(It replaced by [**Colossus**](https://cloud.google.com/blog/products/storage-data-transfer/a-peek-behind-colossus-googles-file-system) and still using **Colossus** in 2024) for the generation and processing of data used by their service as well as research and development efforts that require large data set.



## What is the addressed problem and why is it important to address?

### Importance of Addressing the Problem:



### The problem need to address:



## What has been done? what do previous studies fail to do and why?



## What is novelty or main contribution of this work?



## What is the technical method and approach of this work?



## How is the work evaluated? Are the evaluation method concrete? Does the evaluation cover all the aspects of consideration? Do the evaluation results support the claims?



## What are impacts of this work?

