# Collaborative persistence

With collaborative persistence we try to find the Goldilocks zone between local storage that is irretrievably lost when a device gets lost, broken, or stolen on the one hand and storage on a centralized server under the control of a big tech organisation on the other.

Let's try a bottom-up approach.

1. No persistence: events in the form of [iroh-gossip](https://github.com/n0-computer/iroh-gossip)
2. An event-store of aggregates each of which is an append-only sequence of events
3. Synchronized data set (set elements updated by messages)
4. Conflict-free replicated datatype (CRDT) that represents a string (this could be a Markdown document)
5. Conflict-free replicated datatype (CRDT) that represents a structured document

(Or should event-store and synchronized data set be ranked the other way around?)

There could be a message type between an ephemeral message and a persisted event. A transactional operator? This could work as follows:

1. A transaction-start event starts a transaction: this creates a temporary aggregate for the transaction
2. Transactional operators are events that are stored on the transaction aggregate
3. A transaction can be closed in two ways:
   1. A transaction-commit event records the result of the transaction and deletes the temporary aggregate together with all the transactional operators
   2. A transaction-rollback event signifies that the transaction was aborted and also deletes the temporary aggregate together with all the transactional operators
