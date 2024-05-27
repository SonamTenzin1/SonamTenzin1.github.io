---
Title: DBS101 Flipped Class 10
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: Transaction

**What is a transaction?**

In database system, a transaction is a unit of program execution that access and possibly updates various data items.

Transactions are like journeys with a starting point (begin transaction) and an ending point (end transaction). Everything that happens during the trip (operations) is part of the overall journey (transaction).

**ACID Properties in Transaction**

**Atomicity:** all the transaction that has occured should be reflected or none.

**Consistency:** isolated transaction occuring should preserve the consistency of the database.

**Isolation:** even though multiple transactions occur simultaneously, the system guarantees that each transaction occuring ends before another transaction begins.

**Durability:** the transaction should be completed successfully and the change should persist in the database even if the system fails.

**A Simple Transaction Model**

Assuming that we have a two accounts A and  B with initial balance of Nu.1000 and Nu.2000 respectively. We want to transfer Nu.500 from A to B.

![transaction1](<../assets/dbs_fc_10/Screenshot-(260).png>)

![transaction2](<../assets/dbs_fc_10/Screenshot-(261).png>)
Here, the transaction is successful and the balance of A and B is updated.

**Transaction Atomicity and Durability**

![transaction3](<../assets/dbs_fc_10/Screenshot-(303).png>)

![transaction4](../assets/dbs_fc_10/Screenshot-(262).png)
Here, the transaction is not successful and the balance of A and B is updated.

**Transaction Errors**
![errortransaction1](../assets/dbs_fc_10/Screenshot-(263).png)

![errortransaction2](../assets/dbs_fc_10/Screenshot-(264).png)

![errortransaction3](../assets/dbs_fc_10/Screenshot-(265).png)

**Transaction Isolation**

Systems that handle many transactions (like online stores or banking apps) often let these transactions happen at the same time (concurrently). This can lead to issues with keeping the data accurate (consistency). Making sure the data stays reliable even when transactions happen all at once (concurrently) requires additional effort. It would be much simpler to force transactions to happen in a line (serially), one after another, only starting the next one after the previous finishes completely. 

We can explain concurrency using different terms:

1. **Improved throughput and resource utilization:**
   - **Throughput:** This can be explained as getting more work done in a shorter amount of time. By allowing concurrency, we're essentially enabling the system to handle multiple tasks simultaneously, increasing its overall output.
   - **Resource utilization:** Here, we're talking about making better use of the available resources (like processors) in a computer. Concurrency allows these resources to be constantly engaged, minimizing idle time and maximizing their efficiency.

2. **Reduced waiting time:**
   - **Responsiveness:** This emphasizes how concurrency improves a system's ability to react quickly to user requests or incoming data. Even if multiple tasks are happening concurrently, the user perceives a faster response because they don't have to wait for one task to finish before another begins.  
   - **Improved user experience:** This broader term highlights the overall benefit for users. By reducing waiting times, concurrency makes the system feel smoother and more pleasant to interact with.


* Multiple transactions happening at once (concurrent transactions) can sometimes interfere with each other (violate isolation), potentially causing the entire database to be in an unexpected state (inconsistent) even though each transaction itself is done correctly.

* By looking at different ways transactions can be interleaved (schedules), we can find patterns that guarantee each transaction "sees" a consistent view of the data (isolation) and the overall database stays reliable (consistent).

* Database systems act like traffic controllers (concurrency-control schemes) for transactions, making sure they don't clash with each other (ensuring correct concurrent execution). This protects the integrity of the database.


Imagine a simplified banking system with two transactions happening:

1. **Transaction 1 (T1):** Move $50 from Account A to Account B.
2. **Transaction 2 (T2):** Transfer 10% of the balance from Account A to Account B.

There are two ways these transactions can be processed:

**One at a time (Serial Execution):**

* **Schedule 1:** We handle T1 completely first (transfer $50). Then, we handle T2 completely (transfer 10% of the remaining balance in A).
* **Schedule 2:** We handle T2 completely first (transfer 10% of the initial balance in A). Then, we handle T1 completely (transfer $50).

Think of it like waiting in line at the bank. In serial execution, only one transaction gets processed at a time, just like only one customer gets served at a time.


**Running things at once (Concurrent Execution):**

Imagine juggling tasks. You toss one ball up, then another, and keep switching between them. That's concurrency - handling multiple tasks (transactions) by interleaving their instructions in an unpredictable way.

**Uncertain Order of Events (Concurrent Schedules):**

Since you're juggling tasks, the exact order in which you handle each ball (transaction instruction) can vary. This unpredictable order creates different execution sequences, making it difficult to predict the exact outcome.

**Matching Up (Equivalent Concurrent Schedule):**

Imagine you can juggle in two different ways, but both end with the balls in the same final pattern. A concurrent schedule is "equivalent" if it produces the same result as a simpler, ordered execution (like juggling one ball at a time). This ensures things stay consistent.

**Watch Out for Drops! (Pitfall and Concurrency Control):**

Juggling can get messy if you drop a ball. Similarly, concurrent execution can lead to inconsistent states if transactions interfere with each other. To avoid this, we need "concurrency control" - like having someone help you juggle or using special juggling balls that stick together. This ensures things run smoothly and data stays consistent.

**Making Sure Things Stay The Same, Even with Overlap**

* **Serializable Schedules:** Imagine transactions as tasks. Serializable schedules make sure these tasks can be done at the same time (concurrently) without messing up the final outcome of the database. It's like following multiple recipes in the kitchen at once, but ensuring the final dishes turn out perfect.
* **Goal:** The main aim is to have concurrent executions (tasks happening at the same time) function as if they were done one after another (serially).
* **Why It Matters:** This is crucial because it allows for efficient database usage by enabling multiple tasks to run simultaneously. Without it, things could get mixed up and the database wouldn't be reliable.
* **Database System's Job:** The database system acts as a manager, overseeing all the tasks (transactions) and making sure none of them, even when running together, lead to inconsistencies in the final data.

This Trasaction transfers Nu.50 from account A to B
Sequential execution ensuring consistency

![transaction1](../assets/dbs_fc_10/Screenshot-(304).png)

This transaction transfers 10% of balance from A to B
Sequential execution preserving database integrity

![transaction2](../assets/dbs_fc_10/Screenshot-(305).png)

**Serializabity**

A schedule is considered serializable if it can be reordered to be equivalent to a serial schedule, where transactions are executed one after another. In other words, a serializable schedule ensures that the final outcome is the same as if the transactions were run sequentially. This guarantees that concurrent execution of transactions produces consistent results. Concurrency control mechanisms, such as locking and optimistic concurrency control, are employed to uphold serializability in databases.

The table blows summarizes the concept:

| Term | Description |
|---|---|
| Serializable schedule | A schedule that can be reordered to be equivalent to a serial schedule. |
| Serial schedule | A schedule where transactions are executed one after another. |
| Concurrency control mechanisms | Techniques used to ensure serializability in databases. |

**Importance of Serializability**

* **Prevents data chaos:** Serializability acts like a traffic cop, making sure transactions don't interfere with each other and leave the data in a mess.
* **Guarantees reliable results:** Even when multiple changes happen at once, serializability ensures the final outcome is the same as if the transactions were done one by one, leading to trustworthy data.
* **Like running in a line:** Imagine transactions as people waiting to use a copy machine. Serializability makes them take turns properly, so the final copies (the database state) are always clear and correct. 

**Conflicting Instructions**

Imagine two people (transactions) trying to update the same document (data item) at the same time. In order to avoid any confusion, it's important that only one person works on the document at a time.

- **Collision Course:** Instructions conflict if they're like two people trying to edit the same section of a document simultaneously. This can lead to inconsistencies and errors in the final document.
- **Interference:** If one person is writing (updating) the document and another person tries to read (access) it at the same time, they might interfere with each other's work. The reader might see outdated information, or the writer might overwrite changes made by the reader.
- **Stepping on Each Other's Toes:** Two instructions are seen as conflicting if they're like two people stepping on each other's toes while trying to modify the same part of a document. This creates a situation where it's unclear whose changes should prevail.

Now, imagine you're juggling information balls (transactions) in a specific order to get things done. This order is like a "schedule" for the juggling act. 

**Conflict equivalence** is basically like having two different ways to juggle the same information balls and get the same result, as long as you follow a key rule:

**Don't mess with the throws that could cause a collision!** These are the "conflicting instructions" - things like updating the same information at the same time. Imagine throwing two balls at once - that's a recipe for disaster!

Here's the cool part:

- You can swap around the order of throws that **don't** clash (like showing you a product page before or after someone else adds it to their cart). It doesn't matter as long as you don't mess with the throws that might cause trouble.

Basically, conflict equivalence gives the system some flexibility in juggling the information balls (transactions) as long as the crucial interactions (conflicts) happen in the same order. This helps keep things running smoothly behind the scenes without affecting your experience.

**Conflict Serializability**

Okay, imagine you're juggling balls (transactions) again, but this time you have a helpful friend (the database system) watching your back.

Your friend wants to make sure all the juggling (transactions) happen in a clean, orderly way, even if you don't always toss the balls in the perfect sequence. 

Here's the deal:

- **Your Juggling (The Schedule):** You might throw the balls (transactions) in a bit of a messy order, but as long as you don't throw two at once (conflicting operations), it's generally fine. This messy order is called a "schedule."
- **Clean Order (Serial Schedule):** Your friend, however, prefers a clean, step-by-step order where you throw one ball at a time (like a serial schedule in your example). This ensures no juggling mishaps.
- **Conflict Serializability:** But hey, you're good at juggling (conflict equivalent)! Your friend trusts that even if your order isn't perfect, as long as the order of throws where things could clash (conflicting operations) stays the same, you'll end up with the same result as the clean order. That's conflict serializability – your messy juggling (schedule) is still basically the same as the clean order (serial schedule) as long as the critical parts (conflicts) happen in the same order.

**Predence Graph**

Got it! Imagine you're juggling again, but this time with a helpful friend who draws a map (precedence graph) to keep track of the throws.

**Here's the deal:**

- You juggle balls (transactions) – you might add things, remove things, check on them (reads and writes) in any order that works for you.
- Your friend draws arrows to show what needs to happen in order (conflicts). For example, if you throw a green ball (write data A) before your friend throws a blue one (read data A), there's an arrow pointing from you (T1) to your friend (T2).
- **No Loops!** The key is, your friend avoids drawing circles (cycles) in the map. Circles mean things are getting messy – you might throw a ball back and forth forever!

**Why it matters:**

- If there's no circle (cycle) in the map (precedence graph), your friend knows your messy juggling (schedule) is basically the same as a clean, one-at-a-time juggling (serial schedule). You'll end up with the same result, as long as the throws that could clash (conflicting operations) happen in the same order.

**Think of it this way:**

- You're updating your shopping cart. You might add and remove items (reads and writes) in any order. The precedence graph ensures your friend (database) can still track things and make sure there are no conflicts (like trying to buy the last item while someone else does too). 

So, the precedence graph helps your friend (database) understand your messy juggling (schedule) and confirm it's still okay (conflict serializable) as long as the critical parts (conflicts) happen in the right order. 

**Checking Serializability**

1. **Track the Throws:**  Draw a map where you connect throws (transactions) that could cause trouble (conflicting operations). Like connecting throws where you grab one ball (read) before throwing another (write) at the same spot.
2. **Look for Knots:**  If your map ends up looking like a tangled mess with circles (cycles), it means your throws might clash (not conflict serializable). Imagine a tangled mess where you can't throw without hitting something!
3. **Clean Juggling:**  If your map is clear and doesn't have any circles, your juggling is good (conflict serializable). Each throw happens in a clean order without any potential mid-air collisions.

So, checking serializability is like making a map of your juggling to see if there's a risk of balls crashing (conflicting operations). No tangled mess (cycles) means smooth juggling (conflict serializable)!