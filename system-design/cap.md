# CAP Theorem

CAP is acronym for Consistency, Availability, and Partition Tolerance. It is a theorem that states that it is impossible for a distributed
data store to simultaneously provide more than two out of the following three guarantees:

* CA (Consistency and Availability) - All nodes see the same data at the same time. This guarantee is not applied for distributed systems
  because they have to be Partition Tolerance
* AP (Availability and Partition Tolerance) - Every request receives a (non-error) response, without the guarantee that the data is the most
  recent.
* CP (Consistency and Partition Tolerance) - Every request receives a (non-error) response, with the guarantee that the data is the most
  recent.

## Links

* [Video by IBM Technology: What is CAP Theorem?](https://youtu.be/eWMgsk7mpFc)
* [Video by ByteByteGo: CAP Theorem Simplified | System Design Fundamentals](https://youtu.be/BHqjEjzAicA)
* [Video by Studying with Alex: Friendly Intro To the CAP Theorem (Consistency vs Availability vs Partition Tolerance)](https://youtu.be/gkg-FAEXIkY)
    - I liked the examples which were used to explain the CAP theorem.