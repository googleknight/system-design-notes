### How do you add new files to CDN ?

A. In your file system(either local like Hadoop or in cloud like S3) you have a dedicated folder which is being checked by the CDN service for any new file.
This check could be periodic, which happens every 10 seconds or so. Once it sees a new file, it sends that file and its metadata to their cloud computer which pushes to all the CDN servers across the globe.

#### Why not to use CDN Servers for storing dynamic content ?

A. For example let's say some user places an order for 10 units in US, some user places an order of 50 units in India. While you had only 50 units total. Then when both of them will get processed it will fail as it is going beyond the total available. So for dynamic data it is best to have data in database as a single source of truth.

Examples of CDN: Akamai, AWS Cloudfront, Cloudflare
