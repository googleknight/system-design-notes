### Rate Limiting Algorithms

- Token Bucket: You have max requests/second set in cache, every time a new request comes in that second it decreases the counter(token) and when it is responded then the counter increased again. So we know that at max how many requests are handled at a time.
- Leaky Bucket: How much time each request is allowed is set, for ex. 1/10 of second, i.e. 100ms. So in buckets of 100ms only each request gets processed and until the turn comes they wait in queue. Constant rate of requests. (Not used much, very rare)

#### Applying Rate Limiting

- Local Rate Limiting: Multiple servers, having their own rate limiting set locally.Faster, but not efficient use of resources. Easy to implement
- Centralized Rate Limiting: One of the server controls the rate limiting. Efficient use of resources but network latency. Allows global control.

![Local Rate Limiting vs Centralized Rate Limiting](RateLimiting.png)
