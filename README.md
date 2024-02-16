# stig-scans

stig-scan requires a running container with a shell to scan. With that in mind,
we need to launch a -dev variant of one of our images, and get the container
ID:

```bash
CONTAINER_ID=$(docker run -d --entrypoint /bin/sh cgr.dev/chainguard/nginx:latest-dev -c "tail -f /dev/null")
```

Launch a new container. Need 
```bash
ansible-playbook playbook.yaml -e "container_name=$CONTAINER_ID"
```