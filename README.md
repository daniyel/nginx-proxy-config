# nginx-proxy-config

## Information

This is an example nginx config, that sets proxy server which enables TLS 1.0, 1.1 and 1.2.

## Reason behind it

Some legacy systems, in my case old cash registers could not communicate with the API, so we had to enable TLS 1.0 and 1.1, which is nowadays not recommended anymore.
So updating thousands of cash registries is pretty much costly solution, so in meantime this is an interim solution to the problem.

## Diagram

![Alt text](src/nginx-proxy-diagram.jpg?raw=true "nginx proxy diagram")
