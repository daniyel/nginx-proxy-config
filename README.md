# nginx-proxy-config

## Information

This is an example nginx config, that sets proxy server which enables TLS 1.0, 1.1 and 1.2.

## Reason behind it

Some legacy systems, in my case old cash registers could not communicate with the API, so we had to enable TLS 1.0 and 1.1, which is nowadays not recommended anymore.
So updating thousands of cash registries is pretty much costly solution, so in meantime this is an interim solution to the problem.

## Diagram

![Alt text](src/nginx-proxy-diagram.jpg?raw=true "nginx proxy diagram")

## With Let’s Encrypt

Copy all scripts from folder `scripts` to `/home/myuser/scripts`. In `env.sh` you update `CERTBOT_EMAIL` to your own email or you can add `CERTBOT_EMAIL` environment variable in the `.bash_profile` of the user, that will execute `run_certbot.sh` as cronjob. Another option is to add it in the `/etc/environment` file, if that suits your case more.

Execute:

```
$ sudo crontab -e
```

and add line:

```
10 3 * * 0 /bin/sh /home/myuser/scripts/run_certbot.sh
```
which means execute job `at 03:10 on Sunday`.
