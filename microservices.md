## How to do transactions in microservices?
- First, it's actually the best if we can avoid transactions in distributed systems
- If we have to do transactions, there are a few patterns to commit and rollback.
### SAGA
- SAGA pattern is a pattern when all services need to persist the data, if one of them fails, they should send a request back to the previous service to rollback and this process repeats at the previous service.
- There are 2 ways to implement this since the transaction management should not be done by individual services
- For event driven system, a message is sent to different services to persist the data, if all services succeed, they all send SUCCESS messages back to the queue and distributes to other services to commit. If one of the services fails, a FAIL message is sent to other services to rollback.
- For synchronized system, we can have a orchestration service to manage all requests and responses from and to services, if the responses are all SUCCESS, the orchestration service will mark transaction as successful, if one of the responses is FAIL, the orchestration should send requests to all services to rollback.
- The drawback of this approach is performance but the data is kept consistent throughout all services
### Eventually consistent
- Another way is to have a eventually consistent by running batch job at the end of the day to compare data between services
- The drawback is obviously the inconsistency of the data.

### Outbox pattern
- Each time a transaction is registered, we save the a record to the Event table.
- A service will pick up this record in a time  interval and send it to the message queue
- This is useful in case data is critical and we need to catch all transactions