### When we move from a single instance of server to multiple then the need arises to manage incoming connection requests.

Multiple server instances are usually kept so that the load is distributed rather than a single point get overloaded.

But these are some challenges:

- Redirecting requests when one of the instances crashes.
- Judiciously utilizing all the available resources.

These are handled by load balancers.

For example: Amazon ELB. You can use pre defined algo for load balancing or write your own too.

![Load Balancing Algorithms](Load_Balancing_Algorithms.png)
