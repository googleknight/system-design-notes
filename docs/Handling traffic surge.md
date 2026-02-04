### In cases of some kind of flash sale for some hours/days, you prepare your system for it.

In context of e-commerce these are some common steps are:

- Estimate the expected scale: Talk to business folks and understand the expected network traffic on your platform during that time. This can be roughly estimated by number of followers on social media platform, Google Ads and other ads usual conversion like ads shown to 100k and there is 1% usual conversion. Currently registered users, active users, etc.
- Pre-emptive scaling: Few hours before that scale up your system and keep them ready. Monitor the vital metrics. Do some kind of load testing and monitor the metrics, if everything is behaving normally. Progressively load your system to correctly understand how much computing power you need.
- Some useful metrics to monitor: request latency, memory utilized, currently active users.
- Understand the access patterns: The pattern in which data is accessed in your system. If there's a data which will be shown to every user like collection of products which are on sale. keep them in cdn, their image links too in cdn. Keep your cache warmed up.

### In case of sudden jump in traffic your system likely to crash, in such cases how do you handle the situation.

- Begin identifying that are all the users who came were real users ?
  - Some common patterns are, with same user ids there could be thousands of requests/minute, in this it could be from different ips too!(DDoS attack)
- Gate-keeping to avoid malicious attacks: Use Cloud providers or CDN offers solution to identify and stop them. Eg.: Cloudflare, AWS Web application firewall. On server side have a firewall looking at the requests.
- Graceful degradation incase of over-loaded requests: Serve high priority requests first and lower ones later or drop them with an error message.
- Discarding requests altogether if needed:
  - In a request flow, at any node(application server/cache/db etc) if the upstream or downstream service is failing or restarting, it is best to discard requests to give time to recover for that service(s).
  - Short-circuit: Downstream services are overloaded so current service starts failing the requests to the downstream services.
  - Back-pressure: When the downstream service is overloaded and it starts failing requests from upstream services
  - Usually an error is thrown which signifies that it is a temporary error rather than permanent, so maybe try after a minute or so.

### How does your system actually handles requests?

Without any configuration by default most of the servers follow a queue,i.e. FIFO pattern, and faces head-of-line blocking.
To handle it one could:

- use Parallelism
  - Parallel queues and servers.
  - Multiple VM in the servers.

- Concurrency
  - Same queue is used but multi-threaded approach is used to process requests out of order.( More time taking requests are being processed later or asynchronously)
  - Uses protocol which supports having multiple request queues, like gRPC.

### To future proof your system for increase surges in traffic

Ratelimiting: Answer the ones which you could afford while drop the rest. As making some users happy is better than making everyone unhappy.

[Rate Limiting](/Rate%20Limiting.md)
