# Systems Design Interview

## Why?
* why do we need this

## Requirements Gathering

### Functional Requirements
* what does the service do
* what behaviors should users expect from our service

### Non-Functional Requirements
* availability
* quality of service
* functional security

### Extended Requirements
* analytics
* APIs
* any additional extended functionality

## Capacity Estimation and Constraints
### Traffic Estimates
* read/write ratio
* queries per second
### Storage Estimates
* how much data are we looking to store
* data read to write relationship
### Bandwidth Estimates
* expected number of requests per second
### Memory Estimates
* 80-20 rule
* caching
* number of requests
### High Level Estimates
* number of requests in a given time
* number of operations performed
* incoming / outgoing data
* amount of storage needed
* amount of caching needed

## System APIs
* function name, parameters and return value

## Database Design
* number of records
* size of each record
* relationship between records
* read heavy / write heavy
### Database Schema
### Database type
* relational vs non-relational
* talk about dataset size
* relational vs non-relational

## Basic System Design and Algorithm
Things to consider
* data uniqueness
* identify specific pitfalls

## Data Partitioning and Replication
* database scaling
* data partitioning
 
## Cache

## Load Balancer

## DB Cleanup

## Telemetry

## Security

## Key Characteristics of Distributed Systems
### Scalability
* capability to grow to meet increased usage
* horizontal vs vertical scaling
### Reliability
* probability system will fail in a given period
* redundancy
### Availability
* percentage of time a system remains operational under normal conditions
* high reliability contributes to high availability, but not vice versa 
### Efficiency
Measured using
1. latency
2. bandwidth
### Serviceability / Manageability
* simplicity and speed for a system to be maintained / repaired

## Load Balancing
* spreads traffic across servers 
* improve responsiveness and availability
* reduces server load

### Where are load balancers placed:
* between users and web server
* between web servers and internal platform
* between internal platform and database 

### Benefits
* faster / uninterrupted service
* lower downtime, higher throughput
* easier handling of incoming requests
* smart load balancers
* fewer failed or stressed components

### Load Balancing Algorithms
Consider 2 factors before forwarding requests
1. server is actually responding, then uses algorithm
2. perform health check. If server fails health check, remove server from the pool

#### Algorithms
* least connection method 
* least response time method
* least bandwidth method
* round robin method
* weighted round robin method
* IP hash

Redundant load balancing allows for load balancers to be replaced when one fails

## Caching
* locality of reference: recently requested data is likely requested again 

### Application server cache
* place cache on request layer node to cache local storage of response node

### CDN
* serves large amounts of static media

### Cache Invalidation
#### Write-through cache
* data is written to cache and database
* higher latency
#### Write-around cache
* data written to permanent stage
* recent read might result in cache miss, must read from slower back-end, leads to higher latency
#### Write-back cache
* data written to cache, written to permanent storage later
* low latency and high throughput
* risk of data loss in the case of system crash

### Cache eviction policies
1. First In First Out (FIFO)
2. Last In First Out (LIFO)
3. Least Recently Used (LRU)
4. Most Recently Used (MRU)
5. Least Frequently Used (LFU)
6. Random Replacement (RR)

## Data Partitioning

## Indexes

## Proxies

## Redundancy and Replication

## SQL vs NoSQL

## CAP Theorem

## Consistent Hashing

## Long-Polling vs WebSockets
