# Transactions
> In SQL, a transaction is a sequence of one or more database operations that are executed as a single logical unit of work. These operations can include inserting, updating, or deleting data, and can span multiple tables and/or rows. Transactions are used to ensure that the database remains in a consistent state, even in the event of errors or system failures. They also provide a way to undo or rollback changes, if necessary. Transactions are typically managed using the BEGIN, COMMIT, and ROLLBACK statements.

## Features of transactions
The instructions are carried out according to the ACID principle:

- Atomicity (Atomicity): "Everything or nothing" is executed and stored, only a part is not possible.
- Consistency (Consistency): Before and after the transaction, the data is consistent, that is, free of contradictions and correct.
- Isolation (Isolation): Changes are only stored and visible to other users when the transaction is complete. During the transaction, the affected data is locked for others.
- Durability (Durability): The changes remain permanently stored in the database after the transaction.

Transactions should be as short as possible due to the locks and therefore contain as little SQL code as possible. There is the possibility of rolling back (Rollback) if an error occurs or the transaction is interrupted. This is an implicit rollback to the state before the transaction.

A logbook is maintained for the undo operation, also called a transaction log. It is logically structured, consisting of instructions and not states.

## Transaction Code-Example
> This transaction will virtualy execute the commands and only execute them to the "real" database as soon as the TRY gets executed without errors. If the TRY fails it will go to the CATCH and ROLLBACK the transaction.
```sql¨
BEGIN TRANSACTION 

    BEGIN TRY
        UPDATE example set name = 'Max' where exampleId = 1 
        DELETE from example where example = 7
    END TRY 

    BEGIN CATCH
        ROLLBACK TRANSACTION
    END CATCH

COMMIT TRANSACTION
```
