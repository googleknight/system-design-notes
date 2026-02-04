### How reliable is the system ?

- Notice any points of failure, which on failing can lead to collapse of entire system.

- Any external dependency is prone to failure.

To fix this:

- Have redundancies.
- Have Cloud providers for better reliability like for CDN, for storage etc.
- For external dependencies have backups of using some other external dependencies like multiple payment gateways.
- Have graceful shutdown. Show generic error message.
