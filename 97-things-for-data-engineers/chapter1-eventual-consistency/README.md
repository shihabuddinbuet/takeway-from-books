# A (Book) case for eventual consistency

let's say, there is book store in a location, its inventory system serve the request from customer. 
When a customer approache to purchase a book, the system does the following things:

1. fetch the ledgers to get details
2. Records the new purchase
3. Update all records
4. Return a reciept to the customer

The approache is called **strong consistency**, there will be no outdated data for any transcation. 

Then business is booming, the owner has opened multiple stores in different location and the inventory system has to handle lots of requests from customer. SO, you need to rearchitecte the system where there a master register for first store and other store register is connected with the master register. 

The system works until you control over the master register. Then customers will be block to do a request and your queue takes much time to process. 

## Eventual Consistency
On daily basis, you can update ledger of inventory. In this approache, you update the inventory of your books by counting all of them in each store and validating that each title you expect is on your shelves. Each night, your stores’ shelves pass their tests, and you can go home resting assured that your books are balanced. 
This approach is called eventual consistency where the state will be updated eventually (nightly in the case) but the system will work on outdated data. 

### Inconsistency resolve by read repair approach:
Inconsistency may take place in te eventual consistency. For example, you request to purchase a book but that is not available in the book sheleves. 
This kinds of inconsistency can be resolved by **read repair** approach. In the `read repair` approach, for each query/transcation, consistency is verfied. If consistency is not found, state is updated. So in the example, when you find an inconsistency do you kick off the heavier process to update state across all of your ledgers.

## Strong Consistency VS Eventual Consistency
1. Strong Consistency ensures consistent state
2. Strong Consistency address scale with client/server architecute
3. Eventual Consistency does not ensure consistent state.
4. Eventual Consistency handle high volume of transactions and resolve stateful inconsistencies when they are found. 





