
# RabbitMQ setup
[Install](https://www.rabbitmq.com/download.html) the RabbitMQ server and run the service. You can follow [this tutorial](https://www.rabbitmq.com/getstarted.html)

### Execution
Open three terminals, one for the Send and two for the Receive:

- ../Send (x1)
- ../Receive (x2)

This setup is to see the Round robin feature as default configuration of RabbitMQ where all the messages are balanced between clients (receivers). 
In this case, we have 2 clients and all messages will be sent evenly to each of them, like taking turns.

On both /Receive terminals, run the (same) project with `dotnet run`.

On the /Send project terminal run the commands:
- `dotnet run "First message"` 
- `dotnet run "Second message"` 
- `dotnet run "Third message"` 
- `dotnet run "Fourth message"` 
- `dotnet run "Fifth message"` 

The messages should be "split" or balanced between receivers:
_In one terminal:_
`=> [x] Received First message...
=> [x] Received Third message...
=> [x] Received Fifth message...`

_In the other terminal:_
`=> [x] Received Second message...
=> [x] Received Fourth message...`
