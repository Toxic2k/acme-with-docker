Run as a service with mounted docker.sock

docker run --name acme -v "/var/run/docker.sock:/var/run/docker.sock:ro" -v "./acme:/acme.sh" toxic2k/acme-with-docker daemon

And use exec with --reloadcmd

docker-compose exec acme --issue ..... --reloadcmd "docker restart nginx"
