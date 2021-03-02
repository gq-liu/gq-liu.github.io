---
layout: default
title: Raft
parent: paper-read
nav_order: 2
last_modified_date: Mar 2 2021 at 10:51 AM
---

## 1. What is Raft
Raft is a **consensus algorithm** for managing a **replicated log**.  
- What is a consensus algorithm:  
    >Consensus algorithms allow a collection of machines to work as a coherent group that can survive the fail- ures of some of its members.
- What is a replicated log:
    > See section 3: Replicated state machines

## 2. Key features of Raft  
- Strong Leader: For example, log entries **only flow from the leader to other servers**.  
- Leader election: 
- Membership changes: xxx  

## 3. Replicated state machines   
State:  after a sequences of operation, the machine move from stateA --> stateB.   

Replicated state machines: a cluster of servers which make sure each replica server achieves the identical state eventually, hence they behave like a single, high availability state machine when interacting with client.  

How do RSM ensure identical states?  
Using **replica logs**. Each server stores a log containing a series of commands, which used for its state machine to execute in order. Since logs of replica servers are identical (same commands in same order), and each command are deterministic, so each server's state machine computes the same state and has the same sequence of outputs.   

