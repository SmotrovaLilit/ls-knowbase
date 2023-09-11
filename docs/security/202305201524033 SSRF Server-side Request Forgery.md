---
tags:
- ssrf
---
# SSRF Server-side Request Forgery
It is important to understand that the forged request originates from the vulnerable server, not our browser.
We can use the privileges of vulnerable server.
SSRF vulnerabilities can be especially effective against microservice architecture
 If the microservices are in a _flat network_,[3](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/server-side-request-forgery/introduction-to-ssrf/introduction-to-ssrf#fn3) we could use an SSRF vulnerability to make one microservice talk directly to another one
 Any controls enforced by the API gateway would not apply to the traffic between the two microservices, allowing an SSRF exploit to gather information about the internal network and open new attack vectors.
 
##  Interact with vulnerable servers:
 - loopback interface,
 - Private ip addresses:
	 - 10.0.0.0/8 (Number of addresses: 16,777,216)
	 - 172.16.0.0/12 (Number of addresses: 1,048,576)
	 - 192.168.0.0/16 (Number of addresses: 65,536)
 - link-local addresses [[202305201524033 SSRF Server-side Request Forgery#^cd73f8]]
 - predefined host names [[202305201524033 SSRF Server-side Request Forgery#^43ee88]]
 - metadata.google.internal [[202305201524033 SSRF Server-side Request Forgery#^07b8e3]]
_Basic SSRF_ - when vulnerable application will do an attacker's request and returns the result.
If application has parameters: _URL_, _URI_, or _link_ , we need to test the application for SSRF
_Blind SSRF_ - when vulnerable application will do an attacker's request but doesn't return the result.

Using SSRF we can get access to http content or even files:

```
file:/tmp/foo.txt 
file:///tmp/foo.txt
file:///etc/passwd
```

## Discovering SSRF vulnerabilities 
- We can do request to an attacker's machine and check http server logs

## What we can do with SSRF vulnerabilities
- retrieving data using GER requests
- retrieving file content. Example:  file:///etc/passwd
- do POST/PUT... requests using gopher [[2023090518224444 SSRF with gopher]]
- sometimes applications save files from the url and save them with blobId, which we can execute later calling another get request.  See example here [[202305201524033 SSRF Server-side Request Forgery#^1e32a4]]
## References
1. web200.Server-side Request Forgery  
2. (Wikipedia, 2021), [https://en.wikipedia.org/wiki/Server-side_request_forgery](https://en.wikipedia.org/wiki/Server-side_request_forgery) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/server-side-request-forgery/server-side-request-forgery#fnref1)
3. (Wikipedia, 2021), [https://en.wikipedia.org/wiki/Link-local_address](https://en.wikipedia.org/wiki/Link-local_address) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/server-side-request-forgery/introduction-to-ssrf/interacting-with-back-end-systems-and-private-ip-ranges#fnref1) ^cd73f8
4. (Amazon Web Services, 2021), [https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html#instancedata-data-categories](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-instance-metadata.html#instancedata-data-categories) [↩︎](https://portal.offsec.com/courses/web-200/books-and-videos/modal/modules/server-side-request-forgery/introduction-to-ssrf/interacting-with-back-end-systems-and-private-ip-ranges#fnref2) ^43ee88
5. https://cloud.google.com/compute/docs/metadata/overview ^07b8e3
6. web200, p. 413  ^1e32a4
